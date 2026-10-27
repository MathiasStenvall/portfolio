---
title: Concurrency
weight: 1
date: 2026-10-07
draft: false
---

## Notes
### Atomic
Have added an endpoint that counts the amount of requests my API recieves since it got initiated.
This feature was a perfect fit to use Atomic, so it can safely update when several users are modifying (incrementing) it.

This class is made static and is called before any endpoint is accessed, using:
```java
config.routes.before(ctx -> RequestCounter.increment());
```
Then an endpoint was created where we simple get the current amoun, and display it on screen.

### Threads
After being unable to use Threads for fetching data form my external API, I was looking for somewhere else to implement it. I decided to make a new endpoint where a few stats about my API would be shown.
I created an ExecutorService with a fixed thread pool of 3:
```java
private final ExecutorService executor = Executors.newFixedThreadPool(3);
```
Every thread would fetch some data from my database concurrently, which then would be displayed on the endpoint.