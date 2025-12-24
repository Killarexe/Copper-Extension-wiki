+++
date = '2025-12-15T19:50:39+01:00'
draft = false
title = 'Add Lightning Effect'
type = "docs"
next = "datapacks/add_oxidation_transformation"
weight = 30
+++

> [!CAUTION]
> The datapacks are only supported to versions superior or equal to 1.5.0

## Creating the file

Lightning effect is the most *"complicated"* to implement. Before doing this, if you need more info on this feature see the **[Lightning Effects Mechanic](../../mechanics/lightning_effects)**. First you need to create a `lightning_effect` folder in your namespace folder. Then create a simple `.json` file like your creating a custom recipe.

The structure should looks like this:

{{< filetree/container >}}
  {{< filetree/folder name="example_datapack" >}}
    {{< filetree/file name="pack.mcmeta" >}}
    {{< filetree/file name="pack.png" >}}
    {{< filetree/folder name="data" state="open" >}}
        {{< filetree/folder name="example_datapack" state="open" >}}
            {{< filetree/folder name="lightning_effect" state="open" >}}
                {{< filetree/file name="example.json" >}}
            {{< /filetree/folder >}}
        {{< /filetree/folder >}}
    {{< /filetree/folder >}}
  {{< /filetree/folder >}}
{{< /filetree/container >}}

## The data format

A Lightning Effect json file looks like this:

```json{filename="data/example_datapack/lightning_effect/example.json"}
{
  "effect": {
    "amplifier": 1,
    "duration": 480,
    "id": "<namespace>:<effect_id>",
    "show_icon": true
  },
  "item": "<namespace>:<armor_item_id>"
}
```
| property | description | optional |
| -------- | ----------- | -------- |
| `effect` | The effect applied to the armor item. | no |
| `item`   | The target armor item to trigger the effect. | no |
| `replace`| If you want to overide an already existing waxing transformation (use it with caution) | yes |

If you want more details for the `effect` property, check [this Minecraft Wiki page](https://minecraft.wiki/w/Data_component_format/potion_contents).

Here's an example of a lightning effect that apply an effect of Haste II form a Waxed Copper Chestplate.

```json{filename="data/copper_extension/lightning_effect/waxed_copper_chestplate.json"}
{
  "effect": {
    "amplifier": 1,
    "duration": 480,
    "id": "minecraft:haste",
    "show_icon": true
  },
  "item": "copper_extension:waxed_copper_chestplate"
}
```
