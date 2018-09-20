# Slackcrypto

Slackcrypto is a chat-room based implementation of the decrypto board game published by Iello games.

The game is played by two teams of at least two people each (though theoretically limitless).  In which, each team has a set of 4 cards that they can see, but are hidden to the other team.  Each team takes turns stating related words (for the entire group to hear), such that their team will guess the ordering of the clues.  However, the other team has the first opportunity to guess the ordering, so clue givers must be sneaky enough to hide the order from the opposing team, but transparent enough to get their team to guess. 

The game ends once one team has either failed twice, or one team has succeed twice.  

Why is this a good game for slack? 

Given that it is entirely word-based, and the actions have discreet outcomes, it seemed like a great opportunity to practice building a set of slack integrations, though theoretically this game could be made agnostic to any set of web interactions.

It's also a really cool take on messing around with making data structures.  

[Decrypto rules](https://boardgamegeek.com/filepage/156950/english-rules)


## Data Structure

### Top level structures
- Games
- Players
- Phrases
- Rounds
- Teams

### Relationships
- Game Rounds
- Word Association (describes what a set of phrases have been used for) 
- Team Players
- Game Channel

Can probably hard-code a fair amount of the slack interaction to begin, and associate that later.  

## Challenges

There is really nothing to prevent players from cheating with one another.  It's easy enough to just open up a text or private channel, and to give the answers.  So that bit at least is based purely on player trust.  One potential solution to this is by not knowing who is on your team.  Although in some sense, that would destroy the fun in the game, as you are purposefully trying to encrypt and decrypt the sequence based on your knowledge of the other humans in the room.

Thought: What if the order were different, per player on the guess team? This would certainly be security via obfuscation, but people could just share their unique orders?  Hmm... something to think about.  It would also make the game feel *incredibly* distant. 

The other option here is more on the nose, which is just like, sign the contract up front, which actually makes people more likely to follow the rules. 

## Game Actions

### Player Actions

- Start Game
- Give Clues
- Guess Order
- View Answers (owning team only)
- View Guesses 

Can't guess unless game state is correct.  Can't give clues unless game state is correct.  

### Outcomes

- Reveal Correct Order
- Change turn order
- Assign Clue Giver
- Assign Failure Token
- Assign Success Token 

## Contribution

The best way to contribute is to fork this branch and create pull-requests based on the issues and tickets that have been created.  This is currently in the formative stages and will be updated as time goes on. 
