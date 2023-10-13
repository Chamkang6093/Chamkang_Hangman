# Improving Hangman Puzzle Strategy, in the Perspective of Reinforcement Learning

## Overview
* Applied Deep Q-Learning algorithm to generate and modify strategies repeatedly given a training set of 250,000 words, and the accuracy reached over 25% when it stopped at a given threshold.

## Instructions
* When a user plays Hangman, the server first selects a secret word at random from a list. The server then returns a row of underscores (space separated) — one for each letter in the secret word — and asks the user to guess a letter. If the user guesses a letter that is in the word, the word is redisplayed with all instances of that letter shown in the correct positions, along with any letters correctly guessed on previous turns. If the letter does not appear in the word, the user is charged with an incorrect guess. The user keeps guessing letters until either (1) the user has correctly guessed all the letters in the word or (2) the user has made six incorrect guesses.

* We are supposed to write a "guess" function that takes current word (with underscores) as input and returns a guess letter.

* Our algorithm is required to use a training set of approximately 250,000 dictionary words.

* Here is a basic, feasible algorithm. This algorithm will match the provided masked string (e.g. a _ _ l e) to all possible words in the dictionary, tabulate the frequency of letters appearing in these possible words, and then guess the letter with the highest frequency of appearence that has not already been guessed. If there are no remaining words that match then it will default back to the character frequency distribution of the entire dictionary. This benchmark strategy is successful approximately 18% of the time.
