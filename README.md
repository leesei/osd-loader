# OpenSeadragon Loader

Clone this repo and serve it via HTTP server (e.g. `ecstatic`, `python -m SimpleHTTPServer`).  
Visit the page and use query `source` in URL to specify an arbitrary source to load.
The HTTP server serving the tile source should support CORS.

### Sample commands

These are exposed to `window`:
- viewer
- viewport
- tiledImage
- navigator

You can control OSD with these commands in console (`F12`).

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

See [OSD doc](http://openseadragon.github.io/docs/) for reference.
