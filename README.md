# Contact Game - a word guessing game against the computer
For LING360 class

**Description:**
A word guessing game where the player thinks of a word and gives its first letter to the computer. The computer tries to guess the player’s kept word by going over all the words starting with the given letter in the corpus. It stores its guess as computer_guess and finds a similar word to generate a question: “Is this associated with {similar_word}?” A similar word is found thanks to the trained word2vec model. 

Depending on the difficulty level the player picked, the player tries to find the computer’s guess within a number of attempts. The computer says “You are so close!” when the user’s guess is one letter away from computer’s guess or the computer’s guess starts with player’s guess which is at least 6 letters long. The distance between the computer_guess and player_guess is found with editdistance library. 

 If the player manages to find computer’s guess, another round begins and the computer comes up with a new guess. If the player fails, the computer demands the following letter of the player’s kept word. In the following rounds, the computer finds a new word with the given letters. Also, used words are stored in a list to not generated again as computer_guess or similar_word.
 
**How to win the game?**

The computer wins if it manages to predict player’s word before the word unfolds itself.
The player wins if the word reveals itself or the computer cannot come up with a new word to guess player’s word.

**Data:** [A kaggle dataset](https://www.kaggle.com/datasets/mahdinamidamirchi/turkish-sentences-dataset) based on turkish wikipedia, april 2021 (min 2, max 14 words per sentence, no special symbol or abbreviation).

**Needed packages:** NLTK, editdistance, stanza, tqdm, os
