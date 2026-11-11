# Spooky Player

## Step 1: Set the Night Sky
Open the **Scene** drawer and drag `set background color to` into `on start`. Pick a spooky dark purple!

```blocks
scene.setBackgroundColor(11)
```

## Step 2: Draw Your Character
Open **Sprites**, drag `set mySprite to sprite of kind Player` into `on start`, and draw a ghost, witch, or pumpkin!

```blocks
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . .
    . . . . . . 1 1 1 1 . . . . . .
    . . . . . 1 1 1 1 1 1 . . . . .
    . . . . 1 1 f 1 1 f 1 1 . . . .
    . . . . 1 1 1 1 1 1 1 1 . . . .
    . . . . 1 1 1 f f 1 1 1 . . . .
    . . . . 1 1 1 1 1 1 1 1 . . . .
    . . . . 1 . 1 1 . 1 1 . . . . .
`, SpriteKind.Player)
```