# User Stories
## Tracking Games

### Player

As a player, I want to track life totals throughout the course of a game, because life totals are an integral aspect of the game.

As a player, I want to track which turn / round it is, so that I can check things like tempo, land drops, and lethality of a deck.

As a player, I want to track additional player-states such as poison counters and commander damage, because like life totals, these things are integral to the game.

As a player, I want to be able to rewind through turns or rounds to see where things were at, and choose to recover the state from that point if necessary, so that I can more quickly fix mistakes with things like life totals.
- Moving to the previous turn restores the previous active player and turn position.
- Life totals, commander damage, poison counters, and other tracked values are restored to their values at the selected turn.
- Rewinding to an earlier turn or round lets the players review that state before choosing to restore it.
- The tracker only restores values Cluestone records; players resolve untracked tabletop actions and rules questions themselves.

As a player, I want the ability to toggle whether commander damage is automatically synced with the life total, or not.
- Commander damage and life are synchronized by default.
- While synchronized, increasing commander damage reduces life by the same amount.
- While synchronized, correcting commander damage applies the corresponding correction to life.
- Direct adjustments to life total do not alter commander damage.
- When synchronization is disabled, commander damage and life can be changed independently.
- Commander damage is tracked separately for each opposing commander source.
- A player can be marked as having lost after receiving 21 accumulated damage from any single commander source, regardless of their life total.

As a player, I want to know whose turn it is at a glance, so I can keep track, and so that players at the table don't have to ask as frequently.

As a player, I want the ability to choose my profile name and background image, to clearly distinguish myself from the other players. 

As a player, I want to store my decks in my profile so that the background image can be quickly recalled for personalization.

As a player, I want a way to roll dice or flip a coin, because these randomization features are sometimes a necessary for the game.

As a player, I want my fellow players to be able to access their profiles and decks from my device, so that we can quickly pick up and go.

As a player, I want a quick way to randomly select a player, for the purposes of choosing who goes first, or other in-game purposes.

As a player, I want to be able to pause, close, and recover a game in-progress in case we need to step away or close the app, so that we can quickly return to the action.

As a player, I want the ability for life totals to go negative, so that I can track for game purposes.

As a player, I want to be able to mark when a player has lost the game, so that we can know who is still playing. (When there is only one player left, they have won, and all others have lost)
- Eliminations are entered one player at a time.
- An eliminated player's turn slot is skipped for the remainder of the game.
- An eliminated player remains visible and can continue viewing the game state.
- An eliminated player is greyed out on the tracker to indicate they have lost.

As a player, I want to be able to mark when a player has won the game, irrespective of other players losing, because some cards let you win the game from non-standard means.

As a player, I want to know when the game is over and who won, so that I can celebrate my victory or congratulate the victor. (Ideally this is automatic, based on whenever there is only one person remaining who hasn't lost the game)
- A completed game has exactly one winner.
- The final remaining non-eliminated player is declared the winner.
- Players can declare a winner directly when an alternate win condition applies.
- A game can instead be recorded as drawn or abandoned.
- Drawn and abandoned games are excluded from performance statistics for now.

As a player, I want to be able to open the app and select a game in progress that my profile is part of, even if that game was started on a different device, provided my profile is linked and the game is synced to the internet.

As a player, I want to be able to track when I have multiple consecutive turns within the same round (i.e. progressing the turn without progressing to the next player).

As a player, I want the option to hide or show the "plus" (+) and "minus" (-) buttons from player sections (All or nothing).

## Backlog / Feature Requests

### Player

As a player, I want the option to be able to track which player damage originated from, for analytical purposes.
