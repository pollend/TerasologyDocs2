---
id: asset_system_delta_overrides
title: Latin-ish
sidebar_label: Add A New Creature
---

Modules can modify prefabs from other modules. This is useful if a module needs to add additional components to existing prefabs, e.g. a module that renders health bars could add a `HealthBar` component to minion prefabs from another module.
Another case is the replacement or disabling of features, e.g. disabling a component that makes trees age but keep the rest of the tree to create a world with never-aging trees.

For both purposes each module provides a `deltas` and an `overrides` folder.

The main difference:

*deltas* -> Override or add single **values** in one prefab  
*overrides* -> override the **entire** prefab

# Example

Take the following component from **Module A** as example:
```java
public class ValuesComponent implements Component {
    public String a;
    public String b;
    public String c;
    public String d;
}
```

**Module A** could define the a prefab with this component like so, e.g. in `Module A/assets/prefabs/anyfolder/valueThing.prefab`:

```json
{
    "values" : {
        "a" : "aa",
        "b" : "bb",
        "c" : "cc",
        "d" : "dd"
    }
}
```

If we instanciate an entity from this prefab, the `ValuesComponent` would have the values `a=aa, b=bb, c=cc, d=dd`.

## Deltas

Deltas modify an existing prefab by keeping existing values. We can use deltas to **change values** or to **add components**.

Let's say **Module B** wants to modify the `valueThing.prefab`, so that the value `d` becomes `d=CHANGED`.
and also add a `BoxShapeComponent` to the thing.
The module has to define the file `Module B/deltas/Module A/prefabs/anyfolder/valueThing.prefab`:
```json
{
    "values" : {
        "d" : "CHANGED"
    },
    "boxShape": {
    }
}
```
The general path for a delta is always `deltas/<Name of the origin module>/prefabs/<same directory structure>/<prefab>`.
If we instanciate the `valueThing` in **Module B**, the `ValueComponent` has the properties `a=aa, b=bb, c=cc, d=CHANGED` and the entity will also have a `BoxShapeComponent` attached.

The main difference to the overrides is, that `Module B/deltas/Module A/prefabs/anyfolder/valueThing.prefab`
```json
{
    "boxShape": {
    }
}
```
would still contain the `ValueComponent` with the properties `a=aa, b=bb, c=cc, d=dd` from **Module A**

## Overrides
Let's say **Module C** wants to remove the `ValueComponent` at all and replace the entire prefab with something else.

Module b could define `Module C/overrides/Module A/prefabs/anyfolder/valueThing.prefab`
```json
{
    "Location": {}
}
```
The general path for overrides is similar to deltas: `overrides/<Name of the origin module>/prefabs/<same directory structure>/<prefab>`

In this case, an entity created from the `valueThing.prefab` in **Module C** has no `ValueComponent` because the entire prefab is overriden and has only a `LocationComponent` left.

The main difference to the *deltas* is, that the entire file is replaced with the new content.