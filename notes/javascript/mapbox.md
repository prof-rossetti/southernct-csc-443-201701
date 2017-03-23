## Open-source JavaScript Libraries

### Mapbox Overview

> Mapbox is built on vector maps, an advanced approach to mapping where data is delivered to the device and precisely rendered in real-time. The result is smooth, fast maps.
>
> The data for every feature you see in a vector map resides on the client, not the server. That means data can be instantly queried, allowing for flexible map changes and user interfaces that adapt to the map automatically.
>
> You can customize every aspect of your map, from tweaking the colors, to hiding or showing specific layers, to choosing which information to present on your map, all while your users are interacting with the map. - [Mapbox website](https://www.mapbox.com/maps/)

Mapbox allows you to make interactive maps.

Mapbox provides a variety of products and services, but we will be focusing on using its JavaScript API to make basic maps.

#### Prerequisites

First [register](https://www.mapbox.com/developers/) for a Mapbox account. Then sign in and visit your account homepage to find an access token on the right side of the page. Note the value of your access token for later use.

#### Documentation and Reference

API Documentation: https://www.mapbox.com/mapbox-gl-js/api/.

Examples: https://www.mapbox.com/mapbox-gl-js/examples/.

#### Usage

```` js
mapboxgl.accessToken = 'your.access.token' // where 'your.access.token' corresponds to your own access token (see instructions above)

var configurationOptions = {
  container: 'my-map-container', // where `my-map-container` corresponds to the `id` attribute of some empty `div` element
  style: 'mapbox://styles/mapbox/streets-v9',
  center: [-74.50, 40], // optional
  zoom: 9 // optional
}
var map = new mapboxgl.Map(configurationOptions)
````
