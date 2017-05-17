# OpenSeadragon Loader

Clone this repo and serve it via HTTP server (e.g. `ecstatic`, `python2 -m SimpleHTTPServer`, `python3 -m http.server`).  
Visit the page and use query param `source` to specify an arbitrary source *URL* to load (only URL is supported).  
e.g.: [http://localhost/osd-loader/?source=http://image.server/path-to-tile](http://localhost/osd-loader/?source=http://image.server/path-to-tile)  
The source URL will be passed to `tileSource` of OpenSeadragon, see [supported sources](http://openseadragon.github.io/#examples-and-features).  
The HTTP server serving the tile source should support [CORS](http://enable-cors.org/).

### Sample commands

These are exposed to `window`:
- `viewer`
- `viewport`
- `tiledImage`
- `navigator`

You can control the viewer with these commands in console (`F12`).

```js
// 70% of image width, 70% of image height 
viewport.panTo(new OpenSeadragon.Point(0.7, 0.7));
// pixel coordinate (5000,5000) (wrt to the original WSI)
viewport.panTo(viewport.imageToViewportCoordinates(new OpenSeadragon.Point(5000, 5000)));

// 1.0 = original WSI size
viewport.zoomTo(tiledImage.imageToViewportZoom(1.0))
viewport.zoomTo(tiledImage.imageToViewportZoom(2.0))

viewport.setRotation(0)
viewport.setRotation(45)
```

See [OpenSeadragon doc](http://openseadragon.github.io/docs/) for API reference.
