---
id: asset_system_block_attributes
title: Latin-ish
sidebar_label: Add A New Creature
---

The following are the default attributes that can be included in a `.block` definition file - they determine the block's various properties as well as associate it with block textures. Note that additional metadata can be attached to a block definition - this, however, must be specified in the associated `.prefab` file located in the module's `assets/prefabs` subfolder.

Block Attributes:
```
// If not specified, is the TitleCase of the file name.
"displayName" : "Block",
// Whether the block is a liquid.
"liquid" : false,
 
// The block to copy settings and attributes from.
"basedOn" : "engine:plant",
// If true, the block only serves as a base for other blocks and shouldn't actually be used.
"template" : false,
 
// The shape of the block, cube if there are any issues.
"shape" : "engine:cube",
// If specified, creates a block family based on the settings for each shape - not compatible with "rotation".
"shapes" : ["engine:cube", "engine:stair", "engine:slope"]
 
// The rotation type of the block. If horizontal or align to surface, then makes a block family combining the different rotations needed.
"rotation" : "none/horizontal/attachedToSurface",

"sides/top/bottom" : {
    // both which parts to have for align to surface, and what override settings they should have. Can override any of the other setting (allows torch to have a different shape when on the ground, for instance)
}, 
 
// Hardness 0 for indestructible, maybe make that a separate flag too?
"hardness" : 3,
 
// Can other blocks be attached to this. Should add settings for this per side of the block.
"attachmentAllowed" : true,
// Whether this block should be destroyed if the below block is destroyed, should adapt this for
// other cases like torches on walls.
"supportRequired" : false,
 
// Can the block be passed through like a liquid or air.
"penetrable" : false,
// Can the block be targeted by the player.
"targetable" : true,
// Whether the block is visible.
"invisible" : false,
// Whether the texture is masked (need a separate flag for semi-transparent?)
"translucent" : false,
 
// Should both sides of the mesh be rendered (for billboards).
"doubleSided" : false,
// Is Faux SSAO (shadows) created around this block.
"shadowCasting" : true,
"waving" : false,
 
"luminance" : 0,
 
// The image to use.  Defaults to the tile with the same uri as the block.
"tile" : "engine:stone",
// Per-side textures can also be specified.
"tiles" : {
    "all" : "engine:stone",
    "sides" : "engine:stone",
    "topBottom" : "engine:stone",
    "center" : "engine:stone",
    "left" : "engine:stone",
    "right" : "engine:stone",
    "top" : "engine:stone",
    "bottom" : "engine:stone",
    "front" : "engine:stone",
    "back" : "engine:stone"
},
 
// Special color maps
"colorSource" : "default/color_lut/foliage_lut",
"colorSources" : {
    // Per-side options analogous to tiles.
},
 
// Color tinting, can be a 3 or 4 dimensional color.
"colorOffset" : [1,1,1,1],
"colorOffsets" : {
    // Per-side options analogous to tiles.
},
 
// Not yet functional because of physics system work needed, but the mass of the block debris.
"mass" : 10,
 
// Whether the block becomes debris.
"debrisOnDestroy" : true,
 
"entity" : {
    // The entity prefab associated with this block (maybe allow it to be inlined?)
    "prefab" : "engine:chest",
    // Whether the entity should be persistent.
    "temporary" : false,
    // whether changes to the components of an entity are persisted.
    "keepActive" : true
},
 
"inventory" : {
    // Should the block go straight into the harvester's inventory.
    "directPickup" : false,
    "stackable" : true
}
```