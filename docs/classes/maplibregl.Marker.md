[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / Marker

# Class: Marker

[maplibregl](../modules/maplibregl.md).Marker

Creates a marker component

**`Param`**

**`Param`**

DOM element to use as a marker. The default is a light blue, droplet-shaped SVG marker.

**`Param`**

A string indicating the part of the Marker that should be positioned closest to the coordinate set via [setLngLat](maplibregl.Marker.md#setlnglat).
Options are `'center'`, `'top'`, `'bottom'`, `'left'`, `'right'`, `'top-left'`, `'top-right'`, `'bottom-left'`, and `'bottom-right'`.

**`Param`**

The offset in pixels as a [PointLike](../modules/maplibregl.md#pointlike) object to apply relative to the element's center. Negatives indicate left and up.

**`Param`**

The color to use for the default marker if options.element is not provided. The default is light blue.

**`Param`**

The scale to use for the default marker if options.element is not provided. The default scale corresponds to a height of `41px` and a width of `27px`.

**`Param`**

A boolean indicating whether or not a marker is able to be dragged to a new position on the map.

**`Param`**

The max number of pixels a user can shift the mouse pointer during a click on the marker for it to be considered a valid click (as opposed to a marker drag). The default is to inherit map's clickTolerance.

**`Param`**

The rotation angle of the marker in degrees, relative to its respective `rotationAlignment` setting. A positive value will rotate the marker clockwise.

**`Param`**

`map` aligns the `Marker` to the plane of the map. `viewport` aligns the `Marker` to the plane of the viewport. `auto` automatically matches the value of `rotationAlignment`.

**`Param`**

`map` aligns the `Marker`'s rotation relative to the map, maintaining a bearing as the map rotates. `viewport` aligns the `Marker`'s rotation relative to the viewport, agnostic to map rotations. `auto` is equivalent to `viewport`.

**`Example`**

```ts
var marker = new maplibregl.Marker()
  .setLngLat([30.5, 50.5])
  .addTo(map);
```

**`Example`**

```ts
// Set options
var marker = new maplibregl.Marker({
    color: "#FFFFFF",
    draggable: true
  }).setLngLat([30.5, 50.5])
  .addTo(map);
```

**`See`**

 - [Add custom icons with Markers](https://maplibre.org/maplibre-gl-js-docs/example/custom-marker-icons/)
 - [Create a draggable Marker](https://maplibre.org/maplibre-gl-js-docs/example/drag-a-marker/)

## Hierarchy

- [`Evented`](maplibregl.Evented.md)

  ↳ **`Marker`**

## Table of contents

### Methods

- [addTo](maplibregl.Marker.md#addto)
- [getElement](maplibregl.Marker.md#getelement)
- [getLngLat](maplibregl.Marker.md#getlnglat)
- [getOffset](maplibregl.Marker.md#getoffset)
- [getPitchAlignment](maplibregl.Marker.md#getpitchalignment)
- [getPopup](maplibregl.Marker.md#getpopup)
- [getRotation](maplibregl.Marker.md#getrotation)
- [getRotationAlignment](maplibregl.Marker.md#getrotationalignment)
- [isDraggable](maplibregl.Marker.md#isdraggable)
- [listens](maplibregl.Marker.md#listens)
- [off](maplibregl.Marker.md#off)
- [on](maplibregl.Marker.md#on)
- [once](maplibregl.Marker.md#once)
- [remove](maplibregl.Marker.md#remove)
- [setDraggable](maplibregl.Marker.md#setdraggable)
- [setEventedParent](maplibregl.Marker.md#seteventedparent)
- [setLngLat](maplibregl.Marker.md#setlnglat)
- [setOffset](maplibregl.Marker.md#setoffset)
- [setPitchAlignment](maplibregl.Marker.md#setpitchalignment)
- [setPopup](maplibregl.Marker.md#setpopup)
- [setRotation](maplibregl.Marker.md#setrotation)
- [setRotationAlignment](maplibregl.Marker.md#setrotationalignment)
- [togglePopup](maplibregl.Marker.md#togglepopup)

## Methods

### addTo

▸ **addTo**(`map`): [`Marker`](maplibregl.Marker.md)

Attaches the `Marker` to a `Map` object.

**`Example`**

```ts
var marker = new maplibregl.Marker()
  .setLngLat([30.5, 50.5])
  .addTo(map); // add the marker to the map
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `map` | [`Map`](maplibregl.Map.md) | The MapLibre GL JS map to add the marker to. |

#### Returns

[`Marker`](maplibregl.Marker.md)

`this`

#### Defined in

[src/ui/marker.ts:234](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/marker.ts#L234)

___

### getElement

▸ **getElement**(): `HTMLElement`

Returns the `Marker`'s HTML element.

#### Returns

`HTMLElement`

element

#### Defined in

[src/ui/marker.ts:323](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/marker.ts#L323)

___

### getLngLat

▸ **getLngLat**(): [`LngLat`](maplibregl.LngLat.md)

Get the marker's geographical location.

The longitude of the result may differ by a multiple of 360 degrees from the longitude previously
set by `setLngLat` because `Marker` wraps the anchor longitude across copies of the world to keep
the marker on screen.

**`Example`**

```ts
// Store the marker's longitude and latitude coordinates in a variable
var lngLat = marker.getLngLat();
// Print the marker's longitude and latitude values in the console
console.log('Longitude: ' + lngLat.lng + ', Latitude: ' + lngLat.lat )
```

**`See`**

[Create a draggable Marker](https://maplibre.org/maplibre-gl-js-docs/example/drag-a-marker/)

#### Returns

[`LngLat`](maplibregl.LngLat.md)

A [LngLat](maplibregl.LngLat.md) describing the marker's location.

#### Defined in

[src/ui/marker.ts:295](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/marker.ts#L295)

___

### getOffset

▸ **getOffset**(): `Point`

Get the marker's offset.

#### Returns

`Point`

The marker's screen coordinates in pixels.

#### Defined in

[src/ui/marker.ts:481](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/marker.ts#L481)

___

### getPitchAlignment

▸ **getPitchAlignment**(): `string`

Returns the current `pitchAlignment` property of the marker.

#### Returns

`string`

The current pitch alignment of the marker in degrees.

#### Defined in

[src/ui/marker.ts:671](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/marker.ts#L671)

___

### getPopup

▸ **getPopup**(): [`Popup`](maplibregl.Popup.md)

Returns the [Popup](maplibregl.Popup.md) instance that is bound to the [Marker](maplibregl.Marker.md).

**`Example`**

```ts
var marker = new maplibregl.Marker()
 .setLngLat([0, 0])
 .setPopup(new maplibregl.Popup().setHTML("<h1>Hello World!</h1>"))
 .addTo(map);

console.log(marker.getPopup()); // return the popup instance
```

#### Returns

[`Popup`](maplibregl.Popup.md)

popup

#### Defined in

[src/ui/marker.ts:411](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/marker.ts#L411)

___

### getRotation

▸ **getRotation**(): `number`

Returns the current rotation angle of the marker (in degrees).

#### Returns

`number`

The current rotation angle of the marker.

#### Defined in

[src/ui/marker.ts:633](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/marker.ts#L633)

___

### getRotationAlignment

▸ **getRotationAlignment**(): `string`

Returns the current `rotationAlignment` property of the marker.

#### Returns

`string`

The current rotational alignment of the marker.

#### Defined in

[src/ui/marker.ts:652](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/marker.ts#L652)

___

### isDraggable

▸ **isDraggable**(): `boolean`

Returns true if the marker can be dragged

#### Returns

`boolean`

True if the marker is draggable.

#### Defined in

[src/ui/marker.ts:614](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/marker.ts#L614)

___

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

▸ **off**(`type`, `listener`): [`Marker`](maplibregl.Marker.md)

Removes a previously registered event listener.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to remove listeners for. |
| `listener` | `Listener` | The listener function to remove. |

#### Returns

[`Marker`](maplibregl.Marker.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[off](maplibregl.Evented.md#off)

#### Defined in

[src/util/evented.ts:79](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L79)

___

### on

▸ **on**(`type`, `listener`): [`Marker`](maplibregl.Marker.md)

Adds a listener to a specified event type.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to add a listen for. |
| `listener` | `Listener` | The function to be called when the event is fired. The listener function is called with the data object passed to `fire`, extended with `target` and `type` properties. |

#### Returns

[`Marker`](maplibregl.Marker.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[on](maplibregl.Evented.md#on)

#### Defined in

[src/util/evented.ts:65](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L65)

___

### once

▸ **once**(`type`, `listener?`): `Promise`<`any`\> \| [`Marker`](maplibregl.Marker.md)

Adds a listener that will be called only once to a specified event type.

The listener will be called first time the event fires after the listener is registered.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to listen for. |
| `listener?` | `Listener` | The function to be called when the event is fired the first time. |

#### Returns

`Promise`<`any`\> \| [`Marker`](maplibregl.Marker.md)

`this` or a promise if a listener is not provided

#### Inherited from

[Evented](maplibregl.Evented.md).[once](maplibregl.Evented.md#once)

#### Defined in

[src/util/evented.ts:95](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L95)

___

### remove

▸ **remove**(): [`Marker`](maplibregl.Marker.md)

Removes the marker from a map

**`Example`**

```ts
var marker = new maplibregl.Marker().addTo(map);
marker.remove();
```

#### Returns

[`Marker`](maplibregl.Marker.md)

`this`

#### Defined in

[src/ui/marker.ts:258](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/marker.ts#L258)

___

### setDraggable

▸ **setDraggable**(`shouldBeDraggable?`): [`Marker`](maplibregl.Marker.md)

Sets the `draggable` property and functionality of the marker

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `shouldBeDraggable?` | `boolean` | Turns drag functionality on/off |

#### Returns

[`Marker`](maplibregl.Marker.md)

`this`

#### Defined in

[src/ui/marker.ts:592](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/marker.ts#L592)

___

### setEventedParent

▸ `Private` **setEventedParent**(`parent?`, `data?`): [`Marker`](maplibregl.Marker.md)

Bubble all events fired by this instance of Evented to this parent instance of Evented.

#### Parameters

| Name | Type |
| :------ | :------ |
| `parent?` | [`Evented`](maplibregl.Evented.md) |
| `data?` | `any` |

#### Returns

[`Marker`](maplibregl.Marker.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[setEventedParent](maplibregl.Evented.md#seteventedparent)

#### Defined in

[src/util/evented.ts:170](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L170)

___

### setLngLat

▸ **setLngLat**(`lnglat`): [`Marker`](maplibregl.Marker.md)

Set the marker's geographical position and move it.

**`Example`**

```ts
// Create a new marker, set the longitude and latitude, and add it to the map
new maplibregl.Marker()
  .setLngLat([-65.017, -16.457])
  .addTo(map);
```

**`See`**

 - [Add custom icons with Markers](https://maplibre.org/maplibre-gl-js-docs/example/custom-marker-icons/)
 - [Create a draggable Marker](https://maplibre.org/maplibre-gl-js-docs/example/drag-a-marker/)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `lnglat` | [`LngLatLike`](../modules/maplibregl.md#lnglatlike) | A [LngLat](maplibregl.LngLat.md) describing where the marker should be located. |

#### Returns

[`Marker`](maplibregl.Marker.md)

`this`

#### Defined in

[src/ui/marker.ts:311](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/marker.ts#L311)

___

### setOffset

▸ **setOffset**(`offset`): [`Marker`](maplibregl.Marker.md)

Sets the offset of the marker

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `offset` | [`PointLike`](../modules/maplibregl.md#pointlike) | The offset in pixels as a [PointLike](../modules/maplibregl.md#pointlike) object to apply relative to the element's center. Negatives indicate left and up. |

#### Returns

[`Marker`](maplibregl.Marker.md)

`this`

#### Defined in

[src/ui/marker.ts:490](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/marker.ts#L490)

___

### setPitchAlignment

▸ **setPitchAlignment**(`alignment?`): [`Marker`](maplibregl.Marker.md)

Sets the `pitchAlignment` property of the marker.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `alignment?` | `string` | Sets the `pitchAlignment` property of the marker. If alignment is 'auto', it will automatically match `rotationAlignment`. |

#### Returns

[`Marker`](maplibregl.Marker.md)

`this`

#### Defined in

[src/ui/marker.ts:661](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/marker.ts#L661)

___

### setPopup

▸ **setPopup**(`popup?`): [`Marker`](maplibregl.Marker.md)

Binds a [Popup](maplibregl.Popup.md) to the [Marker](maplibregl.Marker.md).

**`Example`**

```ts
var marker = new maplibregl.Marker()
 .setLngLat([0, 0])
 .setPopup(new maplibregl.Popup().setHTML("<h1>Hello World!</h1>")) // add popup
 .addTo(map);
```

**`See`**

[Attach a popup to a marker instance](https://maplibre.org/maplibre-gl-js-docs/example/set-popup/)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `popup?` | [`Popup`](maplibregl.Popup.md) | An instance of the [Popup](maplibregl.Popup.md) class. If undefined or null, any popup set on this [Marker](maplibregl.Marker.md) instance is unset. |

#### Returns

[`Marker`](maplibregl.Marker.md)

`this`

#### Defined in

[src/ui/marker.ts:339](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/marker.ts#L339)

___

### setRotation

▸ **setRotation**(`rotation?`): [`Marker`](maplibregl.Marker.md)

Sets the `rotation` property of the marker.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `rotation?` | `number` | The rotation angle of the marker (clockwise, in degrees), relative to its respective [setRotationAlignment](maplibregl.Marker.md#setrotationalignment) setting. |

#### Returns

[`Marker`](maplibregl.Marker.md)

`this`

#### Defined in

[src/ui/marker.ts:623](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/marker.ts#L623)

___

### setRotationAlignment

▸ **setRotationAlignment**(`alignment?`): [`Marker`](maplibregl.Marker.md)

Sets the `rotationAlignment` property of the marker.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `alignment?` | `string` | Sets the `rotationAlignment` property of the marker. |

#### Returns

[`Marker`](maplibregl.Marker.md)

`this`

#### Defined in

[src/ui/marker.ts:642](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/marker.ts#L642)

___

### togglePopup

▸ **togglePopup**(): [`Marker`](maplibregl.Marker.md)

Opens or closes the [Popup](maplibregl.Popup.md) instance that is bound to the [Marker](maplibregl.Marker.md), depending on the current state of the [Popup](maplibregl.Popup.md).

**`Example`**

```ts
var marker = new maplibregl.Marker()
 .setLngLat([0, 0])
 .setPopup(new maplibregl.Popup().setHTML("<h1>Hello World!</h1>"))
 .addTo(map);

marker.togglePopup(); // toggle popup open or closed
```

#### Returns

[`Marker`](maplibregl.Marker.md)

`this`

#### Defined in

[src/ui/marker.ts:426](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/marker.ts#L426)
