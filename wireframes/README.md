# Wireframes

This folder will contain screenshots and information pertaining to them, relating to wireframes of the features in the app. Archived versions will not be deleted, but instead stored in an archive folder within here.

## Tracker
This is one of the core utilities of Cluestone. It needs to be accessible quickly when opening the app, and needs to be minimal by default, with options to tailor the experience based on needs and desires.

Should support between 2 and 6 players.

A button in the middle (accessible by all players) should allow for passing the turn with a quick press, or provide other functionality (a radial menu) when held down.

The radial menu should allow the following options:
- Home
- Previous Turn
- Rewind (X turns, or X rounds)
- Reset the game
- Settings

Previous Turn acts as an undo. It returns control to the previous active player and restores all tracked values to their state at that turn. Rewind allows players to review an earlier turn or round and choose whether to restore it.

Each player's section should contain their life total first and foremost, as well as their Commander Damage listed smaller underneath their life total. Number of commander damage indicators is number of players - 1.

Commander damage is synchronized with life by default, with an option in Settings to manage the two values independently. When synchronization is enabled, commander damage adjustments apply an inverse adjustment to life. Commander damage must remain separated by source because 21 damage from any single commander causes that player to lose.

Players must be able to increase or decrease their life total by 1 point each via a single tap on the screen in the relative position (to the right of their life total adds 1, to the left of their life total subtracts 1). A long-press on these same sections should instead adjust by 10, up or down.

Each player section should be color-coded, selected at random from a group of predefined good color choices, with the option to change to any custom color via sliders, a color picker, or hex entry.

Each player section should have the option of featuring an image from the game, based on what deck is selected.

Each player section should show the player's name and the deck's name.

An eliminated player remains visible, but their section should clearly show that they are no longer active and their turn is skipped. The game-ending menu should also allow players to record a draw or abandon the game; these outcomes are excluded from statistics for now.

## Deck List
The deck list page is entered after selecting a deck from the Home page. It contains three main sections: The header, the cards view, and the info pane.

The **header** is a banner which stretches all the way across the top of the page, and contains a hamburger menu button, as well as the Name and color identity of the deck on the left side of the header. The right side of the header shows the Bracket level of the deck. Clicking the name or bracket level allow these values to be changed. Clicking the menu button opens a sidebar menu.

The **cards view** is where you can see the entire deck at a glance. View options (adjustable in the menu) can show the cards in a text list, a solitaire-like stack view, or a grid of card images. After hovering or tapping on a card, it will be featured in the right-hand side info pane. The purpose of the cards view is to show each of the cards in the deck at a glance, and allow for sorting and filtering them (via the menu) for analysis' sake.

The **info pane** shows a larger image of the featured card (defaults to the Commander, but will change when the user taps on or hovers over a card). Underneath the card image, it shows some deck information, as well as access to notes for the card, and the Analysis interface for the deck. The deck information presented in the info pane are the Mana Cost breakdown, Mana Production breakdown, Mana Curve, and win:loss ratio.

## Home

The home page is the landing page that users will see when first opening Cluestone. It contains two main rows of options: Decks and Games. The left-most option in each of these rows is a button to create a new Deck or Game. 

The top left corner of the home page shows the Cluestone name and logo. The top right corner shows the user's profile icon. Clicking this icon opens a menu for profile options.

## Analysis

Similar to the Deck List page in that it contains a header with the menu, color identity, deck name, and bracket information; as well as an info pane with the commander card(s), tags, mana curve, mana cost and production breakdown, and win:loss ratio. The main section of the page, however, is the analysis view itself. It contains a timeline of nodes which can be clicked on to expand and see more information.

By default, the Analysis page will show summary lines for every event, chronologically. Selecting a Node from the timeline will navigate to that position and focus on only events from that node's date. Expanding a particular event will focus on that one.

### Nodes

**Deck Created**: Always the first node on the timeline, and shows the date that the deck was first created in Cluestone. 

**Revisions**:
- Numbered chronologically
- Shows the changes made to the deck (changes to the 99, change to the commander, imports, etc.)
- Selecting the node shows the complete revision diff (between itself and the previous version)
- Even if multiple changes happened on a given date, they are grouped into the same node and revision diff, unless a game takes place in between them. e.g. I made a few swaps to my deck, then play a couple matches, and then decide to make a few more swaps. In this case, there would be three nodes: The first revision, the games (combined into one node), and the second revision.

**Games**: Games are tracked on a date-basis, rather than as their each individual nodes. Clicking on a node with game wins/losses will show information for each game that took place on that date, and a link to the Game view.

**Milestones**: Cluestone could calculate factual milestones without implying that they prove anything. e.g.
- First recorded game
- First win
- 10th, 25th, or 100th game
- Longest game
- Shortest game
- Best recorded win streak
- One-year deck anniversary

**Notes**: Notes can be placed directly on the timeline, capturing dates and user-entered text. 

When expanding a Node, each item that is part of that date will be available. If there is only one, it will be fully expanded by default. If there is more than event in a given date (node), a summary for each will be listed, along with any notes.