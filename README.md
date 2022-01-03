# Basics: Blackjack

## Introduction
Implement a simplified version of Blackjack. If you're not familiar with Blackjack, refer to this video for game rules. Our simplified rules are the following. Please read all the requirements before starting it!
1. There will be only two players. One human and one computer (for the Base solution).
2. The computer will always be the dealer.
3. Each player gets dealt two cards to start.
4. The player goes first, and decides if they want to hit (draw a card) or stand (end their turn).
5. The dealer has to hit if their hand is below 17.
6. Each players' score is the total of their card ranks. Jacks/Queen/Kings are 10. Aces can be 1 or 11.
7. The player who is closer to, but not above 21 wins the hand.

## Base
### Gameplay Description
The main function runs on each player's turn. The sequence of actions in the game might be the following.
1. Deck is shuffled.
2. User clicks Submit to deal cards.
3. The cards are analysed for game winning conditions, e.g. Blackjack.
4. The cards are displayed to the user.
5. The user decides whether to hit or stand, using the submit button to submit their choice.
6. The user's cards are analysed for winning or losing conditions.
7. The computer decides to hit or stand automatically based on game rules.
8. The game either ends or continues.
Note that for the main function to perform different logic on user input, for example when a player decides to hit or stand, we may wish to consider using a new game mode.

### General Tips
- Creating helper functions can be a powerful way to refactor your code and keep it neat.
- Don't be afraid to throw away code, especially if you already know how you would write it better.
- Commit your code often, whenever you have a small working version. For example, each action listed above would be a commit. Make concise and precise commit messages so that you can reference your old changes later.

## Review Coding Strategies
### How to Prioritise Work
Given the above *final* action sequence to play a full game, how do we break these down into sub-features that we can work on (and verify they are working) one at a time? We want to work on features in small parts, but not have to redo any work as we expand the capability of the game, so we want to plan ahead to make sure we can start small and scaffold in the later features at the same time.

If you already have an effective strategy for creating your game, you can skip ahead. If you're not sure how to approach the game, try applying the following strategies to get started. The following are strategies for breaking down larger projects into smaller tasks to keep up progress, momentum, and motivation on the project. Please read to the end before starting.

### First Version: Compare Initial Hands to Determine Winner

Aim for a playable game. The essence of blackjack requires:
1. Two players - a player and a dealer (computer).
2. A deck of cards.
3. A starting hand of 2 cards for each player.

Comparing both hands and determining a winner. The possible scenarios are:
1. A tie. When both the player and dealer have the same total hand values - or if both draw Blackjack
2. A Blackjack win. When either player or dealer draw Blackjack.
3. A normal win. When neither draw Blackjack, the winner is decided by whomever has the higher hand total.

Return appropriate messages. For example:
Player hand: Ace of Hearts, King of Spades
Dealer hand: 8 of Clubs, 8 of Spades
Player wins by black jack!

Test your code.

### Second Version: Add Player Hit or Stand
The player hitting or standing is different from the dealer hitting or standing. The rules state that the dealer hits or stands after all players are done, so let's work on the players hitting or standing first.

The player hitting or standing is a new mode in the game that allows the player to enter their choice. Add the logic for when the player busts (has a total score of >21).

Refactor your logic to wait until the player is done to evaluate the game-winning condition.

The player should not immediately lose if he busts - there is a possibility he will tie with the dealer if the dealer also busts.

Test your code.

### Third Version: Add Dealer Hit or Stand
The rules state that the dealer hits after the player is done. After the player confirms they are done, add the logic for the dealer adding cards to their hand. This should happen before the winning condition.

Test your code.

### Fourth Version: Add Variable Ace Values
Add logic to determine whether Aces should have value of 1 or 11 for a given hand.

For example, if a player draws cards in the following order:
  "Ace" and "2"       (total 13)
  "4"                 (total 17)
  "Ace".              (total 18)
  
The total hand value should be 18, as only ONE of the aces will be counted as 11.

Test your code.
