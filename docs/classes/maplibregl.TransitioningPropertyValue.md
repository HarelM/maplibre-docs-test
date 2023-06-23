[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / TransitioningPropertyValue

# Class: TransitioningPropertyValue<T, R\>

[maplibregl](../modules/maplibregl.md).TransitioningPropertyValue

`TransitioningPropertyValue` implements the first of two intermediate steps in the evaluation chain of a paint
property value. In this step, transitions between old and new values are handled: as long as the transition is in
progress, `TransitioningPropertyValue` maintains a reference to the prior value, and interpolates between it and
the new value based on the current time and the configured transition duration and delay. The product is the next
step in the evaluation chain: the "possibly evaluated" result type `R`. See below for more on this concept.

## Type parameters

| Name |
| :------ |
| `T` |
| `R` |
