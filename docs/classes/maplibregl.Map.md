[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / Map

# Class: Map

[maplibregl](../modules/maplibregl.md).Map

The `Map` object represents the map on your page. It exposes methods
and properties that enable you to programmatically change the map,
and fires events as users interact with it.

You create a `Map` by specifying a `container` and other options.
Then MapLibre GL JS initializes the map on the page and returns your `Map`
object.

**`Param`**

**`Param`**

The HTML element in which MapLibre GL JS will render the map, or the element's string `id`. The specified element must have no children.

**`Param`**

The minimum zoom level of the map (0-24).

**`Param`**

The maximum zoom level of the map (0-24).

**`Param`**

The minimum pitch of the map (0-85). Values greater than 60 degrees are experimental and may result in rendering issues. If you encounter any, please raise an issue with details in the MapLibre project.

**`Param`**

The maximum pitch of the map (0-85). Values greater than 60 degrees are experimental and may result in rendering issues. If you encounter any, please raise an issue with details in the MapLibre project.

**`Param`**

The map's MapLibre style. This must be an a JSON object conforming to
the schema described in the [MapLibre Style Specification](https://maplibre.org/maplibre-style-spec/), or a URL to
such JSON.

**`Param`**

If `true`, the map's position (zoom, center latitude, center longitude, bearing, and pitch) will be synced with the hash fragment of the page's URL.
For example, `http://path/to/my/page.html#2.59/39.26/53.07/-24.1/60`.
An additional string may optionally be provided to indicate a parameter-styled hash,
e.g. http://path/to/my/page.html#map=2.59/39.26/53.07/-24.1/60&foo=bar, where foo
is a custom parameter and bar is an arbitrary hash distinct from the map hash.

**`Param`**

If `false`, no mouse, touch, or keyboard listeners will be attached to the map, so it will not respond to interaction.

**`Param`**

The threshold, measured in degrees, that determines when the map's
bearing will snap to north. For example, with a `bearingSnap` of 7, if the user rotates
the map within 7 degrees of north, the map will automatically snap to exact north.

**`Param`**

If `false`, the map's pitch (tilt) control with "drag to rotate" interaction will be disabled.

**`Param`**

The max number of pixels a user can shift the mouse pointer during a click for it to be considered a valid click (as opposed to a mouse drag).

**`Param`**

If `true`, an [AttributionControl](maplibregl.AttributionControl.md) will be added to the map.

**`Param`**

String or strings to show in an [AttributionControl](maplibregl.AttributionControl.md). Only applicable if `options.attributionControl` is `true`.

**`Param`**

If `true`, the MapLibre logo will be shown.

**`Param`**

A string representing the position of the MapLibre wordmark on the map. Valid options are `top-left`,`top-right`, `bottom-left`, `bottom-right`.

**`Param`**

If `true`, map creation will fail if the performance of MapLibre
GL JS would be dramatically worse than expected (i.e. a software renderer would be used).

**`Param`**

If `true`, the map's canvas can be exported to a PNG using `map.getCanvas().toDataURL()`. This is `false` by default as a performance optimization.

**`Param`**

If `true`, the gl context will be created with MSAA antialiasing, which can be useful for antialiasing custom layers. this is `false` by default as a performance optimization.

**`Param`**

If `false`, the map won't attempt to re-request tiles once they expire per their HTTP `cacheControl`/`expires` headers.

**`Param`**

If set, the map will be constrained to the given bounds.

**`Param`**

If `true`, the "scroll to zoom" interaction is enabled. AroundCenterOptions are passed as options to [enable](maplibregl.ScrollZoomHandler.md#enable).

**`Param`**

If `true`, the "box zoom" interaction is enabled (see [BoxZoomHandler](maplibregl.BoxZoomHandler.md)).

**`Param`**

If `true`, the "drag to rotate" interaction is enabled (see [DragRotateHandler](maplibregl.DragRotateHandler.md)).

**`Param`**

If `true`, the "drag to pan" interaction is enabled. An `Object` value is passed as options to [enable](maplibregl.DragPanHandler.md#enable).

**`Param`**

If `true`, keyboard shortcuts are enabled (see [KeyboardHandler](maplibregl.KeyboardHandler.md)).

**`Param`**

If `true`, the "double click to zoom" interaction is enabled (see [DoubleClickZoomHandler](maplibregl.DoubleClickZoomHandler.md)).

**`Param`**

If `true`, the "pinch to rotate and zoom" interaction is enabled. An `Object` value is passed as options to [enable](maplibregl.TwoFingersTouchZoomRotateHandler.md#enable).

**`Param`**

If `true`, the "drag to pitch" interaction is enabled. An `Object` value is passed as options to TwoFingersTouchPitchHandler#enable.

**`Param`**

If `true` or set to an options object, map is only accessible on desktop while holding Command/Ctrl and only accessible on mobile with two fingers. Interacting with the map using normal gestures will trigger an informational screen. With this option enabled, "drag to pitch" requires a three-finger gesture. Cooperative gestures are disabled when a map enters fullscreen using [#FullscreenControl](../modules/maplibregl.md).

**`Param`**

If `true`, the map will automatically resize when the browser window resizes.

**`Param`**

0]] The initial geographical centerpoint of the map. If `center` is not specified in the constructor options, MapLibre GL JS will look for it in the map's style object. If it is not specified in the style, either, it will default to `[0, 0]` Note: MapLibre GL JS uses longitude, latitude coordinate order (as opposed to latitude, longitude) to match GeoJSON.

**`Param`**

The initial zoom level of the map. If `zoom` is not specified in the constructor options, MapLibre GL JS will look for it in the map's style object. If it is not specified in the style, either, it will default to `0`.

**`Param`**

The initial bearing (rotation) of the map, measured in degrees counter-clockwise from north. If `bearing` is not specified in the constructor options, MapLibre GL JS will look for it in the map's style object. If it is not specified in the style, either, it will default to `0`.

**`Param`**

The initial pitch (tilt) of the map, measured in degrees away from the plane of the screen (0-85). If `pitch` is not specified in the constructor options, MapLibre GL JS will look for it in the map's style object. If it is not specified in the style, either, it will default to `0`. Values greater than 60 degrees are experimental and may result in rendering issues. If you encounter any, please raise an issue with details in the MapLibre project.

**`Param`**

The initial bounds of the map. If `bounds` is specified, it overrides `center` and `zoom` constructor options.

**`Param`**

A [fitBounds](maplibregl.Map.md#fitbounds) options object to use _only_ when fitting the initial `bounds` provided above.

**`Param`**

If `true`, multiple copies of the world will be rendered side by side beyond -180 and 180 degrees longitude. If set to `false`:
- When the map is zoomed out far enough that a single representation of the world does not fill the map's entire
container, there will be blank space beyond 180 and -180 degrees longitude.
- Features that cross 180 and -180 degrees longitude will be cut in two (with one portion on the right edge of the
map and the other on the left edge of the map) at every zoom level.

**`Param`**

The maximum number of tiles stored in the tile cache for a given source. If omitted, the cache will be dynamically sized based on the current viewport which can be set using `maxTileCacheZoomLevels` constructor options.

**`Param`**

The maximum number of zoom levels for which to store tiles for a given source. Tile cache dynamic size is calculated by multiplying `maxTileCacheZoomLevels` with approx number of tiles in the viewport for a given source.

**`Param`**

If false, style validation will be skipped. Useful in production environment.

**`Param`**

Defines a CSS
font-family for locally overriding generation of glyphs in the 'CJK Unified Ideographs', 'Hiragana', 'Katakana' and 'Hangul Syllables' ranges.
In these ranges, font settings from the map's style will be ignored, except for font-weight keywords (light/regular/medium/bold).
Set to `false`, to enable font settings from the map's style for these glyph ranges.
The purpose of this option is to avoid bandwidth-intensive glyph server requests. (See [Use locally generated ideographs](https://maplibre.org/maplibre-gl-js-docs/example/local-ideographs).)

**`Param`**

A callback run before the Map makes a request for an external URL. The callback can be used to modify the url, set headers, or set the credentials property for cross-origin requests.
Expected to return an object with a `url` property and optionally `headers` and `credentials` properties.

**`Param`**

A callback run before the Map's camera is moved due to user input or animation. The callback can be used to modify the new center, zoom, pitch and bearing.
Expected to return an object containing center, zoom, pitch or bearing values to overwrite.

**`Param`**

If `true`, Resource Timing API information will be collected for requests made by GeoJSON and Vector Tile web workers (this information is normally inaccessible from the main Javascript thread). Information will be returned in a `resourceTiming` property of relevant `data` events.

**`Param`**

Controls the duration of the fade-in/fade-out animation for label collisions after initial map load, in milliseconds. This setting affects all symbol layers. This setting does not affect the duration of runtime styling transitions or raster tile cross-fading.

**`Param`**

If `true`, symbols from multiple sources can collide with each other during collision detection. If `false`, collision detection is run separately for the symbols in each source.

**`Param`**

A patch to apply to the default localization table for UI strings, e.g. control tooltips. The `locale` object maps namespaced UI string IDs to translated strings in the target language; see `src/ui/default_locale.js` for an example with all supported string IDs. The object may specify all UI strings (thereby adding support for a new translation) or only a subset of strings (thereby patching the default translation table).

**`Param`**

The pixel ratio. The canvas' `width` attribute will be `container.clientWidth * pixelRatio` and its `height` attribute will be `container.clientHeight * pixelRatio`. Defaults to `devicePixelRatio` if not specified.

**`Example`**

```ts
var map = new maplibregl.Map({
  container: 'map',
  center: [-122.420679, 37.772537],
  zoom: 13,
  style: style_object,
  hash: true,
  transformRequest: (url, resourceType)=> {
    if(resourceType === 'Source' && url.startsWith('http://myHost')) {
      return {
       url: url.replace('http', 'https'),
       headers: { 'my-custom-header': true},
       credentials: 'include'  // Include cookies for cross-origin requests
     }
    }
  }
});
```

**`See`**

[Display a map](https://maplibre.org/maplibre-gl-js-docs/example/simple-map/)

## Hierarchy

- `Camera`

  ↳ **`Map`**

## Table of contents

### Accessors

- [repaint](maplibregl.Map.md#repaint)
- [showCollisionBoxes](maplibregl.Map.md#showcollisionboxes)
- [showPadding](maplibregl.Map.md#showpadding)
- [showTileBoundaries](maplibregl.Map.md#showtileboundaries)
- [version](maplibregl.Map.md#version)

### Methods

- [\_applyUpdatedTransform](maplibregl.Map.md#_applyupdatedtransform)
- [\_cameraForBoxAndBearing](maplibregl.Map.md#_cameraforboxandbearing)
- [\_getTransformForUpdate](maplibregl.Map.md#_gettransformforupdate)
- [\_render](maplibregl.Map.md#_render)
- [\_requestRenderFrame](maplibregl.Map.md#_requestrenderframe)
- [\_update](maplibregl.Map.md#_update)
- [addControl](maplibregl.Map.md#addcontrol)
- [addImage](maplibregl.Map.md#addimage)
- [addLayer](maplibregl.Map.md#addlayer)
- [addSource](maplibregl.Map.md#addsource)
- [addSourceType](maplibregl.Map.md#addsourcetype)
- [addSprite](maplibregl.Map.md#addsprite)
- [areTilesLoaded](maplibregl.Map.md#aretilesloaded)
- [cameraForBounds](maplibregl.Map.md#cameraforbounds)
- [easeTo](maplibregl.Map.md#easeto)
- [fitBounds](maplibregl.Map.md#fitbounds)
- [fitScreenCoordinates](maplibregl.Map.md#fitscreencoordinates)
- [flyTo](maplibregl.Map.md#flyto)
- [getBearing](maplibregl.Map.md#getbearing)
- [getBounds](maplibregl.Map.md#getbounds)
- [getCameraTargetElevation](maplibregl.Map.md#getcameratargetelevation)
- [getCanvas](maplibregl.Map.md#getcanvas)
- [getCanvasContainer](maplibregl.Map.md#getcanvascontainer)
- [getCenter](maplibregl.Map.md#getcenter)
- [getContainer](maplibregl.Map.md#getcontainer)
- [getCooperativeGestures](maplibregl.Map.md#getcooperativegestures)
- [getFeatureState](maplibregl.Map.md#getfeaturestate)
- [getFilter](maplibregl.Map.md#getfilter)
- [getGlyphs](maplibregl.Map.md#getglyphs)
- [getImage](maplibregl.Map.md#getimage)
- [getLayer](maplibregl.Map.md#getlayer)
- [getLayoutProperty](maplibregl.Map.md#getlayoutproperty)
- [getLight](maplibregl.Map.md#getlight)
- [getMaxBounds](maplibregl.Map.md#getmaxbounds)
- [getMaxPitch](maplibregl.Map.md#getmaxpitch)
- [getMaxZoom](maplibregl.Map.md#getmaxzoom)
- [getMinPitch](maplibregl.Map.md#getminpitch)
- [getMinZoom](maplibregl.Map.md#getminzoom)
- [getPadding](maplibregl.Map.md#getpadding)
- [getPaintProperty](maplibregl.Map.md#getpaintproperty)
- [getPitch](maplibregl.Map.md#getpitch)
- [getPixelRatio](maplibregl.Map.md#getpixelratio)
- [getRenderWorldCopies](maplibregl.Map.md#getrenderworldcopies)
- [getSource](maplibregl.Map.md#getsource)
- [getSprite](maplibregl.Map.md#getsprite)
- [getStyle](maplibregl.Map.md#getstyle)
- [getTerrain](maplibregl.Map.md#getterrain)
- [getZoom](maplibregl.Map.md#getzoom)
- [hasControl](maplibregl.Map.md#hascontrol)
- [hasImage](maplibregl.Map.md#hasimage)
- [isMoving](maplibregl.Map.md#ismoving)
- [isRotating](maplibregl.Map.md#isrotating)
- [isSourceLoaded](maplibregl.Map.md#issourceloaded)
- [isStyleLoaded](maplibregl.Map.md#isstyleloaded)
- [isZooming](maplibregl.Map.md#iszooming)
- [jumpTo](maplibregl.Map.md#jumpto)
- [listImages](maplibregl.Map.md#listimages)
- [listens](maplibregl.Map.md#listens)
- [loadImage](maplibregl.Map.md#loadimage)
- [loaded](maplibregl.Map.md#loaded)
- [moveLayer](maplibregl.Map.md#movelayer)
- [off](maplibregl.Map.md#off)
- [on](maplibregl.Map.md#on)
- [once](maplibregl.Map.md#once)
- [panBy](maplibregl.Map.md#panby)
- [panTo](maplibregl.Map.md#panto)
- [project](maplibregl.Map.md#project)
- [queryRenderedFeatures](maplibregl.Map.md#queryrenderedfeatures)
- [querySourceFeatures](maplibregl.Map.md#querysourcefeatures)
- [queryTerrainElevation](maplibregl.Map.md#queryterrainelevation)
- [redraw](maplibregl.Map.md#redraw)
- [remove](maplibregl.Map.md#remove)
- [removeControl](maplibregl.Map.md#removecontrol)
- [removeFeatureState](maplibregl.Map.md#removefeaturestate)
- [removeImage](maplibregl.Map.md#removeimage)
- [removeLayer](maplibregl.Map.md#removelayer)
- [removeSource](maplibregl.Map.md#removesource)
- [removeSprite](maplibregl.Map.md#removesprite)
- [resetNorth](maplibregl.Map.md#resetnorth)
- [resetNorthPitch](maplibregl.Map.md#resetnorthpitch)
- [resize](maplibregl.Map.md#resize)
- [rotateTo](maplibregl.Map.md#rotateto)
- [setBearing](maplibregl.Map.md#setbearing)
- [setCenter](maplibregl.Map.md#setcenter)
- [setCooperativeGestures](maplibregl.Map.md#setcooperativegestures)
- [setEventedParent](maplibregl.Map.md#seteventedparent)
- [setFeatureState](maplibregl.Map.md#setfeaturestate)
- [setFilter](maplibregl.Map.md#setfilter)
- [setGlyphs](maplibregl.Map.md#setglyphs)
- [setLayerZoomRange](maplibregl.Map.md#setlayerzoomrange)
- [setLayoutProperty](maplibregl.Map.md#setlayoutproperty)
- [setLight](maplibregl.Map.md#setlight)
- [setMaxBounds](maplibregl.Map.md#setmaxbounds)
- [setMaxPitch](maplibregl.Map.md#setmaxpitch)
- [setMaxZoom](maplibregl.Map.md#setmaxzoom)
- [setMinPitch](maplibregl.Map.md#setminpitch)
- [setMinZoom](maplibregl.Map.md#setminzoom)
- [setPadding](maplibregl.Map.md#setpadding)
- [setPaintProperty](maplibregl.Map.md#setpaintproperty)
- [setPitch](maplibregl.Map.md#setpitch)
- [setPixelRatio](maplibregl.Map.md#setpixelratio)
- [setRenderWorldCopies](maplibregl.Map.md#setrenderworldcopies)
- [setSprite](maplibregl.Map.md#setsprite)
- [setStyle](maplibregl.Map.md#setstyle)
- [setTerrain](maplibregl.Map.md#setterrain)
- [setTransformRequest](maplibregl.Map.md#settransformrequest)
- [setZoom](maplibregl.Map.md#setzoom)
- [snapToNorth](maplibregl.Map.md#snaptonorth)
- [stop](maplibregl.Map.md#stop)
- [triggerRepaint](maplibregl.Map.md#triggerrepaint)
- [unproject](maplibregl.Map.md#unproject)
- [updateImage](maplibregl.Map.md#updateimage)
- [zoomIn](maplibregl.Map.md#zoomin)
- [zoomOut](maplibregl.Map.md#zoomout)
- [zoomTo](maplibregl.Map.md#zoomto)

### Properties

- [\_imageQueueHandle](maplibregl.Map.md#_imagequeuehandle)
- [\_requestedCameraState](maplibregl.Map.md#_requestedcamerastate)
- [boxZoom](maplibregl.Map.md#boxzoom)
- [doubleClickZoom](maplibregl.Map.md#doubleclickzoom)
- [dragPan](maplibregl.Map.md#dragpan)
- [dragRotate](maplibregl.Map.md#dragrotate)
- [keyboard](maplibregl.Map.md#keyboard)
- [scrollZoom](maplibregl.Map.md#scrollzoom)
- [touchPitch](maplibregl.Map.md#touchpitch)
- [touchZoomRotate](maplibregl.Map.md#touchzoomrotate)
- [transformCameraUpdate](maplibregl.Map.md#transformcameraupdate)

## Accessors

### repaint

• `get` **repaint**(): `boolean`

Gets and sets a Boolean indicating whether the map will
continuously repaint. This information is useful for analyzing performance.

**`Name`**

repaint

**`Instance`**

**`Memberof`**

Map

#### Returns

`boolean`

#### Defined in

[src/ui/map.ts:3140](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L3140)

___

### showCollisionBoxes

• `get` **showCollisionBoxes**(): `boolean`

Gets and sets a Boolean indicating whether the map will render boxes
around all symbols in the data source, revealing which symbols
were rendered or which were hidden due to collisions.
This information is useful for debugging.

**`Name`**

showCollisionBoxes

**`Instance`**

**`Memberof`**

Map

#### Returns

`boolean`

#### Defined in

[src/ui/map.ts:3098](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L3098)

___

### showPadding

• `get` **showPadding**(): `boolean`

Gets and sets a Boolean indicating whether the map will visualize
the padding offsets.

**`Name`**

showPadding

**`Instance`**

**`Memberof`**

Map

#### Returns

`boolean`

#### Defined in

[src/ui/map.ts:3080](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L3080)

___

### showTileBoundaries

• `get` **showTileBoundaries**(): `boolean`

Gets and sets a Boolean indicating whether the map will render an outline
around each tile and the tile ID. These tile boundaries are useful for
debugging.

The uncompressed file size of the first vector source is drawn in the top left
corner of each tile, next to the tile ID.

**`Name`**

showTileBoundaries

**`Instance`**

**`Memberof`**

Map

**`Example`**

```ts
map.showTileBoundaries = true;
```

#### Returns

`boolean`

#### Defined in

[src/ui/map.ts:3064](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L3064)

___

### version

• `get` **version**(): `string`

Returns the package version of the library

#### Returns

`string`

Package version of the library

#### Defined in

[src/ui/map.ts:3155](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L3155)

## Methods

### \_applyUpdatedTransform

▸ **_applyUpdatedTransform**(`tr`): `void`

Called after the camera is done being manipulated.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `tr` | [`Transform`](maplibregl.Transform.md) | the requested camera end state Call `transformCameraUpdate` if present, and then apply the "approved" changes. |

#### Returns

`void`

#### Inherited from

Camera.\_applyUpdatedTransform

#### Defined in

[src/ui/camera.ts:1041](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L1041)

___

### \_cameraForBoxAndBearing

▸ `Private` **_cameraForBoxAndBearing**(`p0`, `p1`, `bearing`, `options?`): `CenterZoomBearing`

Calculate the center of these two points in the viewport and use
the highest zoom level up to and including `Map#getMaxZoom()` that fits
the points in the viewport at the specified bearing.

**`Memberof`**

Map#

**`Example`**

```ts
var p0 = [-79, 43];
var p1 = [-73, 45];
var bearing = 90;
var newCameraTransform = map._cameraForBoxAndBearing(p0, p1, bearing, {
  padding: {top: 10, bottom:25, left: 15, right: 5}
});
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `p0` | [`LngLatLike`](../modules/maplibregl.md#lnglatlike) | First point |
| `p1` | [`LngLatLike`](../modules/maplibregl.md#lnglatlike) | Second point |
| `bearing` | `number` | Desired map bearing at end of animation, in degrees |
| `options?` | `CameraForBoundsOptions` |  |

#### Returns

`CenterZoomBearing`

If map is able to fit to provided bounds, returns `center`, `zoom`, and `bearing`.
     If map is unable to fit, method will warn and return undefined.

#### Inherited from

Camera.\_cameraForBoxAndBearing

#### Defined in

[src/ui/camera.ts:575](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L575)

___

### \_getTransformForUpdate

▸ **_getTransformForUpdate**(): [`Transform`](maplibregl.Transform.md)

Called when the camera is about to be manipulated.
If `transformCameraUpdate` is specified, a copy of the current transform is created to track the accumulated changes.
This underlying transform represents the "desired state" proposed by input handlers / animations / UI controls.
It may differ from the state used for rendering (`this.transform`).

#### Returns

[`Transform`](maplibregl.Transform.md)

Transform to apply changes to

#### Inherited from

Camera.\_getTransformForUpdate

#### Defined in

[src/ui/camera.ts:1027](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L1027)

___

### \_render

▸ `Private` **_render**(`paintStartTimeStamp`): [`Map`](maplibregl.Map.md)

Call when a (re-)render of the map is required:
- The style has changed (`setPaintProperty()`, etc.)
- Source data has changed (e.g. tiles have finished loading)
- The map has is moving (or just finished moving)
- A transition is in progress

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `paintStartTimeStamp` | `number` | The time when the animation frame began executing. |

#### Returns

[`Map`](maplibregl.Map.md)

this

#### Defined in

[src/ui/map.ts:2857](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2857)

___

### \_requestRenderFrame

▸ `Private` **_requestRenderFrame**(`callback`): `number`

Request that the given callback be executed during the next render
frame.  Schedule a render frame if one is not already scheduled.

#### Parameters

| Name | Type |
| :------ | :------ |
| `callback` | () => `void` |

#### Returns

`number`

An id that can be used to cancel the callback

#### Overrides

Camera.\_requestRenderFrame

#### Defined in

[src/ui/map.ts:2836](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2836)

___

### \_update

▸ `Private` **_update**(`updateStyle?`): [`Map`](maplibregl.Map.md)

Update this map's style and sources, and re-render the map.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `updateStyle?` | `boolean` | mark the map's style for reprocessing as well as its sources |

#### Returns

[`Map`](maplibregl.Map.md)

this

#### Defined in

[src/ui/map.ts:2820](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2820)

___

### addControl

▸ **addControl**(`control`, `position?`): [`Map`](maplibregl.Map.md)

Adds an [IControl](../interfaces/maplibregl.IControl.md) to the map, calling `control.onAdd(this)`.

**`Example`**

```ts
// Add zoom and rotation controls to the map.
map.addControl(new maplibregl.NavigationControl());
```

**`See`**

[Display map navigation controls](https://maplibre.org/maplibre-gl-js-docs/example/navigation/)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `control` | [`IControl`](../interfaces/maplibregl.IControl.md) | The [IControl](../interfaces/maplibregl.IControl.md) to add. |
| `position?` | `ControlPosition` | position on the map to which the control will be added. Valid values are `'top-left'`, `'top-right'`, `'bottom-left'`, and `'bottom-right'`. Defaults to `'top-right'`. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:584](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L584)

___

### addImage

▸ **addImage**(`id`, `image`, `options?`): [`Map`](maplibregl.Map.md)

Add an image to the style. This image can be displayed on the map like any other icon in the style's
sprite using the image's ID with
[`icon-image`](https://maplibre.org/maplibre-style-spec/#layout-symbol-icon-image),
[`background-pattern`](https://maplibre.org/maplibre-style-spec/#paint-background-background-pattern),
[`fill-pattern`](https://maplibre.org/maplibre-style-spec/#paint-fill-fill-pattern),
or [`line-pattern`](https://maplibre.org/maplibre-style-spec/#paint-line-line-pattern).
A Map.event:error event will be fired if there is not enough space in the sprite to add this image.

**`Example`**

```ts
// If the style's sprite does not already contain an image with ID 'cat',
// add the image 'cat-icon.png' to the style's sprite with the ID 'cat'.
map.loadImage('https://upload.wikimedia.org/wikipedia/commons/thumb/6/60/Cat_silhouette.svg/400px-Cat_silhouette.svg.png', function(error, image) {
   if (error) throw error;
   if (!map.hasImage('cat')) map.addImage('cat', image);
});

// Add a stretchable image that can be used with `icon-text-fit`
// In this example, the image is 600px wide by 400px high.
map.loadImage('https://upload.wikimedia.org/wikipedia/commons/8/89/Black_and_White_Boxed_%28bordered%29.png', function(error, image) {
   if (error) throw error;
   if (!map.hasImage('border-image')) {
     map.addImage('border-image', image, {
         content: [16, 16, 300, 384], // place text over left half of image, avoiding the 16px border
         stretchX: [[16, 584]], // stretch everything horizontally except the 16px border
         stretchY: [[16, 384]], // stretch everything vertically except the 16px border
     });
   }
});
```

**`See`**

 - Use `HTMLImageElement`: [Add an icon to the map](https://maplibre.org/maplibre-gl-js-docs/example/add-image/)
 - Use `ImageData`: [Add a generated icon to the map](https://maplibre.org/maplibre-gl-js-docs/example/add-image-generated/)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | The ID of the image. |
| `image` | `ImageBitmap` \| `HTMLImageElement` \| `ImageData` \| [`StyleImageInterface`](../interfaces/maplibregl.StyleImageInterface.md) \| { `data`: `Uint8Array` \| `Uint8ClampedArray` ; `height`: `number` ; `width`: `number`  } | The image as an `HTMLImageElement`, `ImageData`, `ImageBitmap` or object with `width`, `height`, and `data` properties with the same format as `ImageData`. |
| `options` | `Partial`<`StyleImageMetadata`\> | Options object. |

#### Returns

[`Map`](maplibregl.Map.md)

#### Defined in

[src/ui/map.ts:1879](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1879)

___

### addLayer

▸ **addLayer**(`layer`, `beforeId?`): [`Map`](maplibregl.Map.md)

Adds a [MapLibre style layer](https://maplibre.org/maplibre-style-spec/#layers)
to the map's style.

A layer defines how data from a specified source will be styled. Read more about layer types
and available paint and layout properties in the [MapLibre Style Specification](https://maplibre.org/maplibre-style-spec/#layers).

TODO: JSDoc can't pass

**`Example`**

```ts
// Add a circle layer with a vector source
map.addLayer({
  id: 'points-of-interest',
  source: {
    type: 'vector',
    url: 'https://demotiles.maplibre.org/tiles/tiles.json'
  },
  'source-layer': 'poi_label',
  type: 'circle',
  paint: {
    // MapLibre Style Specification paint properties
  },
  layout: {
    // MapLibre Style Specification layout properties
  }
});
```

**`Example`**

```ts
// Define a source before using it to create a new layer
map.addSource('state-data', {
  type: 'geojson',
  data: 'path/to/data.geojson'
});

map.addLayer({
  id: 'states',
  // References the GeoJSON source defined above
  // and does not require a `source-layer`
  source: 'state-data',
  type: 'symbol',
  layout: {
    // Set the label content to the
    // feature's `name` property
    text-field: ['get', 'name']
  }
});
```

**`Example`**

```ts
// Add a new symbol layer before an existing layer
map.addLayer({
  id: 'states',
  // References a source that's already been defined
  source: 'state-data',
  type: 'symbol',
  layout: {
    // Set the label content to the
    // feature's `name` property
    text-field: ['get', 'name']
  }
// Add the layer before the existing `cities` layer
}, 'cities');
```

**`See`**

 - [Create and style clusters](https://maplibre.org/maplibre-gl-js-docs/example/cluster/)
 - [Add a vector tile source](https://maplibre.org/maplibre-gl-js-docs/example/vector-source/)
 - [Add a WMS source](https://maplibre.org/maplibre-gl-js-docs/example/wms/)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `layer` | [`CustomLayerInterface`](../interfaces/maplibregl.CustomLayerInterface.md) \| `Object` | The layer to add, |
| `beforeId?` | `string` | The ID of an existing layer to insert the new layer before, resulting in the new layer appearing visually beneath the existing layer. If this argument is not specified, the layer will be appended to the end of the layers array and appear visually above all other layers. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:2177](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2177)

___

### addSource

▸ **addSource**(`id`, `source`): [`Map`](maplibregl.Map.md)

Adds a source to the map's style.

**`Fires`**

source.add

**`Example`**

```ts
map.addSource('my-data', {
  type: 'vector',
  url: 'https://demotiles.maplibre.org/tiles/tiles.json'
});
```

**`Example`**

```ts
map.addSource('my-data', {
  "type": "geojson",
  "data": {
    "type": "Feature",
    "geometry": {
      "type": "Point",
      "coordinates": [-77.0323, 38.9131]
    },
    "properties": {
      "title": "Mapbox DC",
      "marker-symbol": "monument"
    }
  }
});
```

**`See`**

GeoJSON source: [Add live realtime data](https://maplibre.org/maplibre-gl-js-docs/example/live-geojson/)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | The ID of the source to add. Must not conflict with existing sources. |
| `source` | `SourceSpecification` | The source object, conforming to the MapLibre Style Specification's [source definition](https://maplibre.org/maplibre-style-spec/#sources) or CanvasSourceOptions. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:1679](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1679)

___

### addSourceType

▸ `Private` **addSourceType**(`name`, `SourceType`, `callback`): `void`

Adds a [custom source type](#Custom Sources), making it available for use with
[addSource](maplibregl.Map.md#addsource).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `name` | `string` | The name of the source type; source definition objects use this name in the `{type: ...}` field. |
| `SourceType` | `any` | A [Source](../interfaces/maplibregl.Source.md) constructor. |
| `callback` | `Callback`<`void`\> | Called when the source type is ready or with an error argument if there is an error. |

#### Returns

`void`

#### Defined in

[src/ui/map.ts:1791](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1791)

___

### addSprite

▸ **addSprite**(`id`, `url`, `options?`): [`Map`](maplibregl.Map.md)

Adds a sprite to the map's style.

**`Fires`**

style

**`Example`**

```ts
map.addSprite('sprite-two', 'http://example.com/sprite-two');
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | The ID of the sprite to add. Must not conflict with existing sprites. |
| `url` | `string` | The URL to load the sprite from |
| `options?` | `StyleSetterOptions` | Options object. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:2399](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2399)

___

### areTilesLoaded

▸ **areTilesLoaded**(): `boolean`

Returns a Boolean indicating whether all tiles in the viewport from all sources on
the style are loaded.

**`Example`**

```ts
var tilesLoaded = map.areTilesLoaded();
```

#### Returns

`boolean`

A Boolean indicating whether all tiles are loaded.

#### Defined in

[src/ui/map.ts:1770](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1770)

___

### cameraForBounds

▸ **cameraForBounds**(`bounds`, `options?`): `CenterZoomBearing`

**`Memberof`**

Map#

**`Example`**

```ts
var bbox = [[-79, 43], [-73, 45]];
var newCameraTransform = map.cameraForBounds(bbox, {
  padding: {top: 10, bottom:25, left: 15, right: 5}
});
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `bounds` | [`LngLatBoundsLike`](../modules/maplibregl.md#lnglatboundslike) | Calculate the center for these bounds in the viewport and use the highest zoom level up to and including `Map#getMaxZoom()` that fits in the viewport. LngLatBounds represent a box that is always axis-aligned with bearing 0. |
| `options?` | `CameraForBoundsOptions` | Options object |

#### Returns

`CenterZoomBearing`

If map is able to fit to provided bounds, returns `center`, `zoom`, and `bearing`.
If map is unable to fit, method will warn and return undefined.

#### Inherited from

Camera.cameraForBounds

#### Defined in

[src/ui/camera.ts:546](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L546)

___

### easeTo

▸ **easeTo**(`options`, `eventData?`): [`Map`](maplibregl.Map.md)

Changes any combination of `center`, `zoom`, `bearing`, `pitch`, and `padding` with an animated transition
between old and new values. The map will retain its current values for any
details not specified in `options`.

Note: The transition will happen instantly if the user has enabled
the `reduced motion` accessibility feature enabled in their operating system,
unless `options` includes `essential: true`.

**`Memberof`**

Map#

**`Fires`**

movestart

**`Fires`**

zoomstart

**`Fires`**

pitchstart

**`Fires`**

rotate

**`Fires`**

move

**`Fires`**

zoom

**`Fires`**

pitch

**`Fires`**

moveend

**`Fires`**

zoomend

**`Fires`**

pitchend

**`See`**

[Navigate the map with game-like controls](https://maplibre.org/maplibre-gl-js-docs/example/game-controls/)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options` | [`AnimationOptions`](../modules/maplibregl.md#animationoptions) & `CenterZoomBearing` & { `around?`: [`LngLatLike`](../modules/maplibregl.md#lnglatlike) ; `pitch?`: `number`  } & { `delayEndEvents?`: `number` ; `padding?`: `number` \| `RequireAtLeastOne`<[`PaddingOptions`](../modules/maplibregl.md#paddingoptions)\>  } & { `easeId?`: `string` ; `noMoveStart?`: `boolean`  } | Options describing the destination and animation of the transition. Accepts [CameraOptions](../modules/maplibregl.md#cameraoptions) and [AnimationOptions](../modules/maplibregl.md#animationoptions). |
| `eventData?` | `any` | Additional properties to be added to event objects of events triggered by this method. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Inherited from

Camera.easeTo

#### Defined in

[src/ui/camera.ts:879](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L879)

___

### fitBounds

▸ **fitBounds**(`bounds`, `options?`, `eventData?`): [`Map`](maplibregl.Map.md)

Pans and zooms the map to contain its visible area within the specified geographical bounds.
This function will also reset the map's bearing to 0 if bearing is nonzero.

**`Memberof`**

Map#

**`Fires`**

movestart

**`Fires`**

moveend

**`Example`**

```ts
var bbox = [[-79, 43], [-73, 45]];
map.fitBounds(bbox, {
  padding: {top: 10, bottom:25, left: 15, right: 5}
});
```

**`See`**

[Fit a map to a bounding box](https://maplibre.org/maplibre-gl-js-docs/example/fitbounds/)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `bounds` | [`LngLatBoundsLike`](../modules/maplibregl.md#lnglatboundslike) | Center these bounds in the viewport and use the highest zoom level up to and including `Map#getMaxZoom()` that fits them in the viewport. |
| `options?` | `FitBoundsOptions` | Options supports all properties from [AnimationOptions](../modules/maplibregl.md#animationoptions) and [CameraOptions](../modules/maplibregl.md#cameraoptions) in addition to the fields below. |
| `eventData?` | `any` | Additional properties to be added to event objects of events triggered by this method. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Inherited from

Camera.fitBounds

#### Defined in

[src/ui/camera.ts:670](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L670)

___

### fitScreenCoordinates

▸ **fitScreenCoordinates**(`p0`, `p1`, `bearing`, `options?`, `eventData?`): [`Map`](maplibregl.Map.md)

Pans, rotates and zooms the map to to fit the box made by points p0 and p1
once the map is rotated to the specified bearing. To zoom without rotating,
pass in the current map bearing.

**`Memberof`**

Map#

**`Fires`**

movestart

**`Fires`**

moveend

**`Example`**

```ts
var p0 = [220, 400];
var p1 = [500, 900];
map.fitScreenCoordinates(p0, p1, map.getBearing(), {
  padding: {top: 10, bottom:25, left: 15, right: 5}
});
```

**`See`**

Used by [BoxZoomHandler](maplibregl.BoxZoomHandler.md)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `p0` | [`PointLike`](../modules/maplibregl.md#pointlike) | First point on screen, in pixel coordinates |
| `p1` | [`PointLike`](../modules/maplibregl.md#pointlike) | Second point on screen, in pixel coordinates |
| `bearing` | `number` | Desired map bearing at end of animation, in degrees |
| `options?` | `FitBoundsOptions` | Options object |
| `eventData?` | `any` | Additional properties to be added to event objects of events triggered by this method. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Inherited from

Camera.fitScreenCoordinates

#### Defined in

[src/ui/camera.ts:706](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L706)

___

### flyTo

▸ **flyTo**(`options`, `eventData?`): [`Map`](maplibregl.Map.md)

Changes any combination of center, zoom, bearing, and pitch, animating the transition along a curve that
evokes flight. The animation seamlessly incorporates zooming and panning to help
the user maintain her bearings even after traversing a great distance.

Note: The animation will be skipped, and this will behave equivalently to `jumpTo`
if the user has the `reduced motion` accessibility feature enabled in their operating system,
unless 'options' includes `essential: true`.

**`Memberof`**

Map#

**`Fires`**

movestart

**`Fires`**

zoomstart

**`Fires`**

pitchstart

**`Fires`**

move

**`Fires`**

zoom

**`Fires`**

rotate

**`Fires`**

pitch

**`Fires`**

moveend

**`Fires`**

zoomend

**`Fires`**

pitchend

**`Example`**

```ts
// fly with default options to null island
map.flyTo({center: [0, 0], zoom: 9});
// using flyTo options
map.flyTo({
  center: [0, 0],
  zoom: 9,
  speed: 0.2,
  curve: 1,
  easing(t) {
    return t;
  }
});
```

**`See`**

 - [Fly to a location](https://maplibre.org/maplibre-gl-js-docs/example/flyto/)
 - [Slowly fly to a location](https://maplibre.org/maplibre-gl-js-docs/example/flyto-options/)
 - [Fly to a location based on scroll position](https://maplibre.org/maplibre-gl-js-docs/example/scroll-fly-to/)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options` | `FlyToOptions` | Options describing the destination and animation of the transition. Accepts [CameraOptions](../modules/maplibregl.md#cameraoptions), [AnimationOptions](../modules/maplibregl.md#animationoptions), and the following additional options. |
| `eventData?` | `any` | Additional properties to be added to event objects of events triggered by this method. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Inherited from

Camera.flyTo

#### Defined in

[src/ui/camera.ts:1161](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L1161)

___

### getBearing

▸ **getBearing**(): `number`

Returns the map's current bearing. The bearing is the compass direction that is "up"; for example, a bearing
of 90° orients the map so that east is up.

**`Memberof`**

Map#

**`See`**

[Navigate the map with game-like controls](https://maplibre.org/maplibre-gl-js-docs/example/game-controls/)

#### Returns

`number`

The map's current bearing.

#### Inherited from

Camera.getBearing

#### Defined in

[src/ui/camera.ts:383](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L383)

___

### getBounds

▸ **getBounds**(): [`LngLatBounds`](maplibregl.LngLatBounds.md)

Returns the map's geographical bounds. When the bearing or pitch is non-zero, the visible region is not
an axis-aligned rectangle, and the result is the smallest bounds that encompasses the visible region.

**`Example`**

```ts
var bounds = map.getBounds();
```

#### Returns

[`LngLatBounds`](maplibregl.LngLatBounds.md)

The geographical bounds of the map as [LngLatBounds](maplibregl.LngLatBounds.md).

#### Defined in

[src/ui/map.ts:728](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L728)

___

### getCameraTargetElevation

▸ **getCameraTargetElevation**(): `number`

Returns the elevation for the point where the camera is looking.
This value corresponds to:
"meters above sea level" * "exaggeration"

#### Returns

`number`

* The elevation.

#### Defined in

[src/ui/map.ts:3165](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L3165)

___

### getCanvas

▸ **getCanvas**(): `HTMLCanvasElement`

Returns the map's `<canvas>` element.

**`See`**

 - [Measure distances](https://maplibre.org/maplibre-gl-js-docs/example/measure/)
 - [Display a popup on hover](https://maplibre.org/maplibre-gl-js-docs/example/popup-on-hover/)
 - [Center the map on a clicked symbol](https://maplibre.org/maplibre-gl-js-docs/example/center-on-symbol/)

#### Returns

`HTMLCanvasElement`

The map's `<canvas>` element.

#### Defined in

[src/ui/map.ts:2641](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2641)

___

### getCanvasContainer

▸ **getCanvasContainer**(): `HTMLElement`

Returns the HTML element containing the map's `<canvas>` element.

If you want to add non-GL overlays to the map, you should append them to this element.

This is the element to which event bindings for map interactivity (such as panning and zooming) are
attached. It will receive bubbled events from child elements such as the `<canvas>`, but not from
map controls.

**`See`**

[Create a draggable point](https://maplibre.org/maplibre-gl-js-docs/example/drag-a-point/)

#### Returns

`HTMLElement`

The container of the map's `<canvas>`.

#### Defined in

[src/ui/map.ts:2629](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2629)

___

### getCenter

▸ **getCenter**(): [`LngLat`](maplibregl.LngLat.md)

Returns the map's geographical centerpoint.

**`Memberof`**

Map#

**`Example`**

```ts
// return a LngLat object such as {lng: 0, lat: 0}
var center = map.getCenter();
// access longitude and latitude values directly
var {lng, lat} = map.getCenter();
```

#### Returns

[`LngLat`](maplibregl.LngLat.md)

The map's geographical centerpoint.

#### Inherited from

Camera.getCenter

#### Defined in

[src/ui/camera.ts:212](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L212)

___

### getContainer

▸ **getContainer**(): `HTMLElement`

Returns the map's containing HTML element.

#### Returns

`HTMLElement`

The map's container.

#### Defined in

[src/ui/map.ts:2613](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2613)

___

### getCooperativeGestures

▸ **getCooperativeGestures**(): `boolean` \| [`GestureOptions`](../modules/maplibregl.md#gestureoptions)

Gets the map's cooperativeGestures option

#### Returns

`boolean` \| [`GestureOptions`](../modules/maplibregl.md#gestureoptions)

gestureOptions

#### Defined in

[src/ui/map.ts:951](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L951)

___

### getFeatureState

▸ **getFeatureState**(`feature`): `any`

Gets the `state` of a feature.
A feature's `state` is a set of user-defined key-value pairs that are assigned to a feature at runtime.
Features are identified by their `feature.id` attribute, which can be any number or string.

_Note: To access the values in a feature's state object for the purposes of styling the feature, use the [`feature-state` expression](https://maplibre.org/maplibre-style-spec/expressions/#feature-state)._

**`Example`**

```ts
// When the mouse moves over the `my-layer` layer,
// get the feature state for the feature under the mouse
map.on('mousemove', 'my-layer', function(e) {
  if (e.features.length > 0) {
    map.getFeatureState({
      source: 'my-source',
      sourceLayer: 'my-source-layer',
      id: e.features[0].id
    });
  }
});
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `feature` | `FeatureIdentifier` | Feature identifier. Feature objects returned from [queryRenderedFeatures](maplibregl.Map.md#queryrenderedfeatures) or event handlers can be used as feature identifiers. |

#### Returns

`any`

The state of the feature: a set of key-value pairs that was assigned to the feature at runtime.

#### Defined in

[src/ui/map.ts:2604](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2604)

___

### getFilter

▸ **getFilter**(`layerId`): `void` \| `FilterSpecification`

Returns the filter applied to the specified style layer.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `layerId` | `string` | The ID of the style layer whose filter to get. |

#### Returns

`void` \| `FilterSpecification`

The layer's filter.

#### Defined in

[src/ui/map.ts:2300](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2300)

___

### getGlyphs

▸ **getGlyphs**(): `string`

Returns the value of the style's glyphs URL

#### Returns

`string`

glyphs Style's glyphs url

#### Defined in

[src/ui/map.ts:2384](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2384)

___

### getImage

▸ **getImage**(`id`): `StyleImage`

Returns an image, specified by ID, currently available in the map.
This includes both images from the style's original sprite
and any images that have been added at runtime using [addImage](maplibregl.Map.md#addimage).

**`Example`**

```ts
var coffeeShopIcon = map.getImage("coffee_cup");
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | The ID of the image. |

#### Returns

`StyleImage`

An image in the map with the specified ID.

#### Defined in

[src/ui/map.ts:1987](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1987)

___

### getLayer

▸ **getLayer**(`id`): `StyleLayer`

Returns the layer with the specified ID in the map's style.

**`Example`**

```ts
var stateDataLayer = map.getLayer('state-data');
```

**`See`**

 - [Filter symbols by toggling a list](https://maplibre.org/maplibre-gl-js-docs/example/filter-markers/)
 - [Filter symbols by text input](https://maplibre.org/maplibre-gl-js-docs/example/filter-markers-by-input/)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | The ID of the layer to get. |

#### Returns

`StyleLayer`

The layer with the specified ID, or `undefined`
if the ID corresponds to no existing layers.

#### Defined in

[src/ui/map.ts:2230](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2230)

___

### getLayoutProperty

▸ **getLayoutProperty**(`layerId`, `name`): `any`

Returns the value of a layout property in the specified style layer.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `layerId` | `string` | The ID of the layer to get the layout property from. |
| `name` | `string` | The name of the layout property to get. |

#### Returns

`any`

The value of the specified layout property.

#### Defined in

[src/ui/map.ts:2359](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2359)

___

### getLight

▸ **getLight**(): `LightSpecification`

Returns the value of the light object.

#### Returns

`LightSpecification`

light Light properties of the style.

#### Defined in

[src/ui/map.ts:2476](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2476)

___

### getMaxBounds

▸ **getMaxBounds**(): [`LngLatBounds`](maplibregl.LngLatBounds.md)

Returns the maximum geographical bounds the map is constrained to, or `null` if none set.

**`Example`**

```ts
var maxBounds = map.getMaxBounds();
```

#### Returns

[`LngLatBounds`](maplibregl.LngLatBounds.md)

The map object.

#### Defined in

[src/ui/map.ts:738](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L738)

___

### getMaxPitch

▸ **getMaxPitch**(): `number`

Returns the map's maximum allowable pitch.

#### Returns

`number`

maxPitch

#### Defined in

[src/ui/map.ts:911](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L911)

___

### getMaxZoom

▸ **getMaxZoom**(): `number`

Returns the map's maximum allowable zoom level.

**`Example`**

```ts
var maxZoom = map.getMaxZoom();
```

#### Returns

`number`

maxZoom

#### Defined in

[src/ui/map.ts:841](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L841)

___

### getMinPitch

▸ **getMinPitch**(): `number`

Returns the map's minimum allowable pitch.

#### Returns

`number`

minPitch

#### Defined in

[src/ui/map.ts:876](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L876)

___

### getMinZoom

▸ **getMinZoom**(): `number`

Returns the map's minimum allowable zoom level.

**`Example`**

```ts
var minZoom = map.getMinZoom();
```

#### Returns

`number`

minZoom

#### Defined in

[src/ui/map.ts:806](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L806)

___

### getPadding

▸ **getPadding**(): [`PaddingOptions`](../modules/maplibregl.md#paddingoptions)

Returns the current padding applied around the map viewport.

**`Memberof`**

Map#

#### Returns

[`PaddingOptions`](../modules/maplibregl.md#paddingoptions)

The current padding around the map viewport.

#### Inherited from

Camera.getPadding

#### Defined in

[src/ui/camera.ts:412](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L412)

___

### getPaintProperty

▸ **getPaintProperty**(`layerId`, `name`): `unknown`

Returns the value of a paint property in the specified style layer.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `layerId` | `string` | The ID of the layer to get the paint property from. |
| `name` | `string` | The name of a paint property to get. |

#### Returns

`unknown`

The value of the specified paint property.

#### Defined in

[src/ui/map.ts:2331](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2331)

___

### getPitch

▸ **getPitch**(): `number`

Returns the map's current pitch (tilt).

**`Memberof`**

Map#

#### Returns

`number`

The map's current pitch, measured in degrees away from the plane of the screen.

#### Inherited from

Camera.getPitch

#### Defined in

[src/ui/camera.ts:510](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L510)

___

### getPixelRatio

▸ **getPixelRatio**(): `number`

Returns the map's pixel ratio.

#### Returns

`number`

The pixel ratio.

#### Defined in

[src/ui/map.ts:702](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L702)

___

### getRenderWorldCopies

▸ **getRenderWorldCopies**(): `boolean`

Returns the state of `renderWorldCopies`. If `true`, multiple copies of the world will be rendered side by side beyond -180 and 180 degrees longitude. If set to `false`:
- When the map is zoomed out far enough that a single representation of the world does not fill the map's entire
container, there will be blank space beyond 180 and -180 degrees longitude.
- Features that cross 180 and -180 degrees longitude will be cut in two (with one portion on the right edge of the
map and the other on the left edge of the map) at every zoom level.

**`Example`**

```ts
var worldCopiesRendered = map.getRenderWorldCopies();
```

**`See`**

[Render world copies](https://maplibre.org/maplibre-gl-js-docs/example/render-world-copies/)

#### Returns

`boolean`

renderWorldCopies

#### Defined in

[src/ui/map.ts:924](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L924)

___

### getSource

▸ **getSource**(`id`): [`Source`](../interfaces/maplibregl.Source.md)

Returns the source with the specified ID in the map's style.

This method is often used to update a source using the instance members for the relevant
source type as defined in [Sources](#sources).
For example, setting the `data` for a GeoJSON source or updating the `url` and `coordinates`
of an image source.

**`Example`**

```ts
var sourceObject = map.getSource('points');
```

**`See`**

 - [Create a draggable point](https://maplibre.org/maplibre-gl-js-docs/example/drag-a-point/)
 - [Animate a point](https://maplibre.org/maplibre-gl-js-docs/example/animate-point-along-line/)
 - [Add live realtime data](https://maplibre.org/maplibre-gl-js-docs/example/live-geojson/)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | The ID of the source to get. |

#### Returns

[`Source`](../interfaces/maplibregl.Source.md)

The style source with the specified ID or `undefined` if the ID
corresponds to no existing sources.
The shape of the object varies by source type.
A list of options for each source type is available on the MapLibre Style Specification's
[Sources](https://maplibre.org/maplibre-style-spec/sources/) page.

#### Defined in

[src/ui/map.ts:1829](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1829)

___

### getSprite

▸ **getSprite**(): { `id`: `string` ; `url`: `string`  }[]

Returns the as-is value of the style's sprite.

#### Returns

{ `id`: `string` ; `url`: `string`  }[]

style's sprite url or a list of id-url pairs

#### Defined in

[src/ui/map.ts:2431](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2431)

___

### getStyle

▸ **getStyle**(): `StyleSpecification`

Returns the map's MapLibre style object, a JSON object which can be used to recreate the map's style.

**`Example`**

```ts
var styleJson = map.getStyle();
```

#### Returns

`StyleSpecification`

The map's style JSON object.

#### Defined in

[src/ui/map.ts:1629](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1629)

___

### getTerrain

▸ **getTerrain**(): `TerrainSpecification`

Get the terrain-options if terrain is loaded

**`Example`**

```ts
map.getTerrain(); // { source: 'terrain' };
```

#### Returns

`TerrainSpecification`

the TerrainSpecification passed to setTerrain

#### Defined in

[src/ui/map.ts:1758](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1758)

___

### getZoom

▸ **getZoom**(): `number`

Returns the map's current zoom level.

**`Memberof`**

Map#

**`Example`**

```ts
map.getZoom();
```

#### Returns

`number`

The map's current zoom level.

#### Inherited from

Camera.getZoom

#### Defined in

[src/ui/camera.ts:278](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L278)

___

### hasControl

▸ **hasControl**(`control`): `boolean`

Checks if a control exists on the map.

**`Example`**

```ts
// Define a new navigation control.
var navigation = new maplibregl.NavigationControl();
// Add zoom and rotation controls to the map.
map.addControl(navigation);
// Check that the navigation control exists on the map.
map.hasControl(navigation);
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `control` | [`IControl`](../interfaces/maplibregl.IControl.md) | The [IControl](../interfaces/maplibregl.IControl.md) to check. |

#### Returns

`boolean`

True if map contains control.

#### Defined in

[src/ui/map.ts:645](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L645)

___

### hasImage

▸ **hasImage**(`id`): `boolean`

Check whether or not an image with a specific ID exists in the style. This checks both images
in the style's original sprite and any images
that have been added at runtime using [addImage](maplibregl.Map.md#addimage).

**`Example`**

```ts
// Check if an image with the ID 'cat' exists in
// the style's sprite.
var catIconExists = map.hasImage('cat');
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | The ID of the image. |

#### Returns

`boolean`

A Boolean indicating whether the image exists.

#### Defined in

[src/ui/map.ts:2004](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2004)

___

### isMoving

▸ **isMoving**(): `boolean`

Returns true if the map is panning, zooming, rotating, or pitching due to a camera animation or user gesture.

**`Example`**

```ts
var isMoving = map.isMoving();
```

#### Returns

`boolean`

True if the map is moving.

#### Defined in

[src/ui/map.ts:1008](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1008)

___

### isRotating

▸ **isRotating**(): `boolean`

Returns true if the map is rotating due to a camera animation or user gesture.

**`Example`**

```ts
map.isRotating();
```

#### Returns

`boolean`

True if the map is rotating.

#### Defined in

[src/ui/map.ts:1028](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1028)

___

### isSourceLoaded

▸ **isSourceLoaded**(`id`): `boolean`

Returns a Boolean indicating whether the source is loaded. Returns `true` if the source with
the given ID in the map's style has no outstanding network requests, otherwise `false`.

**`Example`**

```ts
var sourceLoaded = map.isSourceLoaded('bathymetry-data');
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | The ID of the source to be checked. |

#### Returns

`boolean`

A Boolean indicating whether the source is loaded.

#### Defined in

[src/ui/map.ts:1694](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1694)

___

### isStyleLoaded

▸ **isStyleLoaded**(): `boolean` \| `void`

Returns a Boolean indicating whether the map's style is fully loaded.

**`Example`**

```ts
var styleLoadStatus = map.isStyleLoaded();
```

#### Returns

`boolean` \| `void`

A Boolean indicating whether the style is fully loaded.

#### Defined in

[src/ui/map.ts:1643](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1643)

___

### isZooming

▸ **isZooming**(): `boolean`

Returns true if the map is zooming due to a camera animation or user gesture.

**`Example`**

```ts
var isZooming = map.isZooming();
```

#### Returns

`boolean`

True if the map is zooming.

#### Defined in

[src/ui/map.ts:1018](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1018)

___

### jumpTo

▸ **jumpTo**(`options`, `eventData?`): [`Map`](maplibregl.Map.md)

Changes any combination of center, zoom, bearing, and pitch, without
an animated transition. The map will retain its current values for any
details not specified in `options`.

**`Memberof`**

Map#

**`Fires`**

movestart

**`Fires`**

zoomstart

**`Fires`**

pitchstart

**`Fires`**

rotate

**`Fires`**

move

**`Fires`**

zoom

**`Fires`**

pitch

**`Fires`**

moveend

**`Fires`**

zoomend

**`Fires`**

pitchend

**`Example`**

```ts
// jump to coordinates at current zoom
map.jumpTo({center: [0, 0]});
// jump with zoom, pitch, and bearing options
map.jumpTo({
  center: [0, 0],
  zoom: 8,
  pitch: 45,
  bearing: 90
});
```

**`See`**

 - [Jump to a series of locations](https://maplibre.org/maplibre-gl-js-docs/example/jump-to/)
 - [Update a feature in realtime](https://maplibre.org/maplibre-gl-js-docs/example/live-update-feature/)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options` | `JumpToOptions` | Options object |
| `eventData?` | `any` | Additional properties to be added to event objects of events triggered by this method. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Inherited from

Camera.jumpTo

#### Defined in

[src/ui/camera.ts:762](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L762)

___

### listImages

▸ **listImages**(): `string`[]

Returns an Array of strings containing the IDs of all images currently available in the map.
This includes both images from the style's original sprite
and any images that have been added at runtime using [addImage](maplibregl.Map.md#addimage).

**`Example`**

```ts
var allImages = map.listImages();
```

#### Returns

`string`[]

An Array of strings containing the names of all sprites/images currently available in the map.

#### Defined in

[src/ui/map.ts:2061](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2061)

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

Camera.listens

#### Defined in

[src/util/evented.ts:155](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L155)

___

### loadImage

▸ **loadImage**(`url`, `callback`): `void`

Load an image from an external URL to be used with [addImage](maplibregl.Map.md#addimage). External
domains must support [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS).

**`Example`**

```ts
// Load an image from an external URL.
map.loadImage('http://placekitten.com/50/50', function(error, image) {
  if (error) throw error;
  // Add the loaded image to the style's sprite with the ID 'kitten'.
  map.addImage('kitten', image);
});
```

**`See`**

[Add an icon to the map](https://maplibre.org/maplibre-gl-js-docs/example/add-image/)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `url` | `string` | The URL of the image file. Image file must be in png, webp, or jpg format. |
| `callback` | `GetImageCallback` | Expecting `callback(error, data)`. Called when the image has loaded or with an error argument if there is an error. |

#### Returns

`void`

#### Defined in

[src/ui/map.ts:2046](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2046)

___

### loaded

▸ **loaded**(): `boolean`

Returns a Boolean indicating whether the map is fully loaded.

Returns `false` if the style is not yet fully loaded,
or if there has been a change to the sources or style that
has not yet fully loaded.

#### Returns

`boolean`

A Boolean indicating whether the map is fully loaded.

#### Defined in

[src/ui/map.ts:2808](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2808)

___

### moveLayer

▸ **moveLayer**(`id`, `beforeId?`): [`Map`](maplibregl.Map.md)

Moves a layer to a different z-position.

**`Example`**

```ts
// Move a layer with ID 'polygon' before the layer with ID 'country-label'. The `polygon` layer will appear beneath the `country-label` layer on the map.
map.moveLayer('polygon', 'country-label');
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | The ID of the layer to move. |
| `beforeId?` | `string` | The ID of an existing layer to insert the new layer before. When viewing the map, the `id` layer will appear beneath the `beforeId` layer. If `beforeId` is omitted, the layer will be appended to the end of the layers array and appear above all other layers on the map. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:2194](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2194)

___

### off

▸ **off**<`T`\>(`type`, `layer`, `listener`): [`Map`](maplibregl.Map.md)

Removes an event listener for layer-specific events previously added with `Map#on`.

#### Type parameters

| Name | Type |
| :------ | :------ |
| `T` | extends keyof `MapLayerEventType` |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `T` | The event type previously used to install the listener. |
| `layer` | `string` | The layer ID or listener previously used to install the listener. |
| `listener` | (`ev`: `MapLayerEventType`[`T`] & `Object`) => `void` | The function previously installed as a listener. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Overrides

Camera.off

#### Defined in

[src/ui/map.ts:1281](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1281)

___

### on

▸ **on**<`T`\>(`type`, `layer`, `listener`): [`Map`](maplibregl.Map.md)

Adds a listener for events of a specified type, optionally limited to features in a specified style layer.

**`Example`**

```ts
// Set an event listener that will fire
// when the map has finished loading
map.on('load', function() {
  // Once the map has finished loading,
  // add a new layer
  map.addLayer({
    id: 'points-of-interest',
    source: {
      type: 'vector',
      url: 'https://maplibre.org/maplibre-style-spec/'
    },
    'source-layer': 'poi_label',
    type: 'circle',
    paint: {
      // MapLibre Style Specification paint properties
    },
    layout: {
      // MapLibre Style Specification layout properties
    }
  });
});
```

**`Example`**

```ts
// Set an event listener that will fire
// when a feature on the countries layer of the map is clicked
map.on('click', 'countries', function(e) {
  new maplibregl.Popup()
    .setLngLat(e.lngLat)
    .setHTML(`Country name: ${e.features[0].properties.name}`)
    .addTo(map);
});
```

**`See`**

 - [Display popup on click](https://maplibre.org/maplibre-gl-js-docs/example/popup-on-click/)
 - [Center the map on a clicked symbol](https://maplibre.org/maplibre-gl-js-docs/example/center-on-symbol/)
 - [Create a hover effect](https://maplibre.org/maplibre-gl-js-docs/example/hover-styles/)
 - [Create a draggable marker](https://maplibre.org/maplibre-gl-js-docs/example/drag-a-point/)

#### Type parameters

| Name | Type |
| :------ | :------ |
| `T` | extends keyof `MapLayerEventType` |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `T` | The event type to listen for. Events compatible with the optional `layerId` parameter are triggered when the cursor enters a visible portion of the specified layer from outside that layer or outside the map canvas. \| Event \| Compatible with `layerId` \| \|-----------------------------------------------------------\|---------------------------\| \| [`mousedown`](#map.event:mousedown) \| yes \| \| [`mouseup`](#map.event:mouseup) \| yes \| \| [`mouseover`](#map.event:mouseover) \| yes \| \| [`mouseout`](#map.event:mouseout) \| yes \| \| [`mousemove`](#map.event:mousemove) \| yes \| \| [`mouseenter`](#map.event:mouseenter) \| yes (required) \| \| [`mouseleave`](#map.event:mouseleave) \| yes (required) \| \| [`click`](#map.event:click) \| yes \| \| [`dblclick`](#map.event:dblclick) \| yes \| \| [`contextmenu`](#map.event:contextmenu) \| yes \| \| [`touchstart`](#map.event:touchstart) \| yes \| \| [`touchend`](#map.event:touchend) \| yes \| \| [`touchcancel`](#map.event:touchcancel) \| yes \| \| [`wheel`](#map.event:wheel) \| \| \| [`resize`](#map.event:resize) \| \| \| [`remove`](#map.event:remove) \| \| \| [`touchmove`](#map.event:touchmove) \| \| \| [`movestart`](#map.event:movestart) \| \| \| [`move`](#map.event:move) \| \| \| [`moveend`](#map.event:moveend) \| \| \| [`dragstart`](#map.event:dragstart) \| \| \| [`drag`](#map.event:drag) \| \| \| [`dragend`](#map.event:dragend) \| \| \| [`zoomstart`](#map.event:zoomstart) \| \| \| [`zoom`](#map.event:zoom) \| \| \| [`zoomend`](#map.event:zoomend) \| \| \| [`rotatestart`](#map.event:rotatestart) \| \| \| [`rotate`](#map.event:rotate) \| \| \| [`rotateend`](#map.event:rotateend) \| \| \| [`pitchstart`](#map.event:pitchstart) \| \| \| [`pitch`](#map.event:pitch) \| \| \| [`pitchend`](#map.event:pitchend) \| \| \| [`boxzoomstart`](#map.event:boxzoomstart) \| \| \| [`boxzoomend`](#map.event:boxzoomend) \| \| \| [`boxzoomcancel`](#map.event:boxzoomcancel) \| \| \| [`webglcontextlost`](#map.event:webglcontextlost) \| \| \| [`webglcontextrestored`](#map.event:webglcontextrestored) \| \| \| [`load`](#map.event:load) \| \| \| [`render`](#map.event:render) \| \| \| [`idle`](#map.event:idle) \| \| \| [`error`](#map.event:error) \| \| \| [`data`](#map.event:data) \| \| \| [`styledata`](#map.event:styledata) \| \| \| [`sourcedata`](#map.event:sourcedata) \| \| \| [`dataloading`](#map.event:dataloading) \| \| \| [`styledataloading`](#map.event:styledataloading) \| \| \| [`sourcedataloading`](#map.event:sourcedataloading) \| \| \| [`styleimagemissing`](#map.event:styleimagemissing) \| \| \| [`dataabort`](#map.event:dataabort) \| \| \| [`sourcedataabort`](#map.event:sourcedataabort) \| \| |
| `layer` | `string` | The ID of a style layer or a listener if no ID is provided. Event will only be triggered if its location is within a visible feature in this layer. The event will have a `features` property containing an array of the matching features. If `layerIdOrListener` is not supplied, the event will not have a `features` property. Please note that many event types are not compatible with the optional `layerIdOrListener` parameter. |
| `listener` | (`ev`: `MapLayerEventType`[`T`] & `Object`) => `void` | The function to be called when the event is fired. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Overrides

Camera.on

#### Defined in

[src/ui/map.ts:1185](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1185)

___

### once

▸ **once**<`T`\>(`type`, `layer`, `listener?`): [`Map`](maplibregl.Map.md) \| `Promise`<`MapLayerEventType`[`T`] & `Object`\>

Adds a listener that will be called only once to a specified event type occurring on features in a specified style layer.

#### Type parameters

| Name | Type |
| :------ | :------ |
| `T` | extends keyof `MapLayerEventType` |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `T` | The event type to listen for; one of `'mousedown'`, `'mouseup'`, `'click'`, `'dblclick'`, `'mousemove'`, `'mouseenter'`, `'mouseleave'`, `'mouseover'`, `'mouseout'`, `'contextmenu'`, `'touchstart'`, `'touchend'`, or `'touchcancel'`. `mouseenter` and `mouseover` events are triggered when the cursor enters a visible portion of the specified layer from outside that layer or outside the map canvas. `mouseleave` and `mouseout` events are triggered when the cursor leaves a visible portion of the specified layer, or leaves the map canvas. |
| `layer` | `string` | The ID of a style layer or a listener if no ID is provided. Only events whose location is within a visible feature in this layer will trigger the listener. The event will have a `features` property containing an array of the matching features. |
| `listener?` | (`ev`: `MapLayerEventType`[`T`] & `Object`) => `void` | The function to be called when the event is fired. |

#### Returns

[`Map`](maplibregl.Map.md) \| `Promise`<`MapLayerEventType`[`T`] & `Object`\>

`this` if listener is provided, promise otherwise to allow easier usage of async/await

#### Overrides

Camera.once

#### Defined in

[src/ui/map.ts:1239](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1239)

___

### panBy

▸ **panBy**(`offset`, `options?`, `eventData?`): [`Map`](maplibregl.Map.md)

Pans the map by the specified offset.

**`Memberof`**

Map#

**`Fires`**

movestart

**`Fires`**

moveend

**`See`**

[Navigate the map with game-like controls](https://maplibre.org/maplibre-gl-js-docs/example/game-controls/)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `offset` | [`PointLike`](../modules/maplibregl.md#pointlike) | `x` and `y` coordinates by which to pan the map. |
| `options?` | [`AnimationOptions`](../modules/maplibregl.md#animationoptions) | Options object |
| `eventData?` | `any` | Additional properties to be added to event objects of events triggered by this method. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Inherited from

Camera.panBy

#### Defined in

[src/ui/camera.ts:242](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L242)

___

### panTo

▸ **panTo**(`lnglat`, `options?`, `eventData?`): [`Map`](maplibregl.Map.md)

Pans the map to the specified location with an animated transition.

**`Memberof`**

Map#

**`Fires`**

movestart

**`Fires`**

moveend

**`Example`**

```ts
map.panTo([-74, 38]);
```

**`Example`**

```ts
// Specify that the panTo animation should last 5000 milliseconds.
map.panTo([-74, 38], {duration: 5000});
```

**`See`**

[Update a feature in realtime](https://maplibre.org/maplibre-gl-js-docs/example/live-update-feature/)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `lnglat` | [`LngLatLike`](../modules/maplibregl.md#lnglatlike) | The location to pan the map to. |
| `options?` | [`AnimationOptions`](../modules/maplibregl.md#animationoptions) | Options describing the destination and animation of the transition. |
| `eventData?` | `any` | Additional properties to be added to event objects of events triggered by this method. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Inherited from

Camera.panTo

#### Defined in

[src/ui/camera.ts:264](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L264)

___

### project

▸ **project**(`lnglat`): `Point`

Returns a [Point](https://github.com/mapbox/point-geometry) representing pixel coordinates, relative to the map's `container`,
that correspond to the specified geographical location.

**`Example`**

```ts
var coordinate = [-122.420679, 37.772537];
var point = map.project(coordinate);
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `lnglat` | [`LngLatLike`](../modules/maplibregl.md#lnglatlike) | The geographical location to project. |

#### Returns

`Point`

The [Point](https://github.com/mapbox/point-geometry) corresponding to `lnglat`, relative to the map's `container`.

#### Defined in

[src/ui/map.ts:982](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L982)

___

### queryRenderedFeatures

▸ **queryRenderedFeatures**(`geometryOrOptions?`, `options?`): `MapGeoJSONFeature`[]

Returns an array of MapGeoJSONFeature objects
representing visible features that satisfy the query parameters.

**`Example`**

```ts
// Find all features at a point
var features = map.queryRenderedFeatures(
  [20, 35],
  { layers: ['my-layer-name'] }
);
```

**`Example`**

```ts
// Find all features within a static bounding box
var features = map.queryRenderedFeatures(
  [[10, 20], [30, 50]],
  { layers: ['my-layer-name'] }
);
```

**`Example`**

```ts
// Find all features within a bounding box around a point
var width = 10;
var height = 20;
var features = map.queryRenderedFeatures([
  [point.x - width / 2, point.y - height / 2],
  [point.x + width / 2, point.y + height / 2]
], { layers: ['my-layer-name'] });
```

**`Example`**

```ts
// Query all rendered features from a single layer
var features = map.queryRenderedFeatures({ layers: ['my-layer-name'] });
```

**`See`**

[Get features under the mouse pointer](https://maplibre.org/maplibre-gl-js-docs/example/queryrenderedfeatures/)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `geometryOrOptions?` | [`PointLike`](../modules/maplibregl.md#pointlike) \| `QueryRenderedFeaturesOptions` \| [[`PointLike`](../modules/maplibregl.md#pointlike), [`PointLike`](../modules/maplibregl.md#pointlike)] | (optional) The geometry of the query region: either a single point or southwest and northeast points describing a bounding box. Omitting this parameter (i.e. calling [queryRenderedFeatures](maplibregl.Map.md#queryrenderedfeatures) with zero arguments, or with only a `options` argument) is equivalent to passing a bounding box encompassing the entire map viewport. The geometryOrOptions can receive a QueryRenderedFeaturesOptions only to support a situation where the function receives only one parameter which is the options parameter. |
| `options?` | `QueryRenderedFeaturesOptions` | (optional) Options object. |

#### Returns

`MapGeoJSONFeature`[]

An array of MapGeoJSONFeature objects.

The `properties` value of each returned feature object contains the properties of its source feature. For GeoJSON sources, only
string and numeric property values are supported (i.e. `null`, `Array`, and `Object` values are not supported).

Each feature includes top-level `layer`, `source`, and `sourceLayer` properties. The `layer` property is an object
representing the style layer to  which the feature belongs. Layout and paint properties in this object contain values
which are fully evaluated for the given zoom level and feature.

Only features that are currently rendered are included. Some features will **not** be included, like:

- Features from layers whose `visibility` property is `"none"`.
- Features from layers whose zoom range excludes the current zoom level.
- Symbol features that have been hidden due to text or icon collision.

Features from all other layers are included, including features that may have no visible
contribution to the rendered result; for example, because the layer's opacity or color alpha component is set to
0.

The topmost rendered feature appears first in the returned array, and subsequent features are sorted by
descending z-order. Features that are rendered multiple times (due to wrapping across the antemeridian at low
zoom levels) are returned only once (though subject to the following caveat).

Because features come from tiled vector data or GeoJSON data that is converted to tiles internally, feature
geometries may be split or duplicated across tile boundaries and, as a result, features may appear multiple
times in query results. For example, suppose there is a highway running through the bounding rectangle of a query.
The results of the query will be those parts of the highway that lie within the map tiles covering the bounding
rectangle, even if the highway extends into other tiles, and the portion of the highway within each map tile
will be returned as a separate feature. Similarly, a point feature near a tile boundary may appear in multiple
tiles due to tile buffering.

#### Defined in

[src/ui/map.ts:1391](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1391)

___

### querySourceFeatures

▸ **querySourceFeatures**(`sourceId`, `parameters?`): `MapGeoJSONFeature`[]

Returns an array of MapGeoJSONFeature objects
representing features within the specified vector tile or GeoJSON source that satisfy the query parameters.

**`Example`**

```ts
// Find all features in one source layer in a vector source
var features = map.querySourceFeatures('your-source-id', {
  sourceLayer: 'your-source-layer'
});
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `sourceId` | `string` | The ID of the vector tile or GeoJSON source to query. |
| `parameters?` | `Object` | Options object. |
| `parameters.filter?` | `FilterSpecification` | A [filter](https://maplibre.org/maplibre-style-spec/layers/#filter) to limit query results. |
| `parameters.sourceLayer?` | `string` | The name of the source layer to query. *For vector tile sources, this parameter is required.* For GeoJSON sources, it is ignored. |
| `parameters.validate?` | `boolean` | Whether to check if the [parameters.filter] conforms to the MapLibre Style Specification. Disabling validation is a performance optimization that should only be used if you have previously validated the values you will be passing to this function. |

#### Returns

`MapGeoJSONFeature`[]

An array of MapGeoJSONFeature objects.

In contrast to [queryRenderedFeatures](maplibregl.Map.md#queryrenderedfeatures), this function returns all features matching the query parameters,
whether or not they are rendered by the current style (i.e. visible). The domain of the query includes all currently-loaded
vector tiles and GeoJSON source tiles: this function does not check tiles outside the currently
visible viewport.

Because features come from tiled vector data or GeoJSON data that is converted to tiles internally, feature
geometries may be split or duplicated across tile boundaries and, as a result, features may appear multiple
times in query results. For example, suppose there is a highway running through the bounding rectangle of a query.
The results of the query will be those parts of the highway that lie within the map tiles covering the bounding
rectangle, even if the highway extends into other tiles, and the portion of the highway within each map tile
will be returned as a separate feature. Similarly, a point feature near a tile boundary may appear in multiple
tiles due to tile buffering.

#### Defined in

[src/ui/map.ts:1445](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1445)

___

### queryTerrainElevation

▸ **queryTerrainElevation**(`lngLatLike`): `number`

Query the current elevation of location. It return null if terrain is not enabled. the elevation is in meters relative to mean sea-level

**`Memberof`**

Map#

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `lngLatLike` | [`LngLatLike`](../modules/maplibregl.md#lnglatlike) | [x,y] or LngLat coordinates of the location |

#### Returns

`number`

elevation in meters

#### Inherited from

Camera.queryTerrainElevation

#### Defined in

[src/ui/camera.ts:1420](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L1420)

___

### redraw

▸ **redraw**(): [`Map`](maplibregl.Map.md)

Force a synchronous redraw of the map.

**`Example`**

```ts
map.redraw();
```

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:2966](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2966)

___

### remove

▸ **remove**(): `void`

Clean up and release all internal resources associated with this map.

This includes DOM elements, event bindings, web workers, and WebGL resources.

Use this method when you are done using the map and wish to ensure that it no
longer consumes browser resources. Afterwards, you must not call any other
methods on the map.

#### Returns

`void`

#### Defined in

[src/ui/map.ts:2987](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2987)

___

### removeControl

▸ **removeControl**(`control`): [`Map`](maplibregl.Map.md)

Removes the control from the map.

**`Example`**

```ts
// Define a new navigation control.
var navigation = new maplibregl.NavigationControl();
// Add zoom and rotation controls to the map.
map.addControl(navigation);
// Remove zoom and rotation controls from the map.
map.removeControl(navigation);
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `control` | [`IControl`](../interfaces/maplibregl.IControl.md) | The [IControl](../interfaces/maplibregl.IControl.md) to remove. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:621](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L621)

___

### removeFeatureState

▸ **removeFeatureState**(`target`, `key?`): [`Map`](maplibregl.Map.md)

Removes the `state` of a feature, setting it back to the default behavior.
If only a `target.source` is specified, it will remove the state for all features from that source.
If `target.id` is also specified, it will remove all keys for that feature's state.
If `key` is also specified, it removes only that key from that feature's state.
Features are identified by their `feature.id` attribute, which can be any number or string.

**`Example`**

```ts
// Reset the entire state object for all features
// in the `my-source` source
map.removeFeatureState({
  source: 'my-source'
});
```

**`Example`**

```ts
// When the mouse leaves the `my-layer` layer,
// reset the entire state object for the
// feature under the mouse
map.on('mouseleave', 'my-layer', function(e) {
  map.removeFeatureState({
    source: 'my-source',
    sourceLayer: 'my-source-layer',
    id: e.features[0].id
  });
});
```

**`Example`**

```ts
// When the mouse leaves the `my-layer` layer,
// reset only the `hover` key-value pair in the
// state for the feature under the mouse
map.on('mouseleave', 'my-layer', function(e) {
  map.removeFeatureState({
    source: 'my-source',
    sourceLayer: 'my-source-layer',
    id: e.features[0].id
  }, 'hover');
});
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `target` | `FeatureIdentifier` | Identifier of where to remove state. It can be a source, a feature, or a specific key of feature. Feature objects returned from [queryRenderedFeatures](maplibregl.Map.md#queryrenderedfeatures) or event handlers can be used as feature identifiers. |
| `key?` | `string` | (optional) The key in the feature state to reset. |

#### Returns

[`Map`](maplibregl.Map.md)

#### Defined in

[src/ui/map.ts:2570](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2570)

___

### removeImage

▸ **removeImage**(`id`): `void`

Remove an image from a style. This can be an image from the style's original
sprite or any images
that have been added at runtime using [addImage](maplibregl.Map.md#addimage).

**`Example`**

```ts
// If an image with the ID 'cat' exists in
// the style's sprite, remove it.
if (map.hasImage('cat')) map.removeImage('cat');
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | The ID of the image. |

#### Returns

`void`

#### Defined in

[src/ui/map.ts:2025](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2025)

___

### removeLayer

▸ **removeLayer**(`id`): [`Map`](maplibregl.Map.md)

Removes the layer with the given ID from the map's style.

If no such layer exists, an `error` event is fired.

**`Fires`**

error

**`Example`**

```ts
// If a layer with ID 'state-data' exists, remove it.
if (map.getLayer('state-data')) map.removeLayer('state-data');
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | id of the layer to remove |

#### Returns

[`Map`](maplibregl.Map.md)

#### Defined in

[src/ui/map.ts:2212](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2212)

___

### removeSource

▸ **removeSource**(`id`): [`Map`](maplibregl.Map.md)

Removes a source from the map's style.

**`Example`**

```ts
map.removeSource('bathymetry-data');
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | The ID of the source to remove. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:1804](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1804)

___

### removeSprite

▸ **removeSprite**(`id`): [`Map`](maplibregl.Map.md)

Removes the sprite from the map's style.

**`Fires`**

style

**`Example`**

```ts
map.removeSprite('sprite-two');
```

**`Example`**

```ts
map.removeSprite('default');
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | The ID of the sprite to remove. If the sprite is declared as a single URL, the ID must be "default". |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:2420](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2420)

___

### resetNorth

▸ **resetNorth**(`options?`, `eventData?`): [`Map`](maplibregl.Map.md)

Rotates the map so that north is up (0° bearing), with an animated transition.

**`Memberof`**

Map#

**`Fires`**

movestart

**`Fires`**

moveend

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options?` | [`AnimationOptions`](../modules/maplibregl.md#animationoptions) | Options object |
| `eventData?` | `any` | Additional properties to be added to event objects of events triggered by this method. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Inherited from

Camera.resetNorth

#### Defined in

[src/ui/camera.ts:462](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L462)

___

### resetNorthPitch

▸ **resetNorthPitch**(`options?`, `eventData?`): [`Map`](maplibregl.Map.md)

Rotates and pitches the map so that north is up (0° bearing) and pitch is 0°, with an animated transition.

**`Memberof`**

Map#

**`Fires`**

movestart

**`Fires`**

moveend

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options?` | [`AnimationOptions`](../modules/maplibregl.md#animationoptions) | Options object |
| `eventData?` | `any` | Additional properties to be added to event objects of events triggered by this method. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Inherited from

Camera.resetNorthPitch

#### Defined in

[src/ui/camera.ts:477](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L477)

___

### resize

▸ **resize**(`eventData?`): [`Map`](maplibregl.Map.md)

Resizes the map according to the dimensions of its
`container` element.

Checks if the map container size changed and updates the map if it has changed.
This method must be called after the map's `container` is resized programmatically
or when the map is shown after being initially hidden with CSS.

**`Example`**

```ts
// Resize the map when the map container is shown
// after being initially hidden with CSS.
var mapDiv = document.getElementById('map');
if (mapDiv.style.visibility === true) map.resize();
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `eventData?` | `any` | Additional properties to be passed to `movestart`, `move`, `resize`, and `moveend` events that get triggered as a result of resize. This can be useful for differentiating the source of an event (for example, user-initiated or programmatically-triggered events). |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:674](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L674)

___

### rotateTo

▸ **rotateTo**(`bearing`, `options?`, `eventData?`): [`Map`](maplibregl.Map.md)

Rotates the map to the specified bearing, with an animated transition. The bearing is the compass direction
that is \"up\"; for example, a bearing of 90° orients the map so that east is up.

**`Memberof`**

Map#

**`Fires`**

movestart

**`Fires`**

moveend

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `bearing` | `number` | The desired bearing. |
| `options?` | [`AnimationOptions`](../modules/maplibregl.md#animationoptions) | Options object |
| `eventData?` | `any` | Additional properties to be added to event objects of events triggered by this method. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Inherited from

Camera.rotateTo

#### Defined in

[src/ui/camera.ts:446](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L446)

___

### setBearing

▸ **setBearing**(`bearing`, `eventData?`): [`Map`](maplibregl.Map.md)

Sets the map's bearing (rotation). The bearing is the compass direction that is "up"; for example, a bearing
of 90° orients the map so that east is up.

Equivalent to `jumpTo({bearing: bearing})`.

**`Memberof`**

Map#

**`Fires`**

movestart

**`Fires`**

moveend

**`Example`**

```ts
// rotate the map to 90 degrees
map.setBearing(90);
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `bearing` | `number` | The desired bearing. |
| `eventData?` | `any` | Additional properties to be added to event objects of events triggered by this method. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Inherited from

Camera.setBearing

#### Defined in

[src/ui/camera.ts:401](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L401)

___

### setCenter

▸ **setCenter**(`center`, `eventData?`): [`Map`](maplibregl.Map.md)

Sets the map's geographical centerpoint. Equivalent to `jumpTo({center: center})`.

**`Memberof`**

Map#

**`Fires`**

movestart

**`Fires`**

moveend

**`Example`**

```ts
map.setCenter([-74, 38]);
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `center` | [`LngLatLike`](../modules/maplibregl.md#lnglatlike) | The centerpoint to set. |
| `eventData?` | `any` | Additional properties to be added to event objects of events triggered by this method. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Inherited from

Camera.setCenter

#### Defined in

[src/ui/camera.ts:226](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L226)

___

### setCooperativeGestures

▸ **setCooperativeGestures**(`gestureOptions?`): [`Map`](maplibregl.Map.md)

Sets or clears the map's cooperativeGestures option

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `gestureOptions?` | `boolean` \| [`GestureOptions`](../modules/maplibregl.md#gestureoptions) | If `true` or set to an options object, map is only accessible on desktop while holding Command/Ctrl and only accessible on mobile with two fingers. Interacting with the map using normal gestures will trigger an informational screen. With this option enabled, "drag to pitch" requires a three-finger gesture. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:961](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L961)

___

### setEventedParent

▸ `Private` **setEventedParent**(`parent?`, `data?`): [`Map`](maplibregl.Map.md)

Bubble all events fired by this instance of Evented to this parent instance of Evented.

#### Parameters

| Name | Type |
| :------ | :------ |
| `parent?` | [`Evented`](maplibregl.Evented.md) |
| `data?` | `any` |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Inherited from

Camera.setEventedParent

#### Defined in

[src/util/evented.ts:170](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L170)

___

### setFeatureState

▸ **setFeatureState**(`feature`, `state`): [`Map`](maplibregl.Map.md)

Sets the `state` of a feature.
A feature's `state` is a set of user-defined key-value pairs that are assigned to a feature at runtime.
When using this method, the `state` object is merged with any existing key-value pairs in the feature's state.
Features are identified by their `feature.id` attribute, which can be any number or string.

This method can only be used with sources that have a `feature.id` attribute. The `feature.id` attribute can be defined in three ways:
- For vector or GeoJSON sources, including an `id` attribute in the original data file.
- For vector or GeoJSON sources, using the [`promoteId`](https://maplibre.org/maplibre-style-spec/sources/#vector-promoteId) option at the time the source is defined.
- For GeoJSON sources, using the [`generateId`](https://maplibre.org/maplibre-style-spec/sources/#geojson-generateId) option to auto-assign an `id` based on the feature's index in the source data. If you change feature data using `map.getSource('some id').setData(..)`, you may need to re-apply state taking into account updated `id` values.

_Note: You can use the [`feature-state` expression](https://maplibre.org/maplibre-style-spec/expressions/#feature-state) to access the values in a feature's state object for the purposes of styling._

**`Example`**

```ts
// When the mouse moves over the `my-layer` layer, update
// the feature state for the feature under the mouse
map.on('mousemove', 'my-layer', function(e) {
  if (e.features.length > 0) {
    map.setFeatureState({
      source: 'my-source',
      sourceLayer: 'my-source-layer',
      id: e.features[0].id,
    }, {
      hover: true
    });
  }
});
```

**`See`**

[Create a hover effect](https://maplibre.org/maplibre-gl-js-docs/example/hover-styles/)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `feature` | `FeatureIdentifier` | Feature identifier. Feature objects returned from [queryRenderedFeatures](maplibregl.Map.md#queryrenderedfeatures) or event handlers can be used as feature identifiers. |
| `state` | `any` | A set of key-value pairs. The values should be valid JSON types. |

#### Returns

[`Map`](maplibregl.Map.md)

#### Defined in

[src/ui/map.ts:2518](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2518)

___

### setFilter

▸ **setFilter**(`layerId`, `filter?`, `options?`): [`Map`](maplibregl.Map.md)

Sets the filter for the specified style layer.

Filters control which features a style layer renders from its source.
Any feature for which the filter expression evaluates to `true` will be
rendered on the map. Those that are false will be hidden.

Use `setFilter` to show a subset of your source data.

To clear the filter, pass `null` or `undefined` as the second parameter.

**`Example`**

```ts
// display only features with the 'name' property 'USA'
map.setFilter('my-layer', ['==', ['get', 'name'], 'USA']);
```

**`Example`**

```ts
// display only features with five or more 'available-spots'
map.setFilter('bike-docks', ['>=', ['get', 'available-spots'], 5]);
```

**`Example`**

```ts
// remove the filter for the 'bike-docks' style layer
map.setFilter('bike-docks', null);
```

**`See`**

[Create a timeline animation](https://maplibre.org/maplibre-gl-js-docs/example/timeline-animation/)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `layerId` | `string` | The ID of the layer to which the filter will be applied. |
| `filter?` | `FilterSpecification` | The filter, conforming to the MapLibre Style Specification's [filter definition](https://maplibre.org/maplibre-style-spec/layers/#filter). If `null` or `undefined` is provided, the function removes any existing filter from the layer. |
| `options?` | `StyleSetterOptions` | Options object. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:2289](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2289)

___

### setGlyphs

▸ **setGlyphs**(`glyphsUrl`, `options?`): [`Map`](maplibregl.Map.md)

Sets the value of the style's glyphs property.

**`Example`**

```ts
map.setGlyphs('https://demotiles.maplibre.org/font/{fontstack}/{range}.pbf');
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `glyphsUrl` | `string` | Glyph URL to set. Must conform to the [MapLibre Style Specification](https://maplibre.org/maplibre-style-spec/glyphs/). |
| `options?` | `StyleSetterOptions` | Options object. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:2373](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2373)

___

### setLayerZoomRange

▸ **setLayerZoomRange**(`layerId`, `minzoom`, `maxzoom`): [`Map`](maplibregl.Map.md)

Sets the zoom extent for the specified style layer. The zoom extent includes the
[minimum zoom level](https://maplibre.org/maplibre-style-spec/#layer-minzoom)
and [maximum zoom level](https://maplibre.org/maplibre-style-spec/#layer-maxzoom))
at which the layer will be rendered.

Note: For style layers using vector sources, style layers cannot be rendered at zoom levels lower than the
minimum zoom level of the _source layer_ because the data does not exist at those zoom levels. If the minimum
zoom level of the source layer is higher than the minimum zoom level defined in the style layer, the style
layer will not be rendered at all zoom levels in the zoom range.

**`Example`**

```ts
map.setLayerZoomRange('my-layer', 2, 5);
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `layerId` | `string` | The ID of the layer to which the zoom extent will be applied. |
| `minzoom` | `number` | The minimum zoom to set (0-24). |
| `maxzoom` | `number` | The maximum zoom to set (0-24). |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:2254](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2254)

___

### setLayoutProperty

▸ **setLayoutProperty**(`layerId`, `name`, `value`, `options?`): [`Map`](maplibregl.Map.md)

Sets the value of a layout property in the specified style layer.

**`Example`**

```ts
map.setLayoutProperty('my-layer', 'visibility', 'none');
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `layerId` | `string` | The ID of the layer to set the layout property in. |
| `name` | `string` | The name of the layout property to set. |
| `value` | `any` | The value of the layout property. Must be of a type appropriate for the property, as defined in the [MapLibre Style Specification](https://maplibre.org/maplibre-style-spec/). |
| `options?` | `StyleSetterOptions` | Options object. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:2347](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2347)

___

### setLight

▸ **setLight**(`light`, `options?`): [`Map`](maplibregl.Map.md)

Sets the any combination of light values.

**`Example`**

```ts
var layerVisibility = map.getLayoutProperty('my-layer', 'visibility');
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `light` | `LightSpecification` | Light properties to set. Must conform to the [MapLibre Style Specification](https://maplibre.org/maplibre-style-spec/#light). |
| `options?` | `StyleSetterOptions` | Options object. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:2465](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2465)

___

### setMaxBounds

▸ **setMaxBounds**(`bounds?`): [`Map`](maplibregl.Map.md)

Sets or clears the map's geographical bounds.

Pan and zoom operations are constrained within these bounds.
If a pan or zoom is performed that would
display regions outside these bounds, the map will
instead display a position and zoom level
as close as possible to the operation's request while still
remaining within the bounds.

**`Example`**

```ts
// Define bounds that conform to the `LngLatBoundsLike` object.
var bounds = [
  [-74.04728, 40.68392], // [west, south]
  [-73.91058, 40.87764]  // [east, north]
];
// Set the map's max bounds.
map.setMaxBounds(bounds);
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `bounds?` | [`LngLatBoundsLike`](../modules/maplibregl.md#lnglatboundslike) | The maximum bounds to set. If `null` or `undefined` is provided, the function removes the map's maximum bounds. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:763](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L763)

___

### setMaxPitch

▸ **setMaxPitch**(`maxPitch?`): [`Map`](maplibregl.Map.md)

Sets or clears the map's maximum pitch.
If the map's current pitch is higher than the new maximum,
the map will pitch to the new maximum.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `maxPitch?` | `number` | The maximum pitch to set (0-85). Values greater than 60 degrees are experimental and may result in rendering issues. If you encounter any, please raise an issue with details in the MapLibre project. If `null` or `undefined` is provided, the function removes the current maximum pitch (sets it to 60). |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:887](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L887)

___

### setMaxZoom

▸ **setMaxZoom**(`maxZoom?`): [`Map`](maplibregl.Map.md)

Sets or clears the map's maximum zoom level.
If the map's current zoom level is higher than the new maximum,
the map will zoom to the new maximum.

**`Example`**

```ts
map.setMaxZoom(18.75);
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `maxZoom?` | `number` | The maximum zoom level to set. If `null` or `undefined` is provided, the function removes the current maximum zoom (sets it to 22). |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:819](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L819)

___

### setMinPitch

▸ **setMinPitch**(`minPitch?`): [`Map`](maplibregl.Map.md)

Sets or clears the map's minimum pitch.
If the map's current pitch is lower than the new minimum,
the map will pitch to the new minimum.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `minPitch?` | `number` | The minimum pitch to set (0-85). Values greater than 60 degrees are experimental and may result in rendering issues. If you encounter any, please raise an issue with details in the MapLibre project. If `null` or `undefined` is provided, the function removes the current minimum pitch (i.e. sets it to 0). |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:852](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L852)

___

### setMinZoom

▸ **setMinZoom**(`minZoom?`): [`Map`](maplibregl.Map.md)

Sets or clears the map's minimum zoom level.
If the map's current zoom level is lower than the new minimum,
the map will zoom to the new minimum.

It is not always possible to zoom out and reach the set `minZoom`.
Other factors such as map height may restrict zooming. For example,
if the map is 512px tall it will not be possible to zoom below zoom 0
no matter what the `minZoom` is set to.

**`Example`**

```ts
map.setMinZoom(12.25);
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `minZoom?` | `number` | The minimum zoom level to set (-2 - 24). If `null` or `undefined` is provided, the function removes the current minimum zoom (i.e. sets it to -2). |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:784](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L784)

___

### setPadding

▸ **setPadding**(`padding`, `eventData?`): [`Map`](maplibregl.Map.md)

Sets the padding in pixels around the viewport.

Equivalent to `jumpTo({padding: padding})`.

**`Memberof`**

Map#

**`Fires`**

movestart

**`Fires`**

moveend

**`Example`**

```ts
// Sets a left padding of 300px, and a top padding of 50px
map.setPadding({ left: 300, top: 50 });
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `padding` | [`PaddingOptions`](../modules/maplibregl.md#paddingoptions) | The desired padding. Format: { left: number, right: number, top: number, bottom: number } |
| `eventData?` | `any` | Additional properties to be added to event objects of events triggered by this method. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Inherited from

Camera.setPadding

#### Defined in

[src/ui/camera.ts:429](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L429)

___

### setPaintProperty

▸ **setPaintProperty**(`layerId`, `name`, `value`, `options?`): [`Map`](maplibregl.Map.md)

Sets the value of a paint property in the specified style layer.

**`Example`**

```ts
map.setPaintProperty('my-layer', 'fill-color', '#faafee');
```

**`See`**

 - [Change a layer's color with buttons](https://maplibre.org/maplibre-gl-js-docs/example/color-switcher/)
 - [Create a draggable point](https://maplibre.org/maplibre-gl-js-docs/example/drag-a-point/)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `layerId` | `string` | The ID of the layer to set the paint property in. |
| `name` | `string` | The name of the paint property to set. |
| `value` | `any` | The value of the paint property to set. Must be of a type appropriate for the property, as defined in the [MapLibre Style Specification](https://maplibre.org/maplibre-style-spec/). |
| `options?` | `StyleSetterOptions` | Options object. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:2319](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2319)

___

### setPitch

▸ **setPitch**(`pitch`, `eventData?`): [`Map`](maplibregl.Map.md)

Sets the map's pitch (tilt). Equivalent to `jumpTo({pitch: pitch})`.

**`Memberof`**

Map#

**`Fires`**

pitchstart

**`Fires`**

movestart

**`Fires`**

moveend

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `pitch` | `number` | The pitch to set, measured in degrees away from the plane of the screen (0-60). |
| `eventData?` | `any` | Additional properties to be added to event objects of events triggered by this method. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Inherited from

Camera.setPitch

#### Defined in

[src/ui/camera.ts:523](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L523)

___

### setPixelRatio

▸ **setPixelRatio**(`pixelRatio`): `void`

Sets the map's pixel ratio. This allows to override `devicePixelRatio`.
After this call, the canvas' `width` attribute will be `container.clientWidth * pixelRatio`
and its height attribute will be `container.clientHeight * pixelRatio`.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `pixelRatio` | `number` | The pixel ratio. |

#### Returns

`void`

#### Defined in

[src/ui/map.ts:712](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L712)

___

### setRenderWorldCopies

▸ **setRenderWorldCopies**(`renderWorldCopies?`): [`Map`](maplibregl.Map.md)

Sets the state of `renderWorldCopies`.

**`Example`**

```ts
map.setRenderWorldCopies(true);
```

**`See`**

[Render world copies](https://maplibre.org/maplibre-gl-js-docs/example/render-world-copies/)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `renderWorldCopies?` | `boolean` | If `true`, multiple copies of the world will be rendered side by side beyond -180 and 180 degrees longitude. If set to `false`: - When the map is zoomed out far enough that a single representation of the world does not fill the map's entire container, there will be blank space beyond 180 and -180 degrees longitude. - Features that cross 180 and -180 degrees longitude will be cut in two (with one portion on the right edge of the map and the other on the left edge of the map) at every zoom level. `undefined` is treated as `true`, `null` is treated as `false`. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:941](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L941)

___

### setSprite

▸ **setSprite**(`spriteUrl`, `options?`): [`Map`](maplibregl.Map.md)

Sets the value of the style's sprite property.

**`Example`**

```ts
map.setSprite('YOUR_SPRITE_URL');
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `spriteUrl` | `string` | Sprite URL to set. |
| `options?` | `StyleSetterOptions` | Options object. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:2445](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L2445)

___

### setStyle

▸ **setStyle**(`style`, `options?`): [`Map`](maplibregl.Map.md)

Updates the map's MapLibre style object with a new value.

If a style is already set when this is used and options.diff is set to true, the map renderer will attempt to compare the given style
against the map's current state and perform only the changes necessary to make the map style match the desired state. Changes in sprites
(images used for icons and patterns) and glyphs (fonts for label text) **cannot** be diffed. If the sprites or fonts used in the current
style and the given style are different in any way, the map renderer will force a full update, removing the current style and building
the given one from scratch.

**`Example`**

```ts
map.setStyle("https://demotiles.maplibre.org/style.json");

map.setStyle('https://demotiles.maplibre.org/style.json', {
  transformStyle: (previousStyle, nextStyle) => ({
      ...nextStyle,
      sources: {
          ...nextStyle.sources,
          // copy a source from previous style
          'osm': previousStyle.sources.osm
      },
      layers: [
          // background layer
          nextStyle.layers[0],
          // copy a layer from previous style
          previousStyle.layers[0],
          // other layers from the next style
          ...nextStyle.layers.slice(1).map(layer => {
              // hide the layers we don't need from demotiles style
              if (layer.id.startsWith('geolines')) {
                  layer.layout = {...layer.layout || {}, visibility: 'none'};
              // filter out US polygons
              } else if (layer.id.startsWith('coastline') || layer.id.startsWith('countries')) {
                  layer.filter = ['!=', ['get', 'ADM0_A3'], 'USA'];
              }
              return layer;
          })
      ]
  })
});
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `style` | `string` \| `StyleSpecification` | A JSON object conforming to the schema described in the [MapLibre Style Specification](https://maplibre.org/maplibre-style-spec/), or a URL to such JSON. |
| `options?` | `StyleSwapOptions` & `StyleOptions` | Options object. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:1509](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1509)

___

### setTerrain

▸ **setTerrain**(`options?`): [`Map`](maplibregl.Map.md)

Loads a 3D terrain mesh, based on a "raster-dem" source.

**`Example`**

```ts
map.setTerrain({ source: 'terrain' });
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options?` | `TerrainSpecification` | Options object. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:1710](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1710)

___

### setTransformRequest

▸ **setTransformRequest**(`transformRequest`): [`Map`](maplibregl.Map.md)

Updates the requestManager's transform request with a new function

**`Example`**

```ts
map.setTransformRequest((url: string, resourceType: string) => {});
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `transformRequest` | `RequestTransformFunction` | A callback run before the Map makes a request for an external URL. The callback can be used to modify the url, set headers, or set the credentials property for cross-origin requests. Expected to return an object with a `url` property and optionally `headers` and `credentials` properties |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Defined in

[src/ui/map.ts:1536](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1536)

___

### setZoom

▸ **setZoom**(`zoom`, `eventData?`): [`Map`](maplibregl.Map.md)

Sets the map's zoom level. Equivalent to `jumpTo({zoom: zoom})`.

**`Memberof`**

Map#

**`Fires`**

movestart

**`Fires`**

zoomstart

**`Fires`**

move

**`Fires`**

zoom

**`Fires`**

moveend

**`Fires`**

zoomend

**`Example`**

```ts
// Zoom to the zoom level 5 without an animated transition
map.setZoom(5);
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `zoom` | `number` | The zoom level to set (0-20). |
| `eventData?` | `any` | Additional properties to be added to event objects of events triggered by this method. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Inherited from

Camera.setZoom

#### Defined in

[src/ui/camera.ts:297](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L297)

___

### snapToNorth

▸ **snapToNorth**(`options?`, `eventData?`): [`Map`](maplibregl.Map.md)

Snaps the map so that north is up (0° bearing), if the current bearing is close enough to it (i.e. within the
`bearingSnap` threshold).

**`Memberof`**

Map#

**`Fires`**

movestart

**`Fires`**

moveend

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options?` | [`AnimationOptions`](../modules/maplibregl.md#animationoptions) | Options object |
| `eventData?` | `any` | Additional properties to be added to event objects of events triggered by this method. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Inherited from

Camera.snapToNorth

#### Defined in

[src/ui/camera.ts:497](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L497)

___

### stop

▸ **stop**(): [`Map`](maplibregl.Map.md)

Stops any animated transition underway.

**`Memberof`**

Map#

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Inherited from

Camera.stop

#### Defined in

[src/ui/camera.ts:1337](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L1337)

___

### triggerRepaint

▸ **triggerRepaint**(): `void`

Trigger the rendering of a single frame. Use this method with custom layers to
repaint the map when the layer changes. Calling this multiple times before the
next frame is rendered will still result in only a single frame being rendered.

**`Example`**

```ts
map.triggerRepaint();
```

**`See`**

 - [Add a 3D model](https://maplibre.org/maplibre-gl-js-docs/example/add-3d-model/)
 - [Add an animated icon to the map](https://maplibre.org/maplibre-gl-js-docs/example/add-image-animated/)

#### Returns

`void`

#### Defined in

[src/ui/map.ts:3035](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L3035)

___

### unproject

▸ **unproject**(`point`): [`LngLat`](maplibregl.LngLat.md)

Returns a [LngLat](maplibregl.LngLat.md) representing geographical coordinates that correspond
to the specified pixel coordinates.

**`Example`**

```ts
map.on('click', function(e) {
  // When the map is clicked, get the geographic coordinate.
  var coordinate = map.unproject(e.point);
});
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `point` | [`PointLike`](../modules/maplibregl.md#pointlike) | The pixel coordinates to unproject. |

#### Returns

[`LngLat`](maplibregl.LngLat.md)

The [LngLat](maplibregl.LngLat.md) corresponding to `point`.

#### Defined in

[src/ui/map.ts:998](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L998)

___

### updateImage

▸ **updateImage**(`id`, `image`): [`Map`](maplibregl.Map.md)

Update an existing image in a style. This image can be displayed on the map like any other icon in the style's
sprite using the image's ID with
[`icon-image`](https://maplibre.org/maplibre-style-spec/#layout-symbol-icon-image),
[`background-pattern`](https://maplibre.org/maplibre-style-spec/#paint-background-background-pattern),
[`fill-pattern`](https://maplibre.org/maplibre-style-spec/#paint-fill-fill-pattern),
or [`line-pattern`](https://maplibre.org/maplibre-style-spec/#paint-line-line-pattern).

**`Example`**

```ts
// If an image with the ID 'cat' already exists in the style's sprite,
// replace that image with a new image, 'other-cat-icon.png'.
if (map.hasImage('cat')) map.updateImage('cat', './other-cat-icon.png');
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `id` | `string` | The ID of the image. |
| `image` | `ImageBitmap` \| `HTMLImageElement` \| `ImageData` \| [`StyleImageInterface`](../interfaces/maplibregl.StyleImageInterface.md) \| { `data`: `Uint8Array` \| `Uint8ClampedArray` ; `height`: `number` ; `width`: `number`  } | The image as an `HTMLImageElement`, `ImageData`, `ImageBitmap` or object with `width`, `height`, and `data` properties with the same format as `ImageData`. |

#### Returns

[`Map`](maplibregl.Map.md)

#### Defined in

[src/ui/map.ts:1941](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L1941)

___

### zoomIn

▸ **zoomIn**(`options?`, `eventData?`): [`Map`](maplibregl.Map.md)

Increases the map's zoom level by 1.

**`Memberof`**

Map#

**`Fires`**

movestart

**`Fires`**

zoomstart

**`Fires`**

move

**`Fires`**

zoom

**`Fires`**

moveend

**`Fires`**

zoomend

**`Example`**

```ts
// zoom the map in one level with a custom animation duration
map.zoomIn({duration: 1000});
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options?` | [`AnimationOptions`](../modules/maplibregl.md#animationoptions) | Options object |
| `eventData?` | `any` | Additional properties to be added to event objects of events triggered by this method. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Inherited from

Camera.zoomIn

#### Defined in

[src/ui/camera.ts:348](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L348)

___

### zoomOut

▸ **zoomOut**(`options?`, `eventData?`): [`Map`](maplibregl.Map.md)

Decreases the map's zoom level by 1.

**`Memberof`**

Map#

**`Fires`**

movestart

**`Fires`**

zoomstart

**`Fires`**

move

**`Fires`**

zoom

**`Fires`**

moveend

**`Fires`**

zoomend

**`Example`**

```ts
// zoom the map out one level with a custom animation offset
map.zoomOut({offset: [80, 60]});
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options?` | [`AnimationOptions`](../modules/maplibregl.md#animationoptions) | Options object |
| `eventData?` | `any` | Additional properties to be added to event objects of events triggered by this method. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Inherited from

Camera.zoomOut

#### Defined in

[src/ui/camera.ts:370](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L370)

___

### zoomTo

▸ **zoomTo**(`zoom`, `options?`, `eventData?`): [`Map`](maplibregl.Map.md)

Zooms the map to the specified zoom level, with an animated transition.

**`Memberof`**

Map#

**`Fires`**

movestart

**`Fires`**

zoomstart

**`Fires`**

move

**`Fires`**

zoom

**`Fires`**

moveend

**`Fires`**

zoomend

**`Example`**

```ts
// Zoom to the zoom level 5 without an animated transition
map.zoomTo(5);
// Zoom to the zoom level 8 with an animated transition
map.zoomTo(8, {
  duration: 2000,
  offset: [100, 50]
});
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `zoom` | `number` | The zoom level to transition to. |
| `options?` | [`AnimationOptions`](../modules/maplibregl.md#animationoptions) | Options object |
| `eventData?` | `any` | Additional properties to be added to event objects of events triggered by this method. |

#### Returns

[`Map`](maplibregl.Map.md)

`this`

#### Inherited from

Camera.zoomTo

#### Defined in

[src/ui/camera.ts:325](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L325)

## Properties

### \_imageQueueHandle

• **\_imageQueueHandle**: `number`

image queue throttling handle. To be used later when clean up

#### Defined in

[src/ui/map.ts:364](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L364)

___

### \_requestedCameraState

• `Optional` **\_requestedCameraState**: [`Transform`](maplibregl.Transform.md)

Used to track accumulated changes during continuous interaction

#### Inherited from

Camera.\_requestedCameraState

#### Defined in

[src/ui/camera.ts:177](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L177)

___

### boxZoom

• **boxZoom**: [`BoxZoomHandler`](maplibregl.BoxZoomHandler.md)

The map's [BoxZoomHandler](maplibregl.BoxZoomHandler.md), which implements zooming using a drag gesture with the Shift key pressed.
Find more details and examples using `boxZoom` in the [BoxZoomHandler](maplibregl.BoxZoomHandler.md) section.

#### Defined in

[src/ui/map.ts:376](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L376)

___

### doubleClickZoom

• **doubleClickZoom**: [`DoubleClickZoomHandler`](maplibregl.DoubleClickZoomHandler.md)

The map's [DoubleClickZoomHandler](maplibregl.DoubleClickZoomHandler.md), which allows the user to zoom by double clicking.
Find more details and examples using `doubleClickZoom` in the [DoubleClickZoomHandler](maplibregl.DoubleClickZoomHandler.md) section.

#### Defined in

[src/ui/map.ts:401](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L401)

___

### dragPan

• **dragPan**: [`DragPanHandler`](maplibregl.DragPanHandler.md)

The map's [DragPanHandler](maplibregl.DragPanHandler.md), which implements dragging the map with a mouse or touch gesture.
Find more details and examples using `dragPan` in the [DragPanHandler](maplibregl.DragPanHandler.md) section.

#### Defined in

[src/ui/map.ts:389](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L389)

___

### dragRotate

• **dragRotate**: [`DragRotateHandler`](maplibregl.DragRotateHandler.md)

The map's [DragRotateHandler](maplibregl.DragRotateHandler.md), which implements rotating the map while dragging with the right
mouse button or with the Control key pressed. Find more details and examples using `dragRotate`
in the [DragRotateHandler](maplibregl.DragRotateHandler.md) section.

#### Defined in

[src/ui/map.ts:383](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L383)

___

### keyboard

• **keyboard**: [`KeyboardHandler`](maplibregl.KeyboardHandler.md)

The map's [KeyboardHandler](maplibregl.KeyboardHandler.md), which allows the user to zoom, rotate, and pan the map using keyboard
shortcuts. Find more details and examples using `keyboard` in the [KeyboardHandler](maplibregl.KeyboardHandler.md) section.

#### Defined in

[src/ui/map.ts:395](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L395)

___

### scrollZoom

• **scrollZoom**: [`ScrollZoomHandler`](maplibregl.ScrollZoomHandler.md)

The map's [ScrollZoomHandler](maplibregl.ScrollZoomHandler.md), which implements zooming in and out with a scroll wheel or trackpad.
Find more details and examples using `scrollZoom` in the [ScrollZoomHandler](maplibregl.ScrollZoomHandler.md) section.

#### Defined in

[src/ui/map.ts:370](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L370)

___

### touchPitch

• **touchPitch**: [`TwoFingersTouchPitchHandler`](maplibregl.TwoFingersTouchPitchHandler.md)

The map's [TwoFingersTouchPitchHandler](maplibregl.TwoFingersTouchPitchHandler.md), which allows the user to pitch the map with touch gestures.
Find more details and examples using `touchPitch` in the [TwoFingersTouchPitchHandler](maplibregl.TwoFingersTouchPitchHandler.md) section.

#### Defined in

[src/ui/map.ts:413](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L413)

___

### touchZoomRotate

• **touchZoomRotate**: [`TwoFingersTouchZoomRotateHandler`](maplibregl.TwoFingersTouchZoomRotateHandler.md)

The map's [TwoFingersTouchZoomRotateHandler](maplibregl.TwoFingersTouchZoomRotateHandler.md), which allows the user to zoom or rotate the map with touch gestures.
Find more details and examples using `touchZoomRotate` in the [TwoFingersTouchZoomRotateHandler](maplibregl.TwoFingersTouchZoomRotateHandler.md) section.

#### Defined in

[src/ui/map.ts:407](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/map.ts#L407)

___

### transformCameraUpdate

• **transformCameraUpdate**: `CameraUpdateTransformFunction`

A callback used to defer camera updates or apply arbitrary constraints.
If specified, this Camera instance can be used as a stateless component in React etc.

#### Inherited from

Camera.transformCameraUpdate

#### Defined in

[src/ui/camera.ts:181](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/ui/camera.ts#L181)
