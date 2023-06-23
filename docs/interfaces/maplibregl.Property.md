[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / Property

# Interface: Property<T, R\>

[maplibregl](../modules/maplibregl.md).Property

Implementations of the `Property` interface:

 * Hold metadata about a property that's independent of any specific value: stuff like the type of the value,
   the default value, etc. This comes from the style specification JSON.
 * Define behavior that needs to be polymorphic across different properties: "possibly evaluating"
   an input value (see below), and interpolating between two possibly-evaluted values.

 The type `T` is the fully-evaluated value type (e.g. `number`, `string`, `Color`).
 The type `R` is the intermediate "possibly evaluated" value type. See below.

 There are two main implementations of the interface -- one for properties that allow data-driven values,
 and one for properties that don't. There are a few "special case" implementations as well: one for properties
 which cross-fade between two values rather than interpolating, one for `heatmap-color` and `line-gradient`,
 and one for `light-position`.

## Type parameters

| Name |
| :------ |
| `T` |
| `R` |

## Implemented by

- [`ColorRampProperty`](../classes/maplibregl.ColorRampProperty.md)
- [`CrossFadedProperty`](../classes/maplibregl.CrossFadedProperty.md)
- [`DataConstantProperty`](../classes/maplibregl.DataConstantProperty.md)
- [`DataDrivenProperty`](../classes/maplibregl.DataDrivenProperty.md)
