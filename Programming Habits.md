# Don't Repeat Yourself

- You've probably more than once reached the point where you look at a piece of code and think; well... this piece of code kind of looks the same as same code that I've written before.

- This should rind a bell. Since it's a situation that you want to avoid. Duplicate code makes your code smell really bad. Code gets harder to maintain since adjustment to this piece of code have to be made in multiple places.

## Oce you think you're done, refactor

- Most programmers, especially those with not a lof of experience, think that their job is done once their code work's as intended. But the word "Done" includes more than just writing a piece of code for a fancy feature.
- Refactoring your code will improve readability. Chances are that you didn't produce the cleanest piece of code you've even written.
- Refactoring can also help to reduce the complexity of the code, which will improve maintainability. In the long run, refactoring your code will pay for itself.

## Focus on the business

- On the Journey to becoming a master of your tech stack, it's important to keep the business in mind. Why are you building this?
- SOme developers are only interested in the technical aspects of their job. They don't care about the business or the economic factors that justify their job's existence.
- Is what you're working on creating value for the business or are you spending too much time on something that doesn't really matter? it's an important question to ask yourself.

## Small Commits

- Your code get easier to debug as well once you start making small commits. It's easy to roll back to a previous commit to check whether a bug was introduced in that commit. Once you've found the commit where the bug was introduced there's not a lot of code that could have caused this bug.

## Touch it once

- I'll fix it later. Yep we've all heard that before. And we all know how often things got fixed "later". You're right. Never. Every time you see a TODO comment you know someone failed to touch it once
- Work on a piece of code or user story form zero till it's completely finished.
- But what does completely finished mean?
- It means that your code is refactored, for a start. Just like we discussed before. On top of that, your code needs to be tested. And testing is for most developers probably the least favorite part of their job. write some automated test.
