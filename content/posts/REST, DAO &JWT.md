---
title: REST, DAO and JWT deployed secret
weight: 1
date: 2026-10-27
draft: false
---

## Notes
### REST
Created another controller test class, where I added Rest assured tests for "register" and "login" endpoints, tests include both happy path and unhappy path. Made a populator class to have some data to test with.

### DAO
Updated savedExercise() and updateExercise() in my ExerciseDAO to check for body parts and equipments (refactored into their own methods), they check wether a body part/equipment already exists, and if not, it creates it. The prupose is to keep the database clean without duplicates.

### JWT deployed secret
Configured my deployed environment variables to contain its own jwt secret, and it being accessed in my docker-compose.yml file.