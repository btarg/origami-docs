---
description: Origami generates a resource pack and hosts it using an internal HTTP server.
cover: >-
  https://images.unsplash.com/photo-1635336969656-0e63e076904f?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw1fHxtaW5lY3JhZnR8ZW58MHx8fHwxNzAwNDQwMjU5fDA&ixlib=rb-4.0.3&q=85
coverY: 0
---

# 🎮 Setup

```yaml
resource-pack:
  http-port: 8008
  pack-description: Powered by <color:#f51d5e>Origami</color>
```

You will need to port forward whichever port you set `http-port` to.

The `pack-description` is shown when the player opens their Resource Packs menu.

## Folder structure

{% hint style="info" %}
I have filled this in with placeholder content. Refer to this when [Creating Custom Content](creating-custom-content/).
{% endhint %}

Here we are creating a Content Pack called "EXAMPLE-NAME". A content pack can have any name, it is just a way of organising your custom content. Content Packs go under the `custom` folder.

```
Origami
|-- custom
|   |-- EXAMPLE-NAME
|       |-- textures
|       |   |-- block
|       |   |   |-- rainbow_block.png
|       |   |
|       |   |-- item
|       |       |-- rainbow_sword.png
|       |
|       |-- models
|       |   |-- block
|       |   |   |-- rainbow_block.json
|       |   |
|       |   |-- item
|       |       |-- rainbow_sword.json
|       |
|       |-- recipes
|       |   |-- rainbow_block_recipe.yml
|       |
|       |-- blocks
|       |   |-- rainbow_block.yml
|       |
|       |-- items
|           |-- rainbow_sword.yml
```
