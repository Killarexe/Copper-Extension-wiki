+++
date = '2025-12-15T19:50:13+01:00'
draft = false
title = 'Add Oxidation Transformation'
type = "docs"
next = "datapacks/add_waxing_transformation"
weight = 10
+++

> [!CAUTION]
> The datapacks are only supported to versions superior or equal to 1.5.0

## Creating the file

Oxidiation transformation is pretty simple to implement. Also **if you add an oxidation for an item to an other, than the oxidized item can be scraped to the unoxidized item.** *(See the [Scraping Mechanic](../../mechanics/scraping))* First you need to create a `oxidation_transformation` folder in your namespace folder. Then create a simple `.json` file like your creating a custom recipe.

The structure should looks like this:

{{< filetree/container >}}
  {{< filetree/folder name="example_datapack" >}}
    {{< filetree/file name="pack.mcmeta" >}}
    {{< filetree/file name="pack.png" >}}
    {{< filetree/folder name="data" state="open" >}}
        {{< filetree/folder name="example_datapack" state="open" >}}
            {{< filetree/folder name="oxidation_transformation" state="open" >}}
                {{< filetree/file name="example.json" >}}
            {{< /filetree/folder >}}
        {{< /filetree/folder >}}
    {{< /filetree/folder >}}
  {{< /filetree/folder >}}
{{< /filetree/container >}}

## The data format

An Oxidation transformation json file looks like this:

```json{filename="data/example_datapack/oxidiation_transformation/example.json"}
{
  "base": "<namespace>:<before_waxing_item_id>",
  "oxidized": "<namespace>:<after_waxing_item_id>",
  "chanceMultiplier": 1.0
}
```
| property | description | optional |
| ------ | --- | --- |
| `base` | The item/block before it's oxidized it.| no |
| `waxed` | The oxidized item/block.| no |
| `chanceMultiplier` | The chance for the `base` item to oxidize. Between 0 and 100. | **yes** |

Here's an example of a oxidation transformation json file which permits a diamond item oxidize into a gold ingot.

```json{filename="data/example_datapack/oxidation_transformation/example.json"}
{
  "base": "minecraft:diamond",
  "oxidized": "minecraft:gold_ingot",
  "chanceMultiplier": 10.0
}
```
