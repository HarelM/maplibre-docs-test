[maplibre-gl-js@3.1.x](../README.md) / [Exports](../modules.md) / [maplibregl](../modules/maplibregl.md) / SymbolBucket

# Class: SymbolBucket

[maplibregl](../modules/maplibregl.md).SymbolBucket

Unlike other buckets, which simply implement #addFeature with type-specific
logic for (essentially) triangulating feature geometries, SymbolBucket
requires specialized behavior:

1. WorkerTile#parse(), the logical owner of the bucket creation process,
   calls SymbolBucket#populate(), which resolves text and icon tokens on
   each feature, adds each glyphs and symbols needed to the passed-in
   collections options.glyphDependencies and options.iconDependencies, and
   stores the feature data for use in subsequent step (this.features).

2. WorkerTile asynchronously requests from the main thread all of the glyphs
   and icons needed (by this bucket and any others). When glyphs and icons
   have been received, the WorkerTile creates a CollisionIndex and invokes:

3. performSymbolLayout(bucket, stacks, icons) perform texts shaping and
   layout on a Symbol Bucket. This step populates:
     `this.symbolInstances`: metadata on generated symbols
     `this.collisionBoxArray`: collision data for use by foreground
     `this.text`: SymbolBuffers for text symbols
     `this.icons`: SymbolBuffers for icons
     `this.iconCollisionBox`: Debug SymbolBuffers for icon collision boxes
     `this.textCollisionBox`: Debug SymbolBuffers for text collision boxes
   The results are sent to the foreground for rendering

4. performSymbolPlacement(bucket, collisionIndex) is run on the foreground,
   and uses the CollisionIndex along with current camera settings to determine
   which symbols can actually show on the map. Collided symbols are hidden
   using a dynamic "OpacityVertexArray".

## Implements

- [`Bucket`](../interfaces/maplibregl.Bucket.md)
