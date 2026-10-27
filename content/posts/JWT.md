---
title: JWT, Login & Register
weight: 1
date: 2026-10-23
draft: false
---

## Notes
### JWT
Implemented JWT to the application. My GET endpoints are available to everyone, but my POST, PUT and DELETE endpoints require a special permission, which only Users with the role "admin" have.

### Login & Register
Added Login and Register endpoints. Both endpoints needed their own DTO to hold the necessary data for their purpose, and Login generates a JWT token containing their "role", which determines their permissions.
Endpoints that modify data require extra permission, so they check the users permissions before executing.

### REST & Test secret
Since I had done my REST-assured tests before implementing JWT (knowing I would later need to update them with JWT), now it was time to do so.
I only need an "admin" token to tests my POST, PUT and DELETE endpoints, so I create an "admin" token on test server startup.

However, I had to make a new secret, so my production and test servers don't share the same. So I generate one in my test class and added it as a parameter to my startServer method, that way the test server uses test secret, my local server uses config.properties' secret, and my deployed version uses its environment variable secret.
