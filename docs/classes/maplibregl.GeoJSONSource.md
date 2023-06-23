[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / GeoJSONSource

# Class: GeoJSONSource

[maplibregl](../modules/maplibregl.md).GeoJSONSource

A source containing GeoJSON.
(See the [Style Specification](https://maplibre.org/maplibre-style-spec/#sources-geojson) for detailed documentation of options.)

**`Example`**

```ts
map.addSource('some id', {
    type: 'geojson',
    data: 'https://d2ad6b4ur7yvpq.cloudfront.net/naturalearth-3.3.0/ne_10m_ports.geojson'
});
```

**`Example`**

```ts
map.addSource('some id', {
   type: 'geojson',
   data: {
       "type": "FeatureCollection",
       "features": [{
           "type": "Feature",
           "properties": {},
           "geometry": {
               "type": "Point",
               "coordinates": [
                   -76.53063297271729,
                   39.18174077994108
               ]
           }
       }]
   }
});
```

**`Example`**

```ts
map.getSource('some id').setData({
  "type": "FeatureCollection",
  "features": [{
      "type": "Feature",
      "properties": { "name": "Null Island" },
      "geometry": {
          "type": "Point",
          "coordinates": [ 0, 0 ]
      }
  }]
});
```

**`See`**

 - [Draw GeoJSON points](https://maplibre.org/maplibre-gl-js-docs/example/geojson-markers/)
 - [Add a GeoJSON line](https://maplibre.org/maplibre-gl-js-docs/example/geojson-line/)
 - [Create a heatmap from points](https://maplibre.org/maplibre-gl-js-docs/example/heatmap/)
 - [Create and style clusters](https://maplibre.org/maplibre-gl-js-docs/example/cluster/)

## Hierarchy

- [`Evented`](maplibregl.Evented.md)

  ↳ **`GeoJSONSource`**

## Implements

- [`Source`](../interfaces/maplibregl.Source.md)

## Table of contents

### Constructors

- [constructor](maplibregl.GeoJSONSource.md#constructor)

### Methods

- [getClusterChildren](maplibregl.GeoJSONSource.md#getclusterchildren)
- [getClusterExpansionZoom](maplibregl.GeoJSONSource.md#getclusterexpansionzoom)
- [getClusterLeaves](maplibregl.GeoJSONSource.md#getclusterleaves)
- [listens](maplibregl.GeoJSONSource.md#listens)
- [off](maplibregl.GeoJSONSource.md#off)
- [on](maplibregl.GeoJSONSource.md#on)
- [once](maplibregl.GeoJSONSource.md#once)
- [setClusterOptions](maplibregl.GeoJSONSource.md#setclusteroptions)
- [setData](maplibregl.GeoJSONSource.md#setdata)
- [setEventedParent](maplibregl.GeoJSONSource.md#seteventedparent)
- [updateData](maplibregl.GeoJSONSource.md#updatedata)

## Constructors

### constructor

• `Private` **new GeoJSONSource**(`id`, `options`, `dispatcher`, `eventedParent`)

#### Parameters

| Name | Type |
| :------ | :------ |
| `id` | `string` |
| `options` | `GeoJSONSourceOptions` |
| `dispatcher` | [`Dispatcher`](maplibregl.Dispatcher.md) |
| `eventedParent` | [`Evented`](maplibregl.Evented.md) |

#### Overrides

Evented.constructor

#### Defined in

[src/source/geojson_source.ts:130](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/geojson_source.ts#L130)

## Methods

### getClusterChildren

▸ **getClusterChildren**(`clusterId`, `callback`): [`GeoJSONSource`](maplibregl.GeoJSONSource.md)

For clustered sources, fetches the children of the given cluster on the next zoom level (as an array of GeoJSON features).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `clusterId` | `number` | The value of the cluster's `cluster_id` property. |
| `callback` | `Callback`<`Feature`<`Geometry`, { `[name: string]`: `any`;  }\>[]\> | A callback to be called when the features are retrieved (`(error, features) => { ... }`). |

#### Returns

[`GeoJSONSource`](maplibregl.GeoJSONSource.md)

this

#### Defined in

[src/source/geojson_source.ts:276](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/geojson_source.ts#L276)

___

### getClusterExpansionZoom

▸ **getClusterExpansionZoom**(`clusterId`, `callback`): [`GeoJSONSource`](maplibregl.GeoJSONSource.md)

For clustered sources, fetches the zoom at which the given cluster expands.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `clusterId` | `number` | The value of the cluster's `cluster_id` property. |
| `callback` | `Callback`<`number`\> | A callback to be called when the zoom value is retrieved (`(error, zoom) => { ... }`). |

#### Returns

[`GeoJSONSource`](maplibregl.GeoJSONSource.md)

this

#### Defined in

[src/source/geojson_source.ts:264](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/geojson_source.ts#L264)

___

### getClusterLeaves

▸ **getClusterLeaves**(`clusterId`, `limit`, `offset`, `callback`): [`GeoJSONSource`](maplibregl.GeoJSONSource.md)

For clustered sources, fetches the original points that belong to the cluster (as an array of GeoJSON features).

**`Example`**

```ts
// Retrieve cluster leaves on click
map.on('click', 'clusters', function(e) {
  var features = map.queryRenderedFeatures(e.point, {
    layers: ['clusters']
  });

  var clusterId = features[0].properties.cluster_id;
  var pointCount = features[0].properties.point_count;
  var clusterSource = map.getSource('clusters');

  clusterSource.getClusterLeaves(clusterId, pointCount, 0, function(error, features) {
    // Print cluster leaves in the console
    console.log('Cluster leaves:', error, features);
  })
});
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `clusterId` | `number` | The value of the cluster's `cluster_id` property. |
| `limit` | `number` | The maximum number of features to return. |
| `offset` | `number` | The number of features to skip (e.g. for pagination). |
| `callback` | `Callback`<`Feature`<`Geometry`, { `[name: string]`: `any`;  }\>[]\> | A callback to be called when the features are retrieved (`(error, features) => { ... }`). |

#### Returns

[`GeoJSONSource`](maplibregl.GeoJSONSource.md)

this

#### Defined in

[src/source/geojson_source.ts:306](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/geojson_source.ts#L306)

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

▸ **off**(`type`, `listener`): [`GeoJSONSource`](maplibregl.GeoJSONSource.md)

Removes a previously registered event listener.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to remove listeners for. |
| `listener` | `Listener` | The listener function to remove. |

#### Returns

[`GeoJSONSource`](maplibregl.GeoJSONSource.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[off](maplibregl.Evented.md#off)

#### Defined in

[src/util/evented.ts:79](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L79)

___

### on

▸ **on**(`type`, `listener`): [`GeoJSONSource`](maplibregl.GeoJSONSource.md)

Adds a listener to a specified event type.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to add a listen for. |
| `listener` | `Listener` | The function to be called when the event is fired. The listener function is called with the data object passed to `fire`, extended with `target` and `type` properties. |

#### Returns

[`GeoJSONSource`](maplibregl.GeoJSONSource.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[on](maplibregl.Evented.md#on)

#### Defined in

[src/util/evented.ts:65](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L65)

___

### once

▸ **once**(`type`, `listener?`): `Promise`<`any`\> \| [`GeoJSONSource`](maplibregl.GeoJSONSource.md)

Adds a listener that will be called only once to a specified event type.

The listener will be called first time the event fires after the listener is registered.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | The event type to listen for. |
| `listener?` | `Listener` | The function to be called when the event is fired the first time. |

#### Returns

`Promise`<`any`\> \| [`GeoJSONSource`](maplibregl.GeoJSONSource.md)

`this` or a promise if a listener is not provided

#### Inherited from

[Evented](maplibregl.Evented.md).[once](maplibregl.Evented.md#once)

#### Defined in

[src/util/evented.ts:95](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L95)

___

### setClusterOptions

▸ **setClusterOptions**(`options`): [`GeoJSONSource`](maplibregl.GeoJSONSource.md)

To disable/enable clustering on the source options

**`Example`**

```ts
map.getSource('some id').setClusterOptions({cluster: false});
map.getSource('some id').setClusterOptions({cluster: false, clusterRadius: 50, clusterMaxZoom: 14});
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options` | `SetClusterOptions` | The options to set |

#### Returns

[`GeoJSONSource`](maplibregl.GeoJSONSource.md)

this

#### Defined in

[src/source/geojson_source.ts:247](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/geojson_source.ts#L247)

___

### setData

▸ **setData**(`data`): [`GeoJSONSource`](maplibregl.GeoJSONSource.md)

Sets the GeoJSON data and re-renders the map.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `data` | `string` \| `GeoJSON` | A GeoJSON data object or a URL to one. The latter is preferable in the case of large GeoJSON files. |

#### Returns

[`GeoJSONSource`](maplibregl.GeoJSONSource.md)

this

#### Defined in

[src/source/geojson_source.ts:210](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/geojson_source.ts#L210)

___

### setEventedParent

▸ `Private` **setEventedParent**(`parent?`, `data?`): [`GeoJSONSource`](maplibregl.GeoJSONSource.md)

Bubble all events fired by this instance of Evented to this parent instance of Evented.

#### Parameters

| Name | Type |
| :------ | :------ |
| `parent?` | [`Evented`](maplibregl.Evented.md) |
| `data?` | `any` |

#### Returns

[`GeoJSONSource`](maplibregl.GeoJSONSource.md)

`this`

#### Inherited from

[Evented](maplibregl.Evented.md).[setEventedParent](maplibregl.Evented.md#seteventedparent)

#### Defined in

[src/util/evented.ts:170](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/util/evented.ts#L170)

___

### updateData

▸ **updateData**(`diff`): [`GeoJSONSource`](maplibregl.GeoJSONSource.md)

Updates the source's GeoJSON, and re-renders the map.

For sources with lots of features, this method can be used to make updates more quickly.

This approach requires unique IDs for every feature in the source. The IDs can either be specified on the feature,
or by using the promoteId option to specify which property should be used as the ID.

It is an error to call updateData on a source that did not have unique IDs for each of its features already.

Updates are applied on a best-effort basis, updating an ID that does not exist will not result in an error.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `diff` | `GeoJSONSourceDiff` | The changes that need to be applied. |

#### Returns

[`GeoJSONSource`](maplibregl.GeoJSONSource.md)

this

#### Defined in

[src/source/geojson_source.ts:232](https://github.com/maplibre/maplibre-gl-js/blob/972e15f62/src/source/geojson_source.ts#L232)
