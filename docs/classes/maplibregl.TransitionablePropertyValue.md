[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / TransitionablePropertyValue

# Class: TransitionablePropertyValue<T, R\>

[maplibregl](../modules/maplibregl.md).TransitionablePropertyValue

Paint properties are _transitionable_: they can change in a fluid manner, interpolating or cross-fading between
old and new value. The duration of the transition, and the delay before it begins, is configurable.

`TransitionablePropertyValue` is a compositional class that stores both the property value and that transition
configuration.

A `TransitionablePropertyValue` can calculate the next step in the evaluation chain for paint property values:
`TransitioningPropertyValue`.

## Type parameters

| Name |
| :------ |
| `T` |
| `R` |
