---
title: US & AC
weight: 1
date: 2026-09-11
draft: false
---

## Requirements
Created User Stories for my project, and the Acceptance Criteria for each of the User Stories:

US1 - Create account
As a user, I want to create an account, so that I can have my own training data.

    - AC 1.1
    Given I am not logged in, when I enter a valid username and password and submit, then a personal account shall be created.

    - AC 1.2
    Given I am creating an account, when I enter invalid data, then I am informed about the issue, the account is not created, and I'm sent back for another attempt.

    - AC 1.3
    Given I have successfully created an account, when I log in, then I can access my personal data.

US2 - Admin role
As an admin, I want to have permission to modify certain data, so that I can keep the app's data up to date.

    - AC 2.1
    Given I have an admin role, when I log in, then I can modify certain user data.

US3 - Create training split
As a user, I want to create my own split, so that I can control how my workouts are organized throughout the week.

    - AC 3.1
    Given I am logged in, when I create my split, then I can select the number of days I intend to train per week.

    - AC 3.2
    Given I am logged in, when I create my split, then I can give my split a customized name.

US4 - Personalize workout
As a user, I want to personalize my workouts, so that I can control their names and exercises.

    - AC 4.1
    Given I am logged in, when I've created my split, then I can give my workouts a personalized name.

    - AC 4.2
    Given I am logged in, when I've created my split, then I can add execises to a workout.

US5 - Select presets
As a user, I want to select a preset, a pre-made split with workouts, so that I don't need to create my own.

    - AC 5.1
    Given I am logged in, when I select to create a split, then I can select to use a preset.

US6 - List of exercises
As a user, I want to access the list of all exercises, so that I can browse the available exercises.

    - AC 6.1
    Given I am a user, when I select to see all the exercises, then a list appears with all the exercises.

US7 - Information about exercise
As a user, I want to see information about each exercise, so that I know how to perform them.

    - AC 7.1
    Given I am a user, when I click on an exercise, then information about that exercise will be displayed.

US8 - Learn about topics
As a user, I want to access information about training topics, so that I can learn and improve my fitness knowledge

    - AC 8.1
    Given I am a user, when I select a topic to learn about, then information about that topic will be displayed.

US9 - Quiz about topics
As a user, I want to answer a quiz about training topics, so that I can test my knowledge.

    - AC 9.1
    Given I am a user, when I select to answer a quiz about training topics, then a random quiz will be generated.

    - AC 9.2
    Given I am a user, when I select an answer to a quiz, then the app will show me the correct answer.

    - AC 9.3
    Given I am a user, when I have completed a quiz, then I can select to continue with another.

US10 - Track workout
As a user, I want to track my performance during a workout, so that I can save my progress.

    - AC 10.1
    Given I am logged in, when I'm tracking my current workout, then I can modify the performance data for each exercise.

    - AC 10.2
    Given I am logged in, when I have completed a workout, then I can save the changes.

    - A 10.3
    Given I am logged in, when I save my workout changes, then it will be saved for the next time I perform those exercises.

US11 - Track weight
As a user, I want to track my body weight, so that I can have a history of my weight.

    - AC 11.1
    Given I am logged in, when I select to track my weight, then a field will be displayed for me to enter my current weight.

    - AC 11.2
    Given I am logged in, when I select weight history, then a list of all past provided data will be displayed.

US12 - See my workouts
As a user, I want to view the structure of my current workouts, so that I can have an overview of my workouts.

    - AC 12.1
    Given I am logged in and have created at least one split, when I select to see my workouts, then an overview of my workouts will be displayed.

US13 - Workout history
As a user, I want to view my workout history, so that I can see the progress I've made.

    - AC 13.1
    Given I am logged in, when I select to see my workout history, then past workouts with their data will be displayed.