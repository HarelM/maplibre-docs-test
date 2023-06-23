[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / Dispatcher

# Class: Dispatcher

[maplibregl](../modules/maplibregl.md).Dispatcher

Responsible for sending messages from a [Source](../interfaces/maplibregl.Source.md) to an associated
WorkerSource.

## Table of contents

### Methods

- [broadcast](maplibregl.Dispatcher.md#broadcast)
- [getActor](maplibregl.Dispatcher.md#getactor)

## Methods

### broadcast

▸ `Private` **broadcast**(`type`, `data`, `cb?`): `void`

Broadcast a message to all Workers.

#### Parameters

| Name | Type |
| :------ | :------ |
| `type` | `string` |
| `data` | `unknown` |
| `cb?` | (...`args`: `any`[]) => `any` |

#### Returns

`void`

#### Defined in

[src/util/dispatcher.ts:42](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/dispatcher.ts#L42)

___

### getActor

▸ **getActor**(): [`Actor`](maplibregl.Actor.md)

Acquires an actor to dispatch messages to. The actors are distributed in round-robin fashion.

#### Returns

[`Actor`](maplibregl.Actor.md)

An actor object backed by a web worker for processing messages.

#### Defined in

[src/util/dispatcher.ts:53](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/dispatcher.ts#L53)
