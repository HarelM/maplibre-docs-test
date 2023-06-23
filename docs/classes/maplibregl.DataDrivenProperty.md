[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / DataDrivenProperty

# Class: DataDrivenProperty<T\>

[maplibregl](../modules/maplibregl.md).DataDrivenProperty

An implementation of `Property` for properties that permit data-driven (source or composite) expressions.
The result of possibly evaluating this kind of property is `PossiblyEvaluatedPropertyValue<T>`; obtaining
a scalar value `T` requires further evaluation on a per-feature basis.

## Type parameters

| Name |
| :------ |
| `T` |

## Hierarchy

- **`DataDrivenProperty`**

  ↳ [`CrossFadedDataDrivenProperty`](maplibregl.CrossFadedDataDrivenProperty.md)

## Implements

- [`Property`](../interfaces/maplibregl.Property.md)<`T`, [`PossiblyEvaluatedPropertyValue`](maplibregl.PossiblyEvaluatedPropertyValue.md)<`T`\>\>
