---
description: >-
  Custom Block Definitions determine the properties of a block, including its
  custom model data.
cover: https://playhive.com/content/images/size/w1600/2022/11/Block4.jpg
coverY: 0
layout:
  cover:
    visible: true
    size: full
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# ⛏ Making Custom Blocks

## Creating Custom Blocks

Custom block definitions go into `plugins/Origami/custom/MY-CONTENT-PACK-NAME/blocks` If this directory is empty, then Origami will generate an example file for you. Below is a working example of a custom block, `rainbow_block.yml`:

```yml
baseBlock: GLASS
displayName: '&cR&6a&ei&an&9b&bo&5w &6B&el&ao&9c&bk'
lore:
  - <rainbow>It shimmers beautifully in the sunlight.</rainbow>
canBeMinedWith:
  - pickaxes
timeToBreak: 40
toolLevelRequired: 2
drops:
  - DIAMOND(1)
dropLootTable: null
canBePushed: true
isAffectedByFortune: true
placeSound: BLOCK_AMETHYST_BLOCK_PLACE
breakSound: BLOCK_AMETHYST_BLOCK_BREAK
model: rainbow

events:
  - onRightClick: # <-- onRightClick is an event, see the events page for more info
      commands:
        # this is a list of Minecraft commands, executed as @s
        - tellraw @s {"text":"The block reverberates majestically.","italic":true,"color":"gray"}
      cooldown: 20 # <-- cooldown of 20 ticks (1 second)
```

* **(**[**Material**](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Material.html)**)** `baseBlock` - determines what block goes beneath the custom model displayed via an item frame. `GLASS` typically works the best, but using `SPAWNER` works too.
* **(Integer)** `dropExperience` is how much XP should be dropped when the block is mined. XP can only be gained from a block if using the correct tool.
* **(Formatted string)** `displayName` - can use either legacy formatting codes (`§` or `&`, but _not both at once_) or [MiniMessage.](https://docs.advntr.dev/minimessage/format.html) You can also use a language string, and set the item's name in your resource pack's lang file instead - formatting included.
* **(List of formatted strings)** `lore` - lore to display on the custom item. Each entry uses the same formatting rules as the `displayName`.
* **(List of tools)** `canBeMinedWith` - multiple "preferred tools" can be set here, with valid tool types being: `pickaxes`, `axes`, `shovels`, `hoes`, and `swords`. A block can only be broken quickly or drop its items if one of the correct tools is used. Usually blocks in Minecraft only set one of these.
* **(Integer)** `toolLevelRequired` - specifies the minimum tool level allowed for mining the block. Wooden tools are level 1, Stone are level 2, etc.
* **(**L**ist of** [**Item Strings**](../item-strings.md)**)** `drops` - If both this and `dropLootTable` are `null`, the block will drop itself. Can optionally be followed by a semicolon and then a 0-1 "chance" value which determines the chance that particular item has of dropping (otherwise the item will always drop)
* **(**[**Loot Table**](https://minecraft.fandom.com/wiki/Loot\_table)**)** `dropLootTable` - if both this and `drops` are null, the block will drop itself. You can use this to specify a loot table for the block to drop.

{% hint style="info" %}
If both `drops` and `dropLootTable` are set, the result will be the items from the loot table plus whatever drops you specified.
{% endhint %}

* **(Boolean)** `canBePushed` - if true, the block can be moved by Pistons and Sticky Pistons.
* **(Boolean)** `isAffectedByFortune` - if true, the Fortune enchantment will apply a multiplier to the amount of each dropped item. Useful when creating ores.
* **(**[**Sound**](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Sound.html)**)** `placeSound` / `breakSound` - self explanatory

### Model data

{% hint style="info" %}
See [this page](./) for a guide on how models work.
{% endhint %}

* **(String)** `model` - the name of the custom model. A value of `rainbow` here would point to `<server folder>/plugins/Origami/custom/MY-CONTENT-PACK-NAME/models/block/rainbow.json`

