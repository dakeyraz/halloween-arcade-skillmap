# Candy & Win Conditions

## Step 1: Paint Your Tilemap
In `on start`, click **Scene** ➔ `set tilemap to`. Paint your platforms, green slime pits at the bottom, candy collectibles, and a finish door. Make sure to turn on the **Wall** tool for solid blocks!

```blocks
scene.setTilemap(tilemap`level1`)
```

## Step 2: Collect Candy for Points
Go to **Scene** and drag `on sprite of kind Player overlaps tile [candy]`. Inside, make the candy disappear (`set tile to transparency`), add 1 to the score, and play a sound!

```blocks
scene.onOverlap(TileKind.Candy, spritekind.Player, function (sprite, location) {
    scene.setTileAt(location, assets.tile`transparency`)
    info.changeScoreBy(1)
    music.baDing.playUntilDone()
})
```

## Step 3: Win & Lose Conditions
Add two more overlap blocks: one for the green slime pit (`game over LOSE`) and one for the finish door (`game over WIN`).

```blocks
scene.onOverlap(TileKind.Slime, spritekind.Player, function (sprite, location) {
    game.gameOver(false)
})
scene.onOverlap(TileKind.Door, spritekind.Player, function (sprite, location) {
    game.gameOver(true)
})
```