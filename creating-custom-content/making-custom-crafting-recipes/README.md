---
description: >-
  Crafting recipes can use both regular items and custom items as ingredients or
  results.
cover: >-
  https://www.minecraft.net/content/dam/archive/fe24093c7f2572ac93d500fa95798f5d-header.jpg
coverY: 0
---

# 🛠 Making Custom Crafting Recipes

Custom recipe definitions go into `plugins/Origami/custom/MY-CONTENT-PACK-NAME/recipes`. If this directory is empty, then Origami will generate an example file for you.

Below is an example of a crafting recipe where surrounding a "Rainbow Block" (see the [Custom Blocks](../making-custom-blocks.md) page for details) with 8 diamonds results in a custom item, in this case `enchanced_rainbow_block`, being created.

&#x20;Notably both an ingredient and the result here are Blocks - Blocks can be used just like any other item and the player will receive the item form of said Block.

<pre class="language-yaml"><code class="lang-yaml"><strong>result: origami:enhanced_rainbow_block
</strong>shape:
- ddd
- drd
- ddd
ingredients:
- d;DIAMOND
- r;origami:rainbow_block
</code></pre>

## Ingredients in a shaped recipe

Ingredients are defined as a one-character "key" and an [item string](../../item-strings.md). The "key" is used to determine the `shape` of the recipe.

<table data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td></td><td><a data-footnote-ref href="#user-content-fn-1">d</a></td><td></td></tr><tr><td></td><td>d</td><td></td></tr><tr><td></td><td>d</td><td></td></tr><tr><td></td><td>d</td><td></td></tr><tr><td></td><td>r</td><td></td></tr><tr><td></td><td>d</td><td></td></tr><tr><td></td><td>d</td><td></td></tr><tr><td></td><td>d</td><td></td></tr><tr><td></td><td>d</td><td></td></tr></tbody></table>

In this example, we replace `d` with a `DIAMOND` and `r` with a `rainbow_block`.

## Ingredients in a shapeless recipe

When `shape` is set to `null`, only the ingredients matter. A key does not need to be specified for each ingredient when the recipe is shapeless:

```yaml
  result: origami:enhanced_rainbow_block
  shape: null
  ingredients:
  - DIAMOND
  - origami:rainbow_block
```

In this example, only one diamond and one Rainbow Block are needed to craft the item.

{% hint style="info" %}
This page is about the Crafting Table. For further information about other types of recipes, see the page "[Crafting Recipe Types](crafting-recipe-types.md)".
{% endhint %}

[^1]: 
