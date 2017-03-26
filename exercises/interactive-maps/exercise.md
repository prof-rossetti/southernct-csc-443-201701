# Interactive Maps Exercise

Make an interactive map.

## Objectives

  1. Gain exposure to making interactive maps.
  2. Gain exposure to Geographic Information System (GIS) data structures, including Latitude and Longitude.
  3. Practice data-driven document development.
  4. Practice updating page contents without refreshing the page.

## Prerequisites

  + [Changing Datasets](/exercises/data-driven-documents/changing-datasets.md)

## Instructions

Create a new `index.html` page and populate it with the following contents:

```` html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Leaflet Exercise</title>

    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.0.3/dist/leaflet.css" />
    <script src="https://unpkg.com/leaflet@1.0.3/dist/leaflet.js"></script>
  </head>
  <body>
    <h1>Leaflet Exercise</h1>

    <!-- OPTIONALLY PUT A SELECT ELEMENT HERE (FURTHER EXPLORATION ONLY) -->

    <div id="my-map-container" style='width: 400px; height: 300px;'></div>

    <script type="text/javascript">

      //
      // RAW DATASET
      // courtesy of Shoreline East GTFS feed:
      //   +  https://www.cttransit.com/about/developers
      //   +  http://www.shorelineeast.com/google_transit.zip
      //

      var trainStations = [
        {abbrev: "NHV", name: "New Haven Union Station", lat: 41.29771887088102, lon: -72.92673110961914, url: "http://www.shorelineeast.com/service_info/stations/nh_u.php"},
        {abbrev: "ST", name: "New Haven State Street Station", lat: 41.3049849812806, lon: -72.92176365852356, url: "http://www.shorelineeast.com/service_info/stations/nh_s.php"},
        {abbrev: "BRN", name: "Branford", lat: 41.27462757904543, lon: -72.81724601984024, url: "http://www.shorelineeast.com/service_info/stations/branford.php"},
        {abbrev: "GUIL", name: "Guilford", lat: 41.275818924391224, lon: -72.6736432313919, url: "http://www.shorelineeast.com/service_info/stations/guilford.php"},
        {abbrev: "MAD", name: "Madison", lat: 41.28366795570182, lon: -72.59953916072845, url: "http://www.shorelineeast.com/service_info/stations/madison.php"},
        {abbrev: "CLIN", name: "Clinton", lat: 41.279485551365795, lon: -72.52829968929291, url: "http://www.shorelineeast.com/service_info/stations/clinton.php"},
        {abbrev: "WES", name: "Westbrook", lat: 41.28876307212696, lon: -72.44840204715729, url: "http://www.shorelineeast.com/service_info/stations/westbrook.php"},
        {abbrev: "OSB", name: "Old Saybrook", lat: 41.30039086249561, lon: -72.37682461738586, url: "http://www.shorelineeast.com/service_info/stations/old_saybrook.php"},
        {abbrev: "NLC", name: "New London", lat: 41.354158032583534, lon: -72.0930764079094, url: "http://www.shorelineeast.com/service_info/stations/new_london.php"},
        {abbrev: "GCS", name: "Grand Central Station", lat: 40.753165, lon: -73.977379, url: "http://as0.mta.info/mnr/stations/station_detail.cfm"},
        {abbrev: "GW", name: "Greenwich", lat: 41.021705, lon: -73.624597, url: "http://as0.mta.info/mnr/stations/station_detail.cfm"},
        {abbrev: "STM", name: "Stamford", lat: 41.04665375272103, lon: -73.54284524917603, url: "http://as0.mta.info/mnr/stations/station_detail.cfm?key=226"},
        {abbrev: "SN", name: "South Norwalk", lat: 41.095529, lon: -73.421803, url: "http://as0.mta.info/mnr/stations/station_detail.cfm"},
        {abbrev: "BRP", name: "Bridgeport", lat: 41.17870242332479, lon: -73.18707704544067, url: "http://as0.mta.info/mnr/stations/station_detail.cfm?key=246"},
        {abbrev: "STR", name: "Stratford", lat: 41.19428563274378, lon: -73.13156604766846, url: "http://as0.mta.info/mnr/stations/station_detail.cfm?key=248"},
        {abbrev: "MIL", name: "Milford", lat: 41.223229872871606, lon: -73.05766582489014, url: "http://as0.mta.info/mnr/stations/station_detail.cfm?key=250"},
        {abbrev: "WH", name: "West Haven", lat: 41.271408, lon: -72.964722, url: "http://as0.mta.info/mnr/stations/station_detail.cfm?key=251"}
      ]

      //
      // INITIALIZE MAP
      //

      var mapContainerId = 'my-map-container'
      var latLonCoords = [41.29771887088102, -72.92673110961914] // [LAT, LON]
      var zoomLevel = 8

      var map = L.map(mapContainerId)
          .setView(latLonCoords, zoomLevel)

      //
      // ADD MAP TILES
      //

      var tileUrlTemplate = 'http://{s}.tile.osm.org/{z}/{x}/{y}.png' // just use this. don't worry about what it means
      var tileLayerOptions = {attribution: '&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors'} // just keep this

      L.tileLayer(tileUrlTemplate, tileLayerOptions)
          .addTo(map);

      //
      // ADD STATION MARKER(S) TO MAP
      //

      var stationPopup = "<b>New Haven Union Station</b>" + "<br>" + "Some content or context here. Maybe a clickable URL! Go crazy."

      L.marker([41.29771887088102, -72.92673110961914])
          .addTo(map)
          .bindPopup(stationPopup)

      // TODO: Add a marker for each station.

    </script>
  </body>
</html>
````

> NOTE: Do not at any time manually edit the HTML elements on this page (except as instructed in the "Further Exploration" section). Only edit the contents of the `script` at the bottom of the page.

Preview the page in a browser. Ensure you see a map with a marker.

The default marker has been hard-coded to depict the location of New Haven Union Station. Your challenge is to instead dynamically display a marker for each station included in the `trainStations` variable. Display all the markers on the same map. HINT: try using a `forEach()` function!

> ## Further Exploration
>
> Display only a single station on the map. Configure a `select` element to include an option for each station. When a station is selected, trigger a map update to display only a marker for the selected station.
