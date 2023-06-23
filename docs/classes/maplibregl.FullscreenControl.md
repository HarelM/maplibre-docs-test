[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / FullscreenControl

# Class: FullscreenControl

[maplibregl](../modules/maplibregl.md).FullscreenControl

A `FullscreenControl` control contains a button for toggling the map in and out of fullscreen mode.
When [requestFullscreen](https://developer.mozilla.org/en-US/docs/Web/API/Element/requestFullscreen) is not supported, fullscreen is handled via CSS properties.
The map's `cooperativeGestures` option is temporarily disabled while the map
is in fullscreen mode, and is restored when the map exist fullscreen mode.

**`Example`**

```ts
// Adds a full screen control to the map
map.addControl(new maplibregl.FullscreenControl({container: document.querySelector('body')}));
```

**`See`**

[View a fullscreen map example](https://maplibre.org/maplibre-gl-js-docs/example/fullscreen/)

 fullscreenstart - Fired when fullscreen mode has started
 fullscreenend - Fired when fullscreen mode has ended

## Hierarchy

- [`Evented`](maplibregl.Evented.md)

  ↳ **`FullscreenControl`**

## Implements

- [`IControl`](../interfaces/maplibregl.IControl.md)

## Table of contents

### Methods

- [listens](maplibregl.FullscreenControl.md#listens)
- [off](maplibregl.FullscreenControl.md#off)
- [on](maplibregl.FullscreenControl.md#on)
- [once](maplibregl.FullscreenControl.md#once)
- [setEventedParent](maplibregl.FullscreenControl.md#seteventedparent)

## Methods

### listens

▸ `Private` **listens**(`type`): `any`

Returns a true if this instance of Evented or any forwardeed instances of Evented have a listener for the specified type.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type |

#### Returns

`any`

`true` if there is at least one registered listener for specified event type, `false` otherwise

#### Inherited from

[Evented](maplibregl.Evented.md).[listens](maplibregl.Evented.md#listens)

#### Defined in

[src/util/evented.ts:155](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L155)

___

### off

▸ **off**(`type`, `listener`): [`FullscreenControl`](maplibregl.FullscreenControl.md)

Removes a previously registered event listener.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to remove listeners for. |
| `listener` | `Listener` | The listener function to remove. |

#### Returns

[`FullscreenControl`](maplibregl.FullscreenControl.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[off](maplibregl.Evented.md#off)

#### Defined in

[src/util/evented.ts:79](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L79)

___

### on

▸ **on**(`type`, `listener`): [`FullscreenControl`](maplibregl.FullscreenControl.md)

Adds a listener to a specified event type.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to add a listen for. |
| `listener` | `Listener` | The function to be called when the event is fired. The listener function is called with the data object passed to `fire`, extended with `target` and `type` properties. |

#### Returns

[`FullscreenControl`](maplibregl.FullscreenControl.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[on](maplibregl.Evented.md#on)

#### Defined in

[src/util/evented.ts:65](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L65)

___

### once

▸ **once**(`type`, `listener?`): `Promise`<`any`\> \| [`FullscreenControl`](maplibregl.FullscreenControl.md)

Adds a listener that will be called only once to a specified event type.

The listener will be called first time the event fires after the listener is registered.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to listen for. |
| `listener?` | `Listener` | The function to be called when the event is fired the first time. |

#### Returns

`Promise`<`any`\> \| [`FullscreenControl`](maplibregl.FullscreenControl.md)

`this` or a promise if a listener is not provided

#### Inherited from

[Evented](maplibregl.Evented.md).[once](maplibregl.Evented.md#once)

#### Defined in

[src/util/evented.ts:95](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L95)

___

### setEventedParent

▸ `Private` **setEventedParent**(`parent?`, `data?`): [`FullscreenControl`](maplibregl.FullscreenControl.md)

Bubble all events fired by this instance of Evented to this parent instance of Evented.

#### Parameters

| Name | Type |
| :------ | :------ |
| `parent?` | [`Evented`](maplibregl.Evented.md) |
| `data?` | `any` |

#### Returns

[`FullscreenControl`](maplibregl.FullscreenControl.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[setEventedParent](maplibregl.Evented.md#seteventedparent)

#### Defined in

[src/util/evented.ts:170](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L170)
