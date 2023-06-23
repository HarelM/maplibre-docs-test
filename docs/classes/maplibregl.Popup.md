[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / Popup

# Class: Popup

[maplibregl](../modules/maplibregl.md).Popup

A popup component.

**`Param`**

**`Param`**

If `true`, a close button will appear in the
top right corner of the popup.

**`Param`**

If `true`, the popup will closed when the
map is clicked.

**`Param`**

If `true`, the popup will closed when the
map moves.

**`Param`**

If `true`, the popup will try to focus the
first focusable element inside the popup.

**`Param`**

A string indicating the part of the Popup that should
be positioned closest to the coordinate set via [setLngLat](maplibregl.Popup.md#setlnglat).
Options are `'center'`, `'top'`, `'bottom'`, `'left'`, `'right'`, `'top-left'`,
`'top-right'`, `'bottom-left'`, and `'bottom-right'`. If unset the anchor will be
dynamically set to ensure the popup falls within the map container with a preference
for `'bottom'`.

**`Param`**

A pixel offset applied to the popup's location specified as:
- a single number specifying a distance from the popup's location
- a [PointLike](../modules/maplibregl.md#pointlike) specifying a constant offset
- an object of Points specifying an offset for each anchor position
Negative offsets indicate left and up.

**`Param`**

Space-separated CSS class names to add to popup container

**`Param`**

A string that sets the CSS property of the popup's maximum width, eg `'300px'`.
To ensure the popup resizes to fit its content, set this property to `'none'`.
Available values can be found here: https://developer.mozilla.org/en-US/docs/Web/CSS/max-width

**`Example`**

```ts
var markerHeight = 50, markerRadius = 10, linearOffset = 25;
var popupOffsets = {
 'top': [0, 0],
 'top-left': [0,0],
 'top-right': [0,0],
 'bottom': [0, -markerHeight],
 'bottom-left': [linearOffset, (markerHeight - markerRadius + linearOffset) * -1],
 'bottom-right': [-linearOffset, (markerHeight - markerRadius + linearOffset) * -1],
 'left': [markerRadius, (markerHeight - markerRadius) * -1],
 'right': [-markerRadius, (markerHeight - markerRadius) * -1]
 };
var popup = new maplibregl.Popup({offset: popupOffsets, className: 'my-class'})
  .setLngLat(e.lngLat)
  .setHTML("<h1>Hello World!</h1>")
  .setMaxWidth("300px")
  .addTo(map);
```

**`See`**

 - [Display a popup](https://maplibre.org/maplibre-gl-js-docs/example/popup/)
 - [Display a popup on hover](https://maplibre.org/maplibre-gl-js-docs/example/popup-on-hover/)
 - [Display a popup on click](https://maplibre.org/maplibre-gl-js-docs/example/popup-on-click/)
 - [Attach a popup to a marker instance](https://maplibre.org/maplibre-gl-js-docs/example/set-popup/)

## Hierarchy

- [`Evented`](maplibregl.Evented.md)

  ↳ **`Popup`**

## Table of contents

### Methods

- [addClassName](maplibregl.Popup.md#addclassname)
- [addTo](maplibregl.Popup.md#addto)
- [getElement](maplibregl.Popup.md#getelement)
- [getLngLat](maplibregl.Popup.md#getlnglat)
- [getMaxWidth](maplibregl.Popup.md#getmaxwidth)
- [isOpen](maplibregl.Popup.md#isopen)
- [listens](maplibregl.Popup.md#listens)
- [off](maplibregl.Popup.md#off)
- [on](maplibregl.Popup.md#on)
- [once](maplibregl.Popup.md#once)
- [remove](maplibregl.Popup.md#remove)
- [removeClassName](maplibregl.Popup.md#removeclassname)
- [setDOMContent](maplibregl.Popup.md#setdomcontent)
- [setEventedParent](maplibregl.Popup.md#seteventedparent)
- [setHTML](maplibregl.Popup.md#sethtml)
- [setLngLat](maplibregl.Popup.md#setlnglat)
- [setMaxWidth](maplibregl.Popup.md#setmaxwidth)
- [setOffset](maplibregl.Popup.md#setoffset)
- [setText](maplibregl.Popup.md#settext)
- [toggleClassName](maplibregl.Popup.md#toggleclassname)
- [trackPointer](maplibregl.Popup.md#trackpointer)

## Methods

### addClassName

▸ **addClassName**(`className`): `void`

Adds a CSS class to the popup container element.

**`Example`**

```ts
let popup = new maplibregl.Popup()
popup.addClassName('some-class')
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `className` | `string` | Non-empty string with CSS class name to add to popup container |

#### Returns

`void`

#### Defined in

[src/ui/popup.ts:441](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/popup.ts#L441)

___

### addTo

▸ **addTo**(`map`): [`Popup`](maplibregl.Popup.md)

Adds the popup to a map.

**`Example`**

```ts
new maplibregl.Popup()
  .setLngLat([0, 0])
  .setHTML("<h1>Null Island</h1>")
  .addTo(map);
```

**`See`**

 - [Display a popup](https://maplibre.org/maplibre-gl-js-docs/example/popup/)
 - [Display a popup on hover](https://maplibre.org/maplibre-gl-js-docs/example/popup-on-hover/)
 - [Display a popup on click](https://maplibre.org/maplibre-gl-js-docs/example/popup-on-click/)
 - [Show polygon information on click](https://maplibre.org/maplibre-gl-js-docs/example/polygon-popup-on-click/)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `map` | [`Map`](maplibregl.Map.md) | The MapLibre GL JS map to add the popup to. |

#### Returns

[`Popup`](maplibregl.Popup.md)

`this`

#### Defined in

[src/ui/popup.ts:130](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/popup.ts#L130)

___

### getElement

▸ **getElement**(): `HTMLElement`

Returns the `Popup`'s HTML element.

**`Example`**

```ts
// Change the `Popup` element's font size
var popup = new maplibregl.Popup()
  .setLngLat([-96, 37.8])
  .setHTML("<p>Hello World!</p>")
  .addTo(map);
var popupElem = popup.getElement();
popupElem.style.fontSize = "25px";
```

#### Returns

`HTMLElement`

element

#### Defined in

[src/ui/popup.ts:320](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/popup.ts#L320)

___

### getLngLat

▸ **getLngLat**(): [`LngLat`](maplibregl.LngLat.md)

Returns the geographical location of the popup's anchor.

The longitude of the result may differ by a multiple of 360 degrees from the longitude previously
set by `setLngLat` because `Popup` wraps the anchor longitude across copies of the world to keep
the popup on screen.

#### Returns

[`LngLat`](maplibregl.LngLat.md)

The geographical location of the popup's anchor.

#### Defined in

[src/ui/popup.ts:250](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/popup.ts#L250)

___

### getMaxWidth

▸ **getMaxWidth**(): `string`

Returns the popup's maximum width.

#### Returns

`string`

The maximum width of the popup.

#### Defined in

[src/ui/popup.ts:381](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/popup.ts#L381)

___

### isOpen

▸ **isOpen**(): `boolean`

#### Returns

`boolean`

`true` if the popup is open, `false` if it is closed.

#### Defined in

[src/ui/popup.ts:184](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/popup.ts#L184)

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

▸ **off**(`type`, `listener`): [`Popup`](maplibregl.Popup.md)

Removes a previously registered event listener.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to remove listeners for. |
| `listener` | `Listener` | The listener function to remove. |

#### Returns

[`Popup`](maplibregl.Popup.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[off](maplibregl.Evented.md#off)

#### Defined in

[src/util/evented.ts:79](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L79)

___

### on

▸ **on**(`type`, `listener`): [`Popup`](maplibregl.Popup.md)

Adds a listener to a specified event type.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to add a listen for. |
| `listener` | `Listener` | The function to be called when the event is fired. The listener function is called with the data object passed to `fire`, extended with `target` and `type` properties. |

#### Returns

[`Popup`](maplibregl.Popup.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[on](maplibregl.Evented.md#on)

#### Defined in

[src/util/evented.ts:65](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L65)

___

### once

▸ **once**(`type`, `listener?`): `Promise`<`any`\> \| [`Popup`](maplibregl.Popup.md)

Adds a listener that will be called only once to a specified event type.

The listener will be called first time the event fires after the listener is registered.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to listen for. |
| `listener?` | `Listener` | The function to be called when the event is fired the first time. |

#### Returns

`Promise`<`any`\> \| [`Popup`](maplibregl.Popup.md)

`this` or a promise if a listener is not provided

#### Inherited from

[Evented](maplibregl.Evented.md).[once](maplibregl.Evented.md#once)

#### Defined in

[src/util/evented.ts:95](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L95)

___

### remove

▸ **remove**(): `this`

Removes the popup from the map it has been added to.

**`Example`**

```ts
var popup = new maplibregl.Popup().addTo(map);
popup.remove();
```

#### Returns

`this`

`this`

#### Defined in

[src/ui/popup.ts:196](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/popup.ts#L196)

___

### removeClassName

▸ **removeClassName**(`className`): `void`

Removes a CSS class from the popup container element.

**`Example`**

```ts
let popup = new maplibregl.Popup()
popup.removeClassName('some-class')
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `className` | `string` | Non-empty string with CSS class name to remove from popup container |

#### Returns

`void`

#### Defined in

[src/ui/popup.ts:456](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/popup.ts#L456)

___

### setDOMContent

▸ **setDOMContent**(`htmlNode`): [`Popup`](maplibregl.Popup.md)

Sets the popup's content to the element provided as a DOM node.

**`Example`**

```ts
// create an element with the popup content
var div = document.createElement('div');
div.innerHTML = 'Hello, world!';
var popup = new maplibregl.Popup()
  .setLngLat(e.lngLat)
  .setDOMContent(div)
  .addTo(map);
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `htmlNode` | `Node` | A DOM node to be used as content for the popup. |

#### Returns

[`Popup`](maplibregl.Popup.md)

`this`

#### Defined in

[src/ui/popup.ts:412](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/popup.ts#L412)

___

### setEventedParent

▸ `Private` **setEventedParent**(`parent?`, `data?`): [`Popup`](maplibregl.Popup.md)

Bubble all events fired by this instance of Evented to this parent instance of Evented.

#### Parameters

| Name | Type |
| :------ | :------ |
| `parent?` | [`Evented`](maplibregl.Evented.md) |
| `data?` | `any` |

#### Returns

[`Popup`](maplibregl.Popup.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[setEventedParent](maplibregl.Evented.md#seteventedparent)

#### Defined in

[src/util/evented.ts:170](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L170)

___

### setHTML

▸ **setHTML**(`html`): [`Popup`](maplibregl.Popup.md)

Sets the popup's content to the HTML provided as a string.

This method does not perform HTML filtering or sanitization, and must be
used only with trusted content. Consider [setText](maplibregl.Popup.md#settext) if
the content is an untrusted text string.

**`Example`**

```ts
var popup = new maplibregl.Popup()
  .setLngLat(e.lngLat)
  .setHTML("<h1>Hello World!</h1>")
  .addTo(map);
```

**`See`**

 - [Display a popup](https://maplibre.org/maplibre-gl-js-docs/example/popup/)
 - [Display a popup on hover](https://maplibre.org/maplibre-gl-js-docs/example/popup-on-hover/)
 - [Display a popup on click](https://maplibre.org/maplibre-gl-js-docs/example/popup-on-click/)
 - [Attach a popup to a marker instance](https://maplibre.org/maplibre-gl-js-docs/example/set-popup/)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `html` | `string` | A string representing HTML content for the popup. |

#### Returns

[`Popup`](maplibregl.Popup.md)

`this`

#### Defined in

[src/ui/popup.ts:362](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/popup.ts#L362)

___

### setLngLat

▸ **setLngLat**(`lnglat`): [`Popup`](maplibregl.Popup.md)

Sets the geographical location of the popup's anchor, and moves the popup to it. Replaces trackPointer() behavior.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `lnglat` | [`LngLatLike`](../modules/maplibregl.md#lnglatlike) | The geographical location to set as the popup's anchor. |

#### Returns

[`Popup`](maplibregl.Popup.md)

`this`

#### Defined in

[src/ui/popup.ts:260](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/popup.ts#L260)

___

### setMaxWidth

▸ **setMaxWidth**(`maxWidth`): [`Popup`](maplibregl.Popup.md)

Sets the popup's maximum width. This is setting the CSS property `max-width`.
Available values can be found here: https://developer.mozilla.org/en-US/docs/Web/CSS/max-width

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `maxWidth` | `string` | A string representing the value for the maximum width. |

#### Returns

[`Popup`](maplibregl.Popup.md)

`this`

#### Defined in

[src/ui/popup.ts:392](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/popup.ts#L392)

___

### setOffset

▸ **setOffset**(`offset?`): [`Popup`](maplibregl.Popup.md)

Sets the popup's offset.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `offset?` | `Offset` | Sets the popup's offset. |

#### Returns

[`Popup`](maplibregl.Popup.md)

`this`

#### Defined in

[src/ui/popup.ts:468](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/popup.ts#L468)

___

### setText

▸ **setText**(`text`): [`Popup`](maplibregl.Popup.md)

Sets the popup's content to a string of text.

This function creates a [Text](https://developer.mozilla.org/en-US/docs/Web/API/Text) node in the DOM,
so it cannot insert raw HTML. Use this method for security against XSS
if the popup content is user-provided.

**`Example`**

```ts
var popup = new maplibregl.Popup()
  .setLngLat(e.lngLat)
  .setText('Hello, world!')
  .addTo(map);
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `text` | `string` | Textual content for the popup. |

#### Returns

[`Popup`](maplibregl.Popup.md)

`this`

#### Defined in

[src/ui/popup.ts:339](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/popup.ts#L339)

___

### toggleClassName

▸ **toggleClassName**(`className`): `boolean`

Add or remove the given CSS class on the popup container, depending on whether the container currently has that class.

**`Example`**

```ts
let popup = new maplibregl.Popup()
popup.toggleClassName('toggleClass')
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `className` | `string` | Non-empty string with CSS class name to add/remove |

#### Returns

`boolean`

if the class was removed return false, if class was added, then return true

#### Defined in

[src/ui/popup.ts:485](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/popup.ts#L485)

___

### trackPointer

▸ **trackPointer**(): [`Popup`](maplibregl.Popup.md)

Tracks the popup anchor to the cursor position on screens with a pointer device (it will be hidden on touchscreens). Replaces the `setLngLat` behavior.
For most use cases, set `closeOnClick` and `closeButton` to `false`.

**`Example`**

```ts
var popup = new maplibregl.Popup({ closeOnClick: false, closeButton: false })
  .setHTML("<h1>Hello World!</h1>")
  .trackPointer()
  .addTo(map);
```

#### Returns

[`Popup`](maplibregl.Popup.md)

`this`

#### Defined in

[src/ui/popup.ts:290](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/popup.ts#L290)
