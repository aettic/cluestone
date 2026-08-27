# Cluestone Definitions

This glossary establishes consistent language for Cluestone's product planning, user stories, data modeling, and interface design. It describes domain concepts rather than database tables or implementation details. When another document uses one of these terms, it should use the meaning given here.

## Product Terms

### Cluestone

A local-first companion application for Magic: The Gathering's Commander format. It connects deck management, in-game tracking, game history, and analysis.

### Local First

An approach in which core features and user data remain available on the current device without an internet connection. Online services may enhance, back up, or synchronize the experience but are not required for ordinary play.

### Tracker

The in-game interface used to manage the current game state, including life totals, commander damage, counters, turns, which players and decks are involved, eliminations, and the game result.

### Analysis

The part of Cluestone that turns recorded deck, revision, card, and game data into summaries or insights. Analysis should distinguish recorded facts from estimates or recommendations.

### Game History

The collection of saved completed, in-progress, drawn, and abandoned games. It preserves what occurred and which decks or deck revisions participated.

## People and Identity

### Profile

A reusable identity for a person in Cluestone. A profile can have a display name, visual preferences, and associated decks. A profile may participate in many games.

### Player

A person playing Commander. In general product language this may refer to the human being; in data-modeling discussions, use **Profile** or **Game Participant** when that distinction matters.

### Guest Profile

A lightweight local profile used for someone who does not maintain a full Cluestone account or deck library. A guest can still be associated with games and simple deck identities, but these are limited compared to a typical user profile.

### Game Participant

One player's presence in one specific game. A game participant has a seat, game-state values, and a selected deck, and may optionally be linked to a reusable profile.

### Starting Player

The game participant who takes the first turn in the first round. They are selected either manually or by using the Random Starting Player option.

### Active Player

The game participant whose turn is currently being tracked.

### Eliminated Player

A participant who has lost, conceded, or otherwise left the game. The participant remains visible in the game record and tracker, but their position is skipped in future turn progression, and their tracker zone is visually adjusted (greyed out) to indicate that they have been eliminated.

### Winner

The single participant who wins a completed game, either by being the last non-eliminated player or through an alternate win condition.

## Decks and Cards

### Deck

The continuing identity of a Commander deck across time. A deck belongs to a profile and has at least a name. It may also have one or more commanders, artwork, notes, tags, and a complete card list.

### Lightweight Deck

A deck represented only by the information needed to identify it during play, such as a nickname and optional commander. It does not require a complete deck list. This is used for tracking purposes similarly to a guest profile.

### Deck List

The cards and quantities that make up a deck at a particular point in time.

### Deck Revision

An immutable historical version of a deck list and any versioned deck properties. Games should be associated with the revision that was used when the game was played so later edits do not change historical context.

### Deck Entry

A card and its quantity within a particular deck revision. A deck entry may also hold deck-specific information such as tags or ownership status if those properties are intended to vary by revision.

### Commander

A card designated as the leader of a Commander deck. A deck may have more than one commander when allowed by the rules, such as with Partner or a Background.

### Color Identity

The Commander-format color classification of a card or deck, conventionally represented with the codes W, U, B, R, and G. Colorless may be represented as C where appropriate.

### Card

A Magic card as players generally understand it, independent of a particular physical copy. When exact identity matters, use **Oracle Card** or **Card Printing**.

### Oracle Card

Scryfall's shared identity for printings that represent the same underlying Magic card and Oracle rules object. It is identified by a Scryfall `oracle_id`.

### Card Printing

A specific printed version of a card, identified by a Scryfall `id` and typically associated with a set and collector number. Artwork and card images belong to a printing.

### Card Cache

Card data temporarily stored by Cluestone so deck lists and images can remain usable and load quickly without repeatedly requesting the same information from Scryfall.

### Tag

A user-assigned label used to organize or describe decks or deck entries, such as owned, wanted, proxy, ramp, or removal. Tags are descriptive and do not change game rules.

### Note

User-entered text that records an observation about a deck, card within a deck, deck revision, or game. The subject and historical scope of a note should always be identifiable.

### Bracket Level

A stated estimate or classification of a deck's expected play environment or power under the Commander bracket system. Because definitions may change, its source and date may need to be preserved.

## Games and Turn Structure

### Game

A single Commander match involving two or more game participants. It begins after participants and decks are selected and ends as completed, drawn, or abandoned.

### Game State

The complete set of values Cluestone currently tracks for an in-progress game, including the active player, turn position, life totals, commander damage, counters, and participant status.

### Starting Life

The life total assigned to each participant when a game begins. The default for an ordinary Commander game is 40, but users may select a different starting life value.

### Turn

