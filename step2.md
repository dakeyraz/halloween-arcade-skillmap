# Gravity & Jumping

## Step 1: Left and Right Movement
In your `on start` container, go to **Controller** and drag `move mySprite with buttons vx [100] vy [0]`. Change `vy` to `0` so players can't float up and down.

```blocks
controller.moveSprite(mySprite, 100, 0)
```

## Step 2: Add Gravity
Go to **Sprites** and drag `set mySprite vx to 0` into `on start`. Change `vx` to `ay` (Acceleration Y) and set it to `400` to pull your character down.

```blocks
mySprite.ay = 400
```

## Step 3: Jump on A Button Press
Grab an `on controller A button pressed` event from **Controller**. Inside it, add a **Logic** `if` block checking if `mySprite` is hitting the wall on the bottom. If true, set `vy` to `-180` to jump!

```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    if (mySprite.isHitting(CollisionDirection.Bottom)) {
        mySprite.vy = -180
    }
})
```