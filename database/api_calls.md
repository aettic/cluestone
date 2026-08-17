### GET /card_info
Make a call to the Scryfall API using the card’s id to retrieve info about it
- Could be different based on whether we want the image or card content.

### GET /color_identity
Get the commander’s color identity and return it as an array of color codes (WUBRGC).
Input: commander’s card reference_id
Output: `CHAR[]`

### GET /mana_curve
Get the mana curve (JSON, broken down by mana value as the key and number of cards of that mana value as the value)

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

