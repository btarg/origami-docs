---
description: >-
  The "events" section of a block or item's YAML allows you to execute Minecraft
  commands when certain interactions are performed.
cover: >-
  https://images.unsplash.com/photo-1501281668745-f7f57925c3b4?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxldmVudHxlbnwwfHx8fDE3MDE5Nzg1ODd8MA&ixlib=rb-4.0.3&q=85
coverY: 0
---

# 📣 Events

{% hint style="info" %}
Both blocks and items use some events by the same name, with them behaving differently depending on the context: for example, `onBroken` is used for both when a block is broken and for when an item breaks as a result of running out of durability.
{% endhint %}

```yaml
# "events" is formatted as a list of event objects:
events:
  - onRightClick: # <-- event name
      commands:
        - say block right clicked!
      cooldown: 20 # <-- cooldown in ticks
  - onBroken:
      commands:
      # this is a list of Minecraft commands, with or without the slash
        - say block broken!
        - say goodbye world!
      # adding a cooldown is optional
```

## List of event names

1. `onRightClick`:
   * **Function:** Triggered when a block or item is right-clicked.
2. `onLeftClick`:
   * **Function:** Triggered when a block or item is left-clicked.
3. `onRightClickAir`:
   * **Function:** Triggered when an item is right-clicked while looking at air.
4. `onLeftClickAir`:
   * **Function:** Triggered when an item or block is left-clicked while looking at air.
5. `onRightClickBlock`:
   * **Function:** Triggered when the player is looking at a block and a right-click is performed.
6. `onLeftClickBlock`:
   * **Function:** Triggered when the player is looking at a block and a left-click is performed.
7. `onPlaced`:
   * **Function:** Triggered when a block is placed.
8. `onBroken`:
   * **Function:** Triggered when a block or item is broken.
9. `onDamaged`:
   * **Function:** Triggered when an item or block is damaged.
10. `onPushed`:
    * **Function:** Triggered when a block is pushed by a piston.
