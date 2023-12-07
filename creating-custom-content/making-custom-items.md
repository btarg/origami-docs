---
description: >-
  Custom items are defined in the same way as blocks and recipes. See the
  "Making Custom Blocks" page for more information on what these fields do.
---

# 💎 Making Custom Items

{% hint style="info" %}
[Item Flags](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/inventory/ItemFlag.html) can be defined with their name, and are not case-sensitive.
{% endhint %}

```yaml
baseItem: DIAMOND_SWORD
lore:
- <rainbow>Test item</rainbow>
displayName: Test Sword
enchantments:
- damage_all(5) # legacy Bukkit enchantment name
- unbreaking(3) # Minecraft enchantment name
- binding_curse # level 1 enchant
flags:
- hide_attributes
events:
  - onRightClick:
      commands:
        - say hello world
      cooldown: 20
  - onDamaged:
      commands:
        - say ouch!
  - onBroken:
      commands:
        - say goodbye world!
```
