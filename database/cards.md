Scryfall URL Format:

```
https://scryfall.com/card/dsc/6/valgavoth-harrower-of-souls
```

`https://`
`scryfall.com/`
`card`: object
`dsc`: set
`6`: collector_number
`valgavoth-harrower-of-souls`: title, HTTP-safe

Query strings are potentially added to the end.

Using the card's scryfall ID instead of a huamn readable identifier:
```
https://scryfall.com/card/8d7c1f6c-af45-4449-8cf8-e13830b3df8a
```

Scryfall already provides a ton of information about cards individually, which are accessible via their API. Cluestone should not store all of this information redundantly. Instead, it should store only simple accessors (such as the scryfall ID for the card) and potentially other simple identifiers like the card's face information (name, mana value, typeline, set, collector number, description, power/toughness, etc.)

For example:

```
Valgavoth, Harrower of Souls {2}{B}{R}
Legendary Creature — Elder Demon
Flying
Ward—Pay 2 life.
Whenever an opponent loses life for the first time during each of their turns, put a +1/+1 counter on Valgavoth and draw a card.
4/4
DSC 0006
```

Most of this information is directly retrievable from Scryfall's "copy-pasteable text" option, though the set and collector_number are not present there. These are likely important to store in Cluestone for the sake of rendering the correct card images on the deck list. It could also just use the ID of the card itself.

## Data Model

```
card_id: REQUIRED UUID
scryfall_id: REQUIRED STRING
name: REQUIRED STRING
set: REQUIRED STRING
collector_number: REQUIRED STRING
```

Information that is needed for the cards to be displayed or accessed in the Deck list / Analysis sections will be pulled from Scryfall and cached based on the appropriate caching policy.