[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / Properties

# Class: Properties<Props\>

[maplibregl](../modules/maplibregl.md).Properties

`Properties` holds objects containing default values for the layout or paint property set of a given
layer type. These objects are immutable, and they are used as the prototypes for the `_values` members of
`Transitionable`, `Transitioning`, `Layout`, and `PossiblyEvaluated`. This allows these classes to avoid
doing work in the common case where a property has no explicit value set and should be considered to take
on the default value: using `for (const property of Object.keys(this._values))`, they can iterate over
only the _own_ properties of `_values`, skipping repeated calculation of transitions and possible/final
evaluations for defaults, the result of which will always be the same.

## Type parameters

| Name |
| :------ |
| `Props` |
