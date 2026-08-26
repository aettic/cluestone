# API Calls

### GET /num_cards
Get the number of cards in the deck
Length of cards_list array

### GET /list_comparison
Compare two deck lists, such as two versions of the same deck, or two different decks with the same Commander. Create a qualitative. And quantitative difference between the two decks.

### CREATE /create_deck
Create a new deck object for the current player, requires at least a name
Overload:
- Name
- Commander
- Deck list

### DELETE /delete_deck
Delete a deck object from the user

### UPDATE /update_deck_list
input: 
- deck’s reference_id: STRING
- changes: JSON

```JSON
{
”add”: [”1234”, “4321”, “1122”],
“remove”: [“4444”, “3434”, “1213”]
}
```

### UPDATE /update_commander
input: new_commander: STRING (card’s reference_id)

---

## Scryfall

Documentation: https://scryfall.com/docs/api
`https://api.scryfall.com`
HTTPS only, TLS 1.2 or better
UTF-8 encoding

### Images
Scryfall card responses contain a JSON object called `image_uris` which has a variety of sizes for the images, and alternative formats such as just the artwork.

### Card Identifiers
Each submitted card identifier must be a JSON object with one or more of the keys id, mtgo_id, multiverse_id, oracle_id, illustration_id, name, set, and collector_number. (name,set must go together, same as collect_number,set).
Here, `id` is the one Cluestone will use.

### POST /cards/collection
https://scryfall.com/docs/api/cards/collection#card-identifiers
INPUT: JSON Array of up to 75 card identifiers per request.
RETURNS: List object (JSON)
USES:
- When retrieving not-cached cards when opening a deck list. Then cache the cards per the appropriate policy.

### GET /cards/:id
Make a call to the Scryfall API using the card’s id to retrieve info about it.
ex.
`GET https://api.scryfall.com/cards/8d7c1f6c-af45-4449-8cf8-e13830b3df8a`
RETURNS: JSON content of that card (see examples/valgavoth-harrower-of-souls.json)