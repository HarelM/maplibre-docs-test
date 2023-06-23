[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / DataConstantProperty

# Class: DataConstantProperty<T\>

[maplibregl](../modules/maplibregl.md).DataConstantProperty

An implementation of `Property` for properties that do not permit data-driven (source or composite) expressions.
This restriction allows us to declare statically that the result of possibly evaluating this kind of property
is in fact always the scalar type `T`, and can be used without further evaluating the value on a per-feature basis.

## Type parameters

| Name |
| :------ |
| `T` |

## Implements

- [`Property`](../interfaces/maplibregl.Property.md)<`T`, `T`\>
