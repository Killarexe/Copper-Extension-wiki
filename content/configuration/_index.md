+++
date = '2025-12-15T21:26:00+01:00'
draft = false
title = 'Mod Configuration'
type = "docs"
weight = 30
+++

**Since Copper Extension version 1.2.1**, there is a GameRule called `copperOxidationChance` which is set by default to 1.

`copperOxidationChance` is a **multiplier to the base oxidation chance** which depends on mod version your playing. *(And yeah, I know the values are high)*


| Version | Chance of oxidation |
|-------- | ------------------- |
| 1.0.0   | $$1.3 \% \ chance/item/s$$ for Fabric; $$27.3 \% \ chance/item/s$$ on Forge |
| 1.1.0   | $$2.7 \% \ chance/item/s$$  |
| 1.4.2   | $$0.3 \% \ chance/item/s$$  |
| 1.5.0   | $$0.004 \% \ chance/item/s$$|

**You can set this GameRule to 0 if you want to disable oxidation in your inventory.**
