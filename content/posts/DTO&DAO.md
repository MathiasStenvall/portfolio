---
title: DTO & DAO
weight: 1
date: 2026-09-27
draft: false
---

## Backend
- Made ExerciseDTO
- Created ExerciseMapper
- Several DAO for exercise fields

## Notes
### ExerciseDTO
Decided to save the data in a DTO instread of the entity itself, respecting SOLID principle.
The collections in this class are all of String, that will later be converted to the proper class for the Exercise class (body parts, equipments...etc).

### ExerciseMapper
My first thought was to have my ExerciseDAO which would take a list of exerciseDTO and return a list of exercises (from DTO to entity), but this class would also need to interact with the database, which started to feel off, as this class would have more than one responsability.
This thought made me create an ExerciseMapper class, that does exactly that, convert exercise DTOs to Exercise entities.

### Exercise field DAOs
To better my design, I have tables that contain information about the exercises, such as "target muscle" for example. But many exercises can have that same value, an dthat value can be in many exercises, which describes a ManyToMany relation. These fields have their own table, and in order to convert an exerciseDTO to the Exercise entity, I need to check weather that data exists in my database, if it does, we use the existing row, and if it doesn't, we create a new row with this new data.
This made me create a DAO for every ManyToMany field, where I use a method that either finds the data and uses it, or creates it and uses it.

This definitely made it more complex, but now I have the responsabilities separated.

The API also returns an array of Strings which contain the instructions of each exercise, I converted it to a regular String containing every element instead, since I see no benefit in having it as an array.