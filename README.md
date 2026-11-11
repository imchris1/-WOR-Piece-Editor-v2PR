# Battlefield Forge

A community map editor for War of Rights. Until 11 November 2026 it was called the WOR Piece Editor; same program, new name.

## Download

**Standalone edition (recommended, 110 MB):** open [Releases](../../releases/tag/v2PR) and click `BattlefieldForge.exe`.
It carries everything it needs and does not look for the game to start.

**Small edition (1.6 MB):** click **BattlefieldForge (small).exe** in the file list above, then the download button
(the small down-arrow on the right). It builds its files from your own game on the first start, so it has to find the game.

## What's new (11 November 2026)

- **New name: Battlefield Forge.** Your settings, autosaves and backups from the WOR Piece Editor move over on the first start.

- **Play zones are drawn.** Every zone of the chosen game mode shows as a fence: yellow for the play zone,
  red and blue for the ground each side may not enter, orange for capture areas, tent colours for staging areas.
- **Zones are fixed on export.** A zone used to keep its original height range, so a map with high ground
  put every player "out of the playable zone". Export now sits every zone under its ground.
- **Zones can be reshaped.** Each corner carries a solid node. In Select units, drag a node to move that
  corner, pull the white square to stretch the zone, or press `-` and `=`. Right-click a fence for
  **Fit this play zone round the units**, **Resize this zone**, and **Put this zone back**.
- The export warns when a unit of the mode stands outside its play zone.
- **Select anything** (key `V`): one tool that picks zone nodes, units, and objects together, so a node is one press and a drag away.
- **Clear map**: a toolbar switch for a top-down map with only the ground, the zones and the units on it.
- **Place a unit here**: right-click the ground, Camps and spawns, pick a unit by name, and it moves to that spot.
- Settings from the old name move over on the first start, and the old folder name keeps working for older copies.

## To start

1. To make and play a map you need War of Rights installed through Steam.
2. Put the exe anywhere, for example on your Desktop, and run it.
3. Windows warns about an unknown publisher. Click **More info**, then **Run anyway**.
4. The first start takes a few seconds while it prepares its files from your game.

If it cannot find the game on its own, it asks for the game folder. That is usually
`<a drive>:\SteamLibrary\steamapps\common\War of Rights`. In Steam you can find it with:
right-click War of Rights, Manage, Browse local files.

## If something goes wrong

Press `Win+R`, type `%APPDATA%\BattlefieldForge` and press Enter. Send the file
`diagnostics.txt` from that folder to whoever gave you this editor.

## Good to know

- The editor never changes your game unless you press **Copy onto my game**.
  **Restore original** puts the game's own file back.
- Keys: `WASD` move, hold the right mouse button to look, `M` top-down map,
  `B` select objects, `U` select units, `V` select anything, `N` measuring pin, `Ctrl+Z` undo.
