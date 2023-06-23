[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / Actor

# Class: Actor

[maplibregl](../modules/maplibregl.md).Actor

An implementation of the [Actor design pattern](http://en.wikipedia.org/wiki/Actor_model)
that maintains the relationship between asynchronous tasks and the objects
that spin them off - in this case, tasks like parsing parts of styles,
owned by the styles

**`Param`**

**`Param`**

**`Param`**

A unique identifier for the Map instance using this Actor.

## Table of contents

### Methods

- [send](maplibregl.Actor.md#send)

## Methods

### send

▸ `Private` **send**(`type`, `data`, `callback?`, `targetMapId?`, `mustQueue?`): `Cancelable`

Sends a message from a main-thread map to a Worker or from a Worker back to
a main-thread map instance.

#### Parameters

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `type` | `string` | `undefined` | The name of the target method to invoke or '[source-type].[source-name].name' for a method on a WorkerSource. |
| `data` | `unknown` | `undefined` | - |
| `callback?` | `Function` | `undefined` | - |
| `targetMapId?` | `string` | `undefined` | A particular mapId to which to send this message. |
| `mustQueue` | `boolean` | `false` | - |

#### Returns

`Cancelable`

#### Defined in

[src/util/actor.ts:58](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/actor.ts#L58)
