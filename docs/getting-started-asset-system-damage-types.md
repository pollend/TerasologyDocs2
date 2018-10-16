---
id: asset_system_damage_types
title: Latin-ish
sidebar_label: Add A New Creature
---

Items can do different kinds of damage. Imagine a hammer doing blunt damage which is great for smashing rocks while a scissor does sharp damage to get your tiny flowers in good shape.

Damage types are defined as prefabs, some of them are predefined in the engine at ```assets/prefabs/damageTypes```
Most interesting for us is the ```materialDamageMultiplier``` from ```BlockDamageModifierComponent``` which increases the items block damage for a given material.