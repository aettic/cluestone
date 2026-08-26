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

## Deck Lists
