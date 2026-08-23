A Deck refers to the deck of cards a player is competing with in the game.

It can be identified as either a chosen nickname (such as "Amy's Green Deck"); or by a single Commander card object (such as "Ashaya, Soul of the Wild") which links to that card object in the database; or a complete deck list, using the commander's name as the deck's name. All decks must have at least a name.

A Deck belongs to a Player.

Will probably need one table to store historical versions of the decks, and one table for the most current version.

```
deck_id: REQUIRED UUID
player_id: REQUIRED UUID
name: REQUIRED STRING (64 character limit)
featured_image: STRING (URL to Scryfall image or Scryfall card uuid)
bracket_level: INTEGER (1 - 5)
cards_list: REPEATED STRING / STRING[] (reference_ids in an array)
commander: STRING (reference_id for card)
notes: STRING[] (References to Notes objects)
wins: INTEGER
losses: INTEGER
version: INTEGER
update_timestamp: TIMESTAMP

```