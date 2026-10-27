---
title: Custom Exception & Endpoints
weight: 1
date: 2026-10-12
draft: false
---

## Notes
### Custom Exception
Made a "UserAlreadyExistsException" to when a User tries to register with a user already existing in the database.
Added it to my ExceptionMapper.

### POST and PUT endpoints
Added post and put endpoints. Both have a check for valid input. Since both checks were identical, I refactored the code and made a "validate" method, containing the check.

### Endpoints
Refactores my controllers, separating the endpoints according to their purpose.