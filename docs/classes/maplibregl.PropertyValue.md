[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / PropertyValue

# Class: PropertyValue<T, R\>

[maplibregl](../modules/maplibregl.md).PropertyValue

`PropertyValue` represents the value part of a property key-value unit. It's used to represent both
 paint and layout property values, and regardless of whether or not their property supports data-driven
 expressions.

 `PropertyValue` stores the raw input value as seen in a style or a runtime styling API call, i.e. one of the
 following:

   * A constant value of the type appropriate for the property
   * A function which produces a value of that type (but functions are quasi-deprecated in favor of expressions)
   * An expression which produces a value of that type
   * "undefined"/"not present", in which case the property is assumed to take on its default value.

 In addition to storing the original input value, `PropertyValue` also stores a normalized representation,
 effectively treating functions as if they are expressions, and constant or default values as if they are
 (constant) expressions.

## Type parameters

| Name |
| :------ |
| `T` |
| `R` |
