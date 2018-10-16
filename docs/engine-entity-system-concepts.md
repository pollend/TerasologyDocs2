---
id: engine-entity-system-concepts
title: Entity System Concepts
sidebar_label: Entity System Concepts
---

This guide is intended to be a quick, non-technical overview of the entity system used by Terasology. For the full technical version see [Entity System Architecture](https://github.com/MovingBlocks/Terasology/wiki/Entity-System-Architecture).

## Entities and Components

The heart of the Entity System is a simple data structure composed of Entities and Components. Each Entity is unique object in the world - the Player is an entity, a single enemy is an Entity, a chest is also an Entity. Entities don't have to be objects that are visible in the world either - they can be scoreboards, loot tables, a UI, and other gameplay related things.

An entity on its own isn't really anything, though. For an Entity to be of use it needs to be given Components. Each component is a feature that an entity can have: a Location component gives an entity a position in the world, a Mesh component gives it appearance, a RigidBody component along with a shape component gives it collision, and so forth.  Each component also can have properties that can be set, that relate to the feature it provides - Location component has a position property, Mesh component has the mesh to display.

This structure provides flexibility and reuse when creating entities - you can add any of the existing components to make use of their features, and concentrate on creating new components for any features that don't presently exist - if any.

## Components and Systems

In Terasology, a component is essentially just a request for an entity to be given a feature, and some data that feeds into how that feature works.  A component itself does not contain any logic for a feature - instead that is left to Systems.

A System provides the actual logic behind a component or combination of components - it can process them each frame, or respond to events dealing with them.  Multiple components being involved is common - rendering a mesh from a Mesh component cannot be done without a location from a Location component, for instance.

There are a number of advantages to the separation between data (in the Components) and logic (in the Systems)
* Allows modules to modify the behaviour of components. If a modder doesn't like the default behaviour of the Health component, they can replace the Health system with their own version - that will still work with all the existing entities with a Health component.
* Allows optimisation of the processing of multiple entities.

## Events

Terasology also includes an event system built around the entity system. Events can be sent to entities, and systems can subscribe to be notified about specific events, when they are received by entities with a desired combination of components.

For instance, when an entity is hit by a sword a DamageEvent is sent to it. This event includes the amount of damage dealt - it could also include information on the type of damage, the source of the damage and so forth.  The Health System would subscribe to the damage event but only for entities with a Health component. So if the hit entity has a health component then the health system would receive the event and can react to it by subtracting health - potentially sending another event if the entity's health reaches zero.

This provides two valuable features:
1. It provides a mechanism for an entity to react to an event based on the components it has. This means that someone can later on create their own component and system combination that reacts to Damage events differently.
2. Because an event can be received by multiple systems, it is possible for modders to intercept and modify or cancel an event to change behaviour.  An armor component could be added that halves all damage, and set up to intercept the damage event - without having to change the health system at all.

## Prefabs

A prefab is a recipe for creating entities. Prefabs mimic the an actual entity - they have components with all the usual values - but are not processes by systems.  Instead they can be used to create an entity with the same components and the same settings.

Additionally, prefabs can be used as a read-only source of information, without ever making entities from them. They could be used to describe crafting recipes for instance.

In Terasology, prefabs can be defined in a JSON format and included in modules.

## Persistence

Entities and their components are automatically persisted when a world is saved.  

## Example modules

Terasology's codebase can be daunting for somebody new to the project. Here are some examples that can hopefully provide some guidance for those who'd like to see how systems and components work in practice, starting from simpler modules and progressing to more complex ones.

1. **[Hunger](https://github.com/Terasology/Hunger)** (basic complexity) - simple component, single widget UI, simple event handling.
1. **[Journal](https://github.com/Terasology/Journal)** (intermediate) - simple component, composite widgets in UI, key binding, introduces events sent over network.
1. **[GrowingFlora](https://github.com/Terasology/GrowingFlora)** (advanced) - advanced components, interaction with world generation and use of scheduled events, introduces concept of chunk states, I'd suggest not looking too much into the tree shape and growth generation itself (implementation) just look at the interfaces.
1. **[Workstation](https://github.com/Terasology/Workstation)** (advanced) - use of components for defining flow, use of prefabs for defining new types of objects, complex interaction with inventory, both player and entity.
1. **[BlockNetwork](https://github.com/Terasology/BlockNetwork)** and **[Signalling](https://github.com/Terasology/Signalling)** (fairly complex) - maintains a separate data structure for loaded entities to improve performance, listens on Component, Entity and Chunk life-cycle events to keep the data structure up-to-date, complex logic, delay handling of events.
