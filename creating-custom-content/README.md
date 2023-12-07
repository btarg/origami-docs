---
description: >-
  Custom content in Origami is written in YAML, and can be reloaded with
  subcommands of the "/oc" command in-game.
cover: >-
  https://images.unsplash.com/photo-1621360841013-c7683c659ec6?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxtaW5lY3JhZnR8ZW58MHx8fHwxNjk1NzQyMjA4fDA&ixlib=rb-4.0.3&q=85
coverY: 0
---

# ✍ Creating Custom Content

{% hint style="info" %}
## Learn about the YAML format [here](https://learnxinyminutes.com/docs/yaml/)!
{% endhint %}

## Model data

{% hint style="info" %}
Both blocks and items can have custom models defined. Here's how:
{% endhint %}

Block textures are stored at `<server folder>/plugins/Origami/custom/MY-CONTENT-PACK-NAME/textures/block/<texture name>.png` and will be automatically added to the generated resource pack. For items, replace "block" here with "item".

In a custom block's YAML file, a `model` field with the value of `rainbow` would point to: `<server folder>/plugins/Origami/custom/MY-CONTENT-PACK-NAME/models/block/rainbow.json`. Again, replace "block" with "item" fo the equivalent folder for custom item models.

## JSON Models

{% hint style="info" %}
For more information on models, see the [Minecraft Wiki](https://minecraft.wiki/w/Tutorials/Models).
{% endhint %}

Below is an example of a simple custom block using the texture `mosaic` on all sides.

```json
{
    "parent": "minecraft:block/cube_all",
    "textures": {
        "all": "origami:block/mosaic"
    }
}
```
