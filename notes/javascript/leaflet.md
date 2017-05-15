## Open-source JavaScript Libraries

### Leaflet Overview

>  Leaflet is the leading open-source JavaScript library for mobile-friendly interactive maps... Leaflet is designed with simplicity, performance and usability in mind. It works efficiently across all major desktop and mobile platforms, can be extended with lots of plugins, has a beautiful, easy to use and well-documented API and a simple, readable source code that is a joy to contribute to. - [Leaflet website](http://leafletjs.com/)

Leaflet allows you to make interactive maps.

#### Documentation and Reference

Source Code: https://github.com/Leaflet/Leaflet.

API Documentation: https://www.mapbox.com/mapbox-gl-js/api/.

  + `Map`: http://leafletjs.com/reference-1.0.3.html#map.
  + `TileLayer`: http://leafletjs.com/reference-1.0.3.html#tilelayer.
  + `Marker`: http://leafletjs.com/reference-1.0.3.html#marker.

Examples: http://leafletjs.com/examples.html.

#### Usage

```` js
//
// CREATE A MAP
//

var mapContainerId = 'my-map-container'
var latLonCoords = [41.29771887088102, -72.92673110961914]
var zoomLevel = 8

var map = L.map(mapContainerId)
    .setView(latLonCoords, zoomLevel)

//
// ADD MAP TILES
//

var tileUrlTemplate = 'http://{s}.tile.osm.org/{z}/{x}/{y}.png' // just use this. don't worry about what it means
var tileLayerOptions = {
  attribution: '&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors'
}

L.tileLayer(tileUrlTemplate, tileLayerOptions)
    .addTo(map)
````
