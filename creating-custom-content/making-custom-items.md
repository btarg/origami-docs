---
description: Custom items are defined in the same way as blocks and recipes.
---

# 💎 Making Custom Items

{% hint style="info" %}
[Item Flags](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/inventory/ItemFlag.html) can be defined with their name, and are not case-sensitive
{% endhint %}

```yaml
baseItem: DIAMOND_SWORD
rightClickCommands:
- tellraw @s {"text":"Your sword glimmers with power.","italic":true,"color":"gray"}
leftClickCommands:
- tellraw @s {"text":"You swing your sword with extra power!","italic":true,"color":"gray"}
leftClickCooldown: 20 # 20 ticks = second
rightClickCooldown: 100
lore:
- <rainbow>Test item</rainbow>
displayName: Test Sword
enchantments:
- damage_all(5) # legacy Bukkit enchantment name
- unbreaking(3) # Minecraft enchantment name
- binding_curse # level 1 enchant
flags:
- hide_attributes
```
