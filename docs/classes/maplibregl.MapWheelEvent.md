[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / MapWheelEvent

# Class: MapWheelEvent

[maplibregl](../modules/maplibregl.md).MapWheelEvent

`MapWheelEvent` is the event type for the `wheel` map event.

## Hierarchy

- `Event`

  ↳ **`MapWheelEvent`**

## Table of contents

### Accessors

- [defaultPrevented](maplibregl.MapWheelEvent.md#defaultprevented)

### Constructors

- [constructor](maplibregl.MapWheelEvent.md#constructor)

### Methods

- [preventDefault](maplibregl.MapWheelEvent.md#preventdefault)

### Properties

- [originalEvent](maplibregl.MapWheelEvent.md#originalevent)
- [target](maplibregl.MapWheelEvent.md#target)
- [type](maplibregl.MapWheelEvent.md#type)

## Accessors

### defaultPrevented

• `get` **defaultPrevented**(): `boolean`

`true` if `preventDefault` has been called.

#### Returns

`boolean`

#### Defined in

[src/ui/events.ts:252](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L252)

## Constructors

### constructor

• `Private` **new MapWheelEvent**(`type`, `map`, `originalEvent`)

#### Parameters

| Name | Type |
| :------ | :------ |
| `type` | `string` |
| `map` | [`Map`](maplibregl.Map.md) |
| `originalEvent` | `WheelEvent` |

#### Overrides

Event.constructor

#### Defined in

[src/ui/events.ts:261](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L261)

## Methods

### preventDefault

▸ **preventDefault**(): `void`

Prevents subsequent default processing of the event by the map.

Calling this method will prevent the the behavior of [ScrollZoomHandler](maplibregl.ScrollZoomHandler.md).

#### Returns

`void`

#### Defined in

[src/ui/events.ts:244](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L244)

## Properties

### originalEvent

• **originalEvent**: `WheelEvent`

The DOM event which caused the map event.

#### Defined in

[src/ui/events.ts:237](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L237)

___

### target

• **target**: [`Map`](maplibregl.Map.md)

The `Map` object that fired the event.

#### Defined in

[src/ui/events.ts:232](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L232)

___

### type

• **type**: ``"wheel"``

The event type.

#### Overrides

Event.type

#### Defined in

[src/ui/events.ts:227](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/events.ts#L227)
