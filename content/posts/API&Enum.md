---
title: API & Enum
weight: 1
date: 2026-09-26
draft: false
---

## Backend
- Implemented API fetching to program
- Created Enums

## Notes
### API
While creating the API fetching class, I had to take into account my API uses "cursor" pagination, which, once understood, is rather simple, but as it was new to me, I had to learn how it works.
I decided to make a method that takes two parameters, a "body part" and "equipment", so you can search specificly what you are looking for and equipment you have available. While more methods will surely be needed in the future, I decided it was a good start, and I will furthur add methods as I need them, instead of guessing which ones I will need.

A mistake that took me some time to realize, was the url is case sensitive, which gave me inconsistent data. While I knew this, when I fixed the link, and pressed "enter", my browser used a suggested link I had used before (where case sensitivity wasn't considered) and wouldn't work, and it took me some time to realize what was happening.

### Enum
A thing I considered, was the method's inputs would cause problems if they would have a typo. Therefore, I decided to create Enums to store the different options my program accepts, and those Enums are used as parameters. This completely removes the danger of making a typo, and I have more control over what I want my program to be able to fetch.