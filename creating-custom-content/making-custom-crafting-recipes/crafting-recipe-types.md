---
description: >-
  So far, we've gone through how to create recipes that use the Crafting Table,
  but there are other types of crafting in the game. Other than the crafting
  table, no other recipe types use a shape.
---

# 🧑🍳 Crafting Recipe Types

{% hint style="info" %}
Results and ingredients both use [Item Strings](../../item-strings.md).
{% endhint %}

The following recipe uses the type `BLASTING` ([Blast Furnace](https://minecraft.fandom.com/wiki/Blast\_Furnace))

```yaml
result: ACACIA_BOAT(1)
ingredients:
- d;DIAMOND
- r;origami:rainbow_block
type: BLASTING
cookingTime: 40
experience: 69
```

## Ingredients

Ingredients do not require keys unless your recipe is a shapeless crafting recipe, but they can still have them, so if you accidentally add one don't worry.

When the type is set to `SMITHING`, the ingredients specified top-to-bottom in the YAML file are read left-to-right in the [Smithing Table](https://minecraft.fandom.com/wiki/Smithing\_Table).

For recipe types that only use one ingredient (cooking and stonecutting), each ingredient will be treated like a separate recipe. In the case of the example above, the player could put **either** a diamond **or** a "Rainbow Block" custom item into a Blast Furnace and receive an Acacia Boat. Both recipes have the same cooking time and XP output.

## Results

For `STONECUTTING` recipes, multiple results can be defined, by using a comma (`,`) with the `result` field, for example `ACACIA_BOAT, OAK_BOAT` as a result would allow any of the ingredients to be put into a stonecutter and turned into either an acacia boat or oak boat.

## Optional parameters

`cookingTime` and `experience` are only relevant for cooking-based recipes. Campfires do not give XP. The default cooking time is 20 ticks, which applies to all types of cooking.

## The `type` field

Any one of the following types can be used:

* `CRAFTING` **(DEFAULT)**
* `SMELTING`
* `BLASTING`
* `SMITHING`
* `CAMPFIRE_COOKING`
* `SMOKING`
* `STONECUTTING`