One participant's tracked turn. An extra turn is a distinct turn even when the same participant takes multiple consecutive turns.

### Turn Order

The ordered sequence in which participants normally become the active player. Eliminated participants are skipped without being removed from the game record. Turns typically progress in clockwise fashion.

### Round

A tracker-level grouping representing one expected pass through the current turn order. Extra turns and eliminated players may cause a round to contain something other than exactly one turn for every original participant. A round begins with the starting player and ends after the turn of the player immediately counterclockwise from them.

### Extra Turn

An additional turn taken by a participant before normal turn order resumes. It does not automatically advance the active player to the next seat.

### Life Total

A participant's current life. Life may fall below zero because the tracker records the entered value rather than acting as a comprehensive rules engine. Sometimes game actions and card effects can cause a player to have a life total less than zero without losing the game (such as Platinum Angel).

### Counter

A numeric player-state value tracked in addition to life, such as poison counters, experience counters, and energy counters. This is distinct from a counter placed on a permanent in the game, which Cluestone does not currently track.

### Poison Counter

A counter received by a participant that may cause that participant to lose under the rules of the game.

### Experience Counter

A player-specific counter which is tracked for the purposes of resolving certain card effects, such as Azlask, the Swelling Scourge.

### Energy Counter

A non-mana resource type which is accrued by card effects and can be spent for various card abilities.

### Commander Damage

Combat damage a participant has received from a particular opposing commander over the course of a game. It begins at zero and is tracked separately for each commander source. Receiving 21 commander damage from any single commander causes that participant to lose.

### Commander-Damage Synchronization

A tracker setting, enabled by default, that applies commander-damage adjustments to life as well. Increasing commander damage reduces life by the same amount and vice-versa; correcting commander damage applies the corresponding life correction. When disabled, the values are managed independently.

### Elimination

The transition of a participant from active in the game to having lost, conceded, or otherwise left it. Eliminations are entered one participant at a time.

### Concession

A participant voluntarily leaving and losing the game.

### Alternate Win Condition

A card or game effect that causes a participant to win without first eliminating every opponent. Cluestone allows the table to declare that participant the winner directly.

### Completed Game

A game that ended with exactly one winner. Completed games contribute to applicable performance statistics.

### Drawn Game

A game that ended without a winner and was intentionally recorded as a draw. Drawn games are retained in history but excluded from performance statistics for now.

### Abandoned Game

A game that stopped without a result and will not be resumed. Abandoned games are retained in history but excluded from performance statistics for now.

### Paused Game

An in-progress game saved with the intention of resuming it later. It has not yet produced a result.

## History and Corrections

### Tracked Value

Any piece of game state recorded by Cluestone, such as life, poison, commander damage, active player, or elimination status. Physical game actions not entered into Cluestone are not tracked values.

### Game Event

A recorded change to game state, such as adjusting life, passing the turn, or eliminating a participant. Events may be used to support history, recovery, and analysis.

### Snapshot

The tracked game state as it existed at a particular point, commonly at a turn boundary. A snapshot can be displayed or restored during rewind.

### Previous Turn

An undo-style action that returns to the preceding turn, restores its active player and turn position, and restores all tracked values to their state at that point.

### Rewind

An action that lets players review an earlier turn or round and restore its tracked state. Rewind helps correct entered values after a missed effect or rules mistake; it does not reconstruct physical actions that Cluestone did not record.

### Life Adjustment

A change to a player’s tracked life total. Consecutive inputs may be grouped temporarily to show the net adjustment, such as −17, regardless of how many taps or holds were used. A life adjustment records the change in the tracked total but does not attempt to identify individual damage, life-loss, or life-gain events.

## Data and Integration

### Scryfall

An external Magic card-data service used by Cluestone to identify cards and retrieve card details and images. Scryfall data supplements Cluestone's own deck and gameplay data.

### Import

Creating or updating a Cluestone deck list from data produced elsewhere, such as a plain-text list or another deck-building service.

### Export

Producing deck or game data in a form that can be used outside Cluestone.

### Synchronization

The process of reconciling Cluestone data between a local device and an online service or another device. Synchronization is an enhancement to, rather than a prerequisite for, core local use.

### Reference ID

An identifier used to associate one Cluestone record with another. Documents should name the specific identifier when possible, such as `deck_id`, `profile_id`, Scryfall `id`, or Scryfall `oracle_id`, rather than relying on the generic term.

### Performance Statistics

Calculated summaries based on eligible completed games, such as games played, wins, losses, and win rate. Drawn and abandoned games are excluded unless a future decision changes that policy.

### Card-Level Performance

Evidence about how a card performs within a particular deck or revision. It must be based on explicitly recorded observations or events and should not be inferred solely from a card's presence in a winning or losing deck.