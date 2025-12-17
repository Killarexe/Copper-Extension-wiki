+++
date = '2025-12-15T19:50:22+01:00'
draft = false 
title = 'Add Waxing Transformation'
type = "docs"
next = "datapacks/add_lightning_effect"
weight = 20
+++

> [!CAUTION]
> The datapacks are only supported to versions superior or equal to 1.5.0

## Creating the file

Waxing transformation is one of the easiest to implement. Also **if you add a transformation for an item to an other, than the waxed item can be scraped to the unwaxed item.** *(See the [Scraping Mechanic](../../mechanics/scraping))* First you need to create a `waxing_transformation` folder in your namespace folder. Then create a simple `.json` file like your creating a custom recipe.

The structure should looks like this:

{{< filetree/container >}}
  {{< filetree/folder name="example_datapack" >}}
    {{< filetree/file name="pack.mcmeta" >}}
    {{< filetree/file name="pack.png" >}}
    {{< filetree/folder name="data" state="open" >}}
        {{< filetree/folder name="example_datapack" state="open" >}}
            {{< filetree/folder name="waxing_transformation" state="open" >}}
                {{< filetree/file name="example.json" >}}
            {{< /filetree/folder >}}
        {{< /filetree/folder >}}
    {{< /filetree/folder >}}
  {{< /filetree/folder >}}
{{< /filetree/container >}}

## The data format

A Waxing transformation json file looks like this:

```json{filename="data/example_datapack/waxing_transformation/example.json"}
{
  "base": "<namespace>:<before_waxing_item_id>",
  "waxed": "<namespace>:<after_waxing_item_id>"
}
```
| property | description |
| ------ | --- |
| `base` | The item/block before we wax it.|
| `waxed` | The item/block after we wax it.|

Here's an example of a waxing transformation json file which permits to wax a cobblestone into a stone block.

```json{filename="data/example_datapack/waxing_transformation/example.json"}
{
  "base": "minecraft:cobblestone",
  "waxed": "minecraft:stone"
}
```
