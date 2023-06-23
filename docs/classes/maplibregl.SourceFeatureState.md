[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / SourceFeatureState

# Class: SourceFeatureState

[maplibregl](../modules/maplibregl.md).SourceFeatureState

SourceFeatureState manages the state and pending changes
to features in a source, separated by source layer.
stateChanges and deletedStates batch all changes to the tile (updates and removes, respectively)
between coalesce() events. addFeatureState() and removeFeatureState() also update their counterpart's
list of changes, such that coalesce() can apply the proper state changes while agnostic to the order of operations.
In deletedStates, all null's denote complete removal of state at that scope
