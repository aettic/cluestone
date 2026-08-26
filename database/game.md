A "Game" refers to whenever multiple Players sit down to play Commander. It starts when all Players have chosen their Decks and are ready to play. A completed game normally has exactly one winner. A game may instead end as a draw or be abandoned; drawn and abandoned games are recorded but excluded from performance statistics for now.

A game is made up of multiple rounds.

A round is made up of one turn per player by default.

If a player loses, concedes, or otherwise leaves the game, their turn slot is skipped for the remainder of the game. The player can remain present at the table and can still view the game state.

A player is a profile that includes their name, and their deck.

A deck can be as simple as a deck nickname, a chosen commander, or a full deck list (integrated in the app), as well as a background (which can be a card image or a selected color).

## Tracker Behavior

### Previous Turn and Rewind

The tracker preserves enough historical state to restore an earlier turn. Choosing **Previous Turn** functions like an undo: it moves the turn position and active player back one turn and restores all values tracked at that point, including life totals, commander damage, and other counters.

The broader **Rewind** action lets players review earlier turns or rounds and restore the game to a selected state. It is intended to help the table correct incorrectly entered values after a missed effect or rules mistake. Cluestone does not attempt to reproduce untracked tabletop actions or enforce Magic's rules.

### Commander Damage and Life

Commander damage begins at 0 and is tracked separately for each opposing commander source. A player loses after receiving 21 commander damage from any one commander source, regardless of their life total.

Commander damage is synchronized with life by default. While synchronization is enabled, increasing commander damage reduces life by the same amount, and correcting commander damage applies the corresponding correction to life. Players can disable synchronization in the game settings and manage the two values independently.

### Ending a Game

Players enter eliminations one at a time. When only one non-eliminated player remains, that player is the winner. A player can also be declared the sole winner directly when a card effect or another valid game condition causes them to win.
