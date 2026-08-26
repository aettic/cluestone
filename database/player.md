A Profile is a reusable person or device identityreferencedon the database which contains a list of decks, and a player's name.

Guest Player
A guest player can have a list of decks, but these decks are limited to the Commander or a nickname, and cannot contain a deck list. It can still track wins and losses for those decks.

```
player_id: UUID
decks: STRING[] (list of deck_ids)
username: STRING
profile_icon: STRING (URL to stored image)
update_timestamp: TIMESTAMP
```