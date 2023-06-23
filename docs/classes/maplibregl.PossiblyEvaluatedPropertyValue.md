[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / PossiblyEvaluatedPropertyValue

# Class: PossiblyEvaluatedPropertyValue<T\>

[maplibregl](../modules/maplibregl.md).PossiblyEvaluatedPropertyValue

`PossiblyEvaluatedPropertyValue` is used for data-driven paint and layout property values. It holds a
`PossiblyEvaluatedValue` and the `GlobalProperties` that were used to generate it. You're not allowed to supply
a different set of `GlobalProperties` when performing the final evaluation because they would be ignored in the
case where the input value was a constant or camera function.

## Type parameters

| Name |
| :------ |
| `T` |
