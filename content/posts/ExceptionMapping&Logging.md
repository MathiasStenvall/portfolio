---
title: Exception Mapping & Logging
weight: 1
date: 2026-10-05
draft: false
---

## Notes
### Exception Mapping
Created an Exceptionmapper class, implemented basic 400, 404 and 500 exceptions.
Will add further exceptions as needed.

### Logging
Decided to add the logging logic inside my exceptions, meaning it got implemented in my ExceptionMapping class, and every exception logs accordingly.

Changed the logging behaviour, instead of appending the same file, which will eventually create one huge file, I decided to make the files have a size limit, and upon reaching it, it creates a new file. This gives a better overview and I can delete old files if I wish to do so. 
This was achieved with:
- RollingFileAppender: Switches to a new file when a condition is met.
- FixedWindowRollingPolicy: Defines what happens when a rollover is triggered.
- SizeBasedTriggeringPolicy: Defines when the rollover takes place.