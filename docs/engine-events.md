---
id: engine-events
title: Engine Events
sidebar_label: Engine Events
---

## Block Events
|Event|Description|
|---|---|
|BlockLifecycleEvent|   |
|LargeBlockUpdateFinished|   |
|LargeblockUpdateStarting|   |
|OnBlockItemPlaced|Occurs when a BlockItem is placed in the world and becomes a real-world block.  The associated entity is the BlockItem being placed.|
|OnBlockToItem|   |
|OnChangedBlock|   |
|ApplyBlockSelectionEvent|   |

## Chunk Events
|Event|Description|
|---|---|
|BeforeChunkUnload|   |
|OnChunkGenerated|   |
|OnChunkLoaded|   |
|PurgeWorldEvent|   |

## Physics Events
|Event|Description|
|---|---|
|ChangeVelocityEvent|   |
|CollideEvent|   |
|ForceEvent|   |
|ImpuseEvent|   |
|MovedEvent|   |
|PhysicsResynchEvent|   |

## Networking Events
|Event|Description|
|---|---|
|ConnectedEvent|   |
|DisconnectedEvent|   |

## Players Events
|Event|Description|
|---|---|
|OnPlayerSpawnedEvent|   |
|ResetCameraEvent|   |
|RespawnRequestEvent|   |
|PlayerTargetChangedEvent|   |
|DropItemEvent|   |
|GiveItemEvent|   |

## Entity Events
|Event|Description|
|---|---|
|DestroyEvent|   |
|DoDestroyEvent|   |
|InteractionEndEvent|   |
|InteractionEndPredicted|   |
|InteractionEndRequest|   |
|InteractionStartPredicted|   |
|ActivationPredicted|   |
|ActivationRequestDenied|   |
|ChangeHeldItemRequest|   |
|CollisionEvent|   |
|DeathEvent|   |
|FootstepEvent|   |
|JumpEvent|   |
|OnEnterBlockEvent|   |
|OnItemUseEvent|   |
|SetMovmentModeEvent|   |
|SwimStrokeEvent|   |
|CharacterImpuseEvent|   |
|CharacterTeleportEvent|   |

## Life Cycle Events
|Event|Description|
|---|---|
|BeforeDeactivateComponent|   |
|BeforeEntityCreated|   |
|BeforeRemoveComponent|   |
|OnActivatedComponent|   |
|OnAddedComponent|   |
|OnChangedComponent|   |


## Delay Events
|Event|Description|
|---|---|
|AddDelayedActionEvent|   |
|CancelDelayedActionEvent|   |
|DelayedActionTriggeredEvent|   |
|HasDelayedActionEvent|   |
|PeriodicActionTriggeredEvent|   |

## Other Events
|Event|Description|
|---|---|
|ViewDistanceEvent|   |
|AnimEndEvent|   |
|ScreenLayerClosedEvent|   |
|TimeResynchEvent|  |
|LocationResynchEvent|   |
|CommandEvent|    |
|CameraOutEvent|  |
|CameraOverEvent|   |
|CameraTargetChangedEvent|    |