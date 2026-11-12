# Battlefield Forge

A community map editor for War of Rights. Until 11 November 2026 it was called the WOR Piece Editor; same program, new name.

**Work in progress.** This editor is being built and refined as we go, with new builds most days. Expect rough edges, and expect things to change between builds. If something is wrong, say so: what you did, what happened, and the `diagnostics.txt` file (see below), and it gets fixed in the next build. Maps you make keep working; a new build opens your old saves.

## Download

**Standalone edition (recommended, 115 MB zip):** open [Releases](../../releases/tag/v2PR) and click `BattlefieldForge.zip`.
Unzip it anywhere you can write to, such as your Desktop or Documents, and run `BattlefieldForge.exe` from the unzipped folder.
It carries everything it needs and does not look for the game to start.

**Small edition (1.6 MB):** click **BattlefieldForge (small).exe** in the file list above, then the download button
(the small down-arrow on the right). It builds its files from your own game on the first start, so it has to find the game.

**Why a zip:** on 11 November Windows Defender started calling the old one-file download a virus. That was a wrong guess
by its machine-learning model, which saw a program unpacking files from inside itself, the way a virus installer does.
The zip has no such step. If your antivirus still objects to the editor, it is wrong, and a report of what it said helps.

## What's new (12 November 2026)

- **Fixed: the editor would not start on AMD and Intel graphics cards.** It stopped with
  `ERROR: 0:35: 'patch' : syntax error`. One word in the ground shader was a name those drivers
  reserve; NVIDIA's driver had let it through, so it never showed here. Every shader is now checked
  against the whole GLSL keyword list before a build goes out. If a driver ever refuses a shader again,
  the editor now says so plainly, names the card, and writes `shader_log.txt` beside `diagnostics.txt`.
- **Roads are now real roads.** The Road tool lays nodes: click along the way the road goes and it curves
  smoothly through every node, as wide as the brush was when you started. Enter finishes it. Drag a node to
  bend the road, Delete removes the node under the cursor, click an end node to carry the road on. Right-click
  a road for its width, its surface (dirt road, forest track, double track), a node where you point, or to
  take it away. The ground is graded flat across the road and even along it as you go, and one Ctrl+Z takes
  back the node and the ground together. On export every road is written as the game's own road mesh,
  so in the game it is a proper dirt road with its texture, not only a strip of ground paint.
- **Towns and farms.** On the Objects tab, pick a mix (village street, farm lane, hamlet, or one farmstead)
  and drag along a street: houses stand along both sides with fenced fronts and outbuildings behind; a farm
  lane puts whole farmsteads with barns, spring houses, corn cribs, hay and a fenced yard every 120 m. A short
  drag puts one farmstead where you pressed. Right-click a road and **Line this road with houses** does the
  same along its curve. The buildings are the game's own; a building's front is not known from its model,
  so each stands with its long side along the street, and the ring handle turns it.
- Typing in the object search box no longer trips the single-letter hot keys.
- **The download is now a zip, not a single exe.** Windows Defender's machine-learning model started calling the
  one-file build a virus on 11 November (a wrong guess: it saw a program unpacking files from inside itself). The zip
  has no such step. Unzip it, keep the files together, and run `BattlefieldForge.exe`. The first start builds the
  editor's level file beside it, once.

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
- **More plants**: standing wheat, three corn mixes, tall and withered grass, flowers, forest floor, hedgerow, big hardwoods and scattered rocks in the foliage brush.
- **Lay a corn field in rows** (Objects tab): drag a rectangle and it fills with corn patches on a grid, rows lined up, stalks round the edge. Strength sets how tight.
- Select tools: a press a few pixels from a unit or an object now picks it up, not only a press on the drawn figure.
- Artillery spawns show the gun with a crewman holding the sponge-rammer beside it.
- Spawn points wear their own badge: rings on the ground in the side's colour and INF, CAV or ART over the figure, and a ring with the same word on the map.
- Artillery base and staging points show the gun with its crewman; a battery's forward position shows the crewman with his rammer alone.
- A clean map now moves every Drill Camp fence, door and shutter to the map's far south-west corner instead of burying it, so nothing of the old map stands on yours.
- Artillery and cavalry no longer drop from the sky: the camps' unnamed spawn spots are now sat on the new ground and move with the camp.
- Upload now always sends the second map file (ground data, water, fences), not only when the map name changed.
- **Out of bounds on the ground**: everything outside the chosen mode's play zone is washed red with faint stripes, in both views. Every zone carries its name at its first corner.
- Right-click the ground, Camps and spawns, **Move the play zone here** puts the zone's middle on that spot.
- Units outside the play zone are ringed in red with the words OUTSIDE THE PLAY ZONE. The export warning lists them, selects them and puts the camera on the first; **Show me the units outside the play zone** in the ground menu does the same any time.
- The yellow square at the map's middle is labelled: it is the home mark and the map centre.
- Spawn spots are lifted to 1.2 m over the ground, and a final pass on every export makes sure no spawn spot is ever written under the map.
- **Tool panel** down the left edge of the view: every tool one click away, the live one lit.
- **Placing is a brush**: pick an object, click to set one, or hold the button and drag to lay a row. Brush size sets the spacing.
- **Fly camera**: WASD flies where you look, E or Space up, Q or C down, Shift fast, Ctrl slow. The pace grows with your height.
- **Finer sculpting**: the brush goes down to 1 m, strength is finer at the low end, Shift while sculpting is a heavy hand, and a Roughen tool adds small bumps and detail.
- **Fence tool**: drag from one end to the other and the panels are laid end to end; start the next run where the last ended to turn a corner.
- **Road tool**: click node after node and the road curves through them, graded flat across the brush width with blended shoulders, and surfaced. See the top of this list.

## To start

1. To make and play a map you need War of Rights installed through Steam.
2. Unzip the folder anywhere you can write to, for example your Desktop, keep its files together, and run `BattlefieldForge.exe`.
   (Small edition: put the exe anywhere and run it.)
3. Windows warns about an unknown publisher. Click **More info**, then **Run anyway**.
4. The first start takes under a minute while it prepares its level files. That happens once.
   The small edition takes them from your game.

If it cannot find the game on its own, it asks for the game folder. That is usually
`<a drive>:\SteamLibrary\steamapps\common\War of Rights`. In Steam you can find it with:
right-click War of Rights, Manage, Browse local files.

## If something goes wrong

Press `Win+R`, type `%APPDATA%\BattlefieldForge` and press Enter. Send the file
`diagnostics.txt` from that folder to whoever gave you this editor. If the editor said your
graphics driver refused a shader, send `shader_log.txt` from the same folder too.

## Good to know

- The editor never changes your game unless you press **Copy onto my game**.
  **Restore original** puts the game's own file back.
- Keys: `WASD` fly where you look, `E`/`Space` up, `Q`/`C` down, `Shift` fast, hold the right mouse button to look,
  `M` top-down map, `B` select objects, `U` select units, `V` select anything, `N` measuring pin, `Ctrl+Z` undo.
