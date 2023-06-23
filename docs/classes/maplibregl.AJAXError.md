[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / AJAXError

# Class: AJAXError

[maplibregl](../modules/maplibregl.md).AJAXError

An error thrown when a HTTP request results in an error response.

**`Param`**

The response's HTTP status code.

**`Param`**

The response's HTTP status text.

**`Param`**

The request's URL.

**`Param`**

The response's body.

## Hierarchy

- `Error`

  ↳ **`AJAXError`**

## Table of contents

### Properties

- [body](maplibregl.AJAXError.md#body)
- [status](maplibregl.AJAXError.md#status)
- [statusText](maplibregl.AJAXError.md#statustext)
- [url](maplibregl.AJAXError.md#url)

## Properties

### body

• **body**: `Blob`

The response's body.

#### Defined in

[src/util/ajax.ts:74](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/ajax.ts#L74)

___

### status

• **status**: `number`

The response's HTTP status code.

#### Defined in

[src/util/ajax.ts:59](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/ajax.ts#L59)

___

### statusText

• **statusText**: `string`

The response's HTTP status text.

#### Defined in

[src/util/ajax.ts:64](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/ajax.ts#L64)

___

### url

• **url**: `string`

The request's URL.

#### Defined in

[src/util/ajax.ts:69](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/ajax.ts#L69)
