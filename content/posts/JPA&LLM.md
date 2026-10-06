---
title: JPA & LLM
weight: 1
date: 2026-09-06
draft: false
---

## Backend
- Implemented JPA relations between entities.
- Implemented LLM as a quiz generator.

## Notes
Exercise entity had Lists of Strings, which were saved as a @ElementCollection. Under review, learned that could cause multiple instance of the same element, decided to better make them their own tables and utilize their Ids. 

Under development, realized my choice of API might not be optimal. Will further research for APIs that better suit my needs.

The quiz LLM works by having a list of subjects, where the promp defines it should select a random subject and generate a quiz. However, under testing, the LLM would pick the first element of the list the vast majority of times. To fix this, an array was created with all the subjects, which was sent inside the prompt, and a random generated value (fitting to the array size) would tell the LLM exactly which element to select.
This worked perfectly, however the quiz wasn't working as intended. The other issue was the correct answer was always placed on the second option. This was fixed with the same logic, a random number (fitting the number of possible answers) was generated, and then injected into the LLM prompt.

Now the LLM properly selects a random subject from the list, and displays the correct answer on a random answer option.