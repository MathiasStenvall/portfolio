---
title: Threads & My API
weight: 1
date: 2026-10-02
draft: false
---

## Notes
### Threads
The API I'm fetching exercise data from has 1500 results, which makes fetching them all take some time. To fix this I considered using threads, however it ended up not being possible, due to the api using a cursor based pagination, which means I need the value of the cursor from last call, making using several threads not possible.

### Instructions String convertion
The instructions I get from the api is a list of Strings, however, since I see no benefit in that format, I chose to convert it into one single string.
Upon running the program, an error ocurred, the instructions were too big for my database column, which was a character varying, which can hold 255 characters. The fix was easy, change the column data to "text", which I did with:
@Column (columnDefinition ="TEXT")

### Http 429 - Too Many Requests
When fetching large amount of data I was getting an error, a http 429 - too many requests.
To fix this I added a slight delay between calls, the only downside is the process takes slightly longer.

### Exercise Id
Originally I was using the same Ids provided from the external API, which is a mix of numbers and letters. When I started making the endpoint that fetches a specific exercise with its Id, the problem became apparent, I needed a simple and intuitive Id. Adding my own Id to the exercise class fixed this issue, and now the endpoint will fetch the exercise with a given id (fx. id=829).

### Enums
Enums were used to avoid typos when searching for specific criteria, and it also provided an "url-ready" string to filter the API.

When I started making my endpoints, specifically my POST endpoint, I wanted to check several attributes, including the input should be found inside these enums, meaning I can't create a new body part or equipment (willingly or unwillingly), it has to exist in my enums. Now my Enums hold a "value" and a "urlValue".

### "EntityManager is closed"
When fetching a specific ID, since the entity has relations with other entities (tables in the database), I need to trigger Hibernate to fetch that data, because the fetch type is set to lazy. Making Hibernate find the size of those collections, was enough to create the whole Exercise entity with every data from every table.

### Pagination
After making the endpoint that fetches all the exercises, I tested it, and it returned one huge list with all 1500 elements. This worked, but wasn't ideal, and I decided to add pagination, and unlike the API I consumed, which used cursor-based pagination, I would use page-based pagination.
To achieve this I changed my getAllExercises() method from my DAO, to now fetch the rows decided by "page" and "pageSize". I set my page size to be 20, and the user will select the page with a query parameter, which means my endpoint collects the "page" query parameter, and sends it to the method.
