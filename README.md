
![Mappls APIs](https://about.mappls.com/images/mappls-b-logo.svg)
# MapmyIndia Interactive Vector Maps JS SDK for Web !

Explore the largest directory of APIs & SDKs for maps, routes and search.

Our APIs, SDKs, and live updating map data available for [238 nations](https://github.com/MapmyIndia/mapmyindia-rest-api/blob/master/docs/countryISO.md) give developers tools to build better mapping, navigation, and search experiences across platforms.

This page will be continually enhanced to offer more insights and reference material on how to best utilize our Vector Maps JS SDK for Web.

You can get your api key to be used in this document here: [https://apis.mappls.com/console/](https://apis.mappls.com/console/)


## Documentation History

| Version | Remarks | Author |
|--|--|--|
| 3.0 | Initial Commit  |Mappls API Team ([MS](https://github.com/mamtasharma117))|

## Introduction
The Interactive Maps JavaScript SDK for Web helps render and display map tiles while customizing the map's look and feel on mobile or web browser. Mappls (MapmyIndia) is India's leading Map provider, and produces various SDKs, including Web SDKs (JavaScript libraries) for mobile-friendly interactive maps which are easy to use & high on performance. 
This SDK is a collection of classes and functions that can be used to implement a host of map features.

**Features:**

-   **Zoom**: Pan-able map of India with 19 zoom levels, 22 being the highest (most detailed) and 4 being the lowest (country level) map display.
-   **Overlays**: The map is the key for any sort of business and understanding this, we at Mappls provide quick default overlays to reduce the boiler plate code for your code base.
    -   **Map Markers (Pushpins)**: Point to any location using default pushpin behaviors and provide it your own style to make it look more tailored for your application. Note: Have a look at the Plug-ins section to find out what makes it cooler.
    -   **Info Windows (Pop-ups)**: On a Map Clicking is a native behavior understanding this, we provide out of the box info windows such that if a pushpin is clicked an info window pops up open and you can show your content related to that location there. You can style it to make it behave as required for your UI to be magnificent.
    -   **Polylines**: Connect any two points or even more with out of the box Mappls polylines dedicated to high customizability and performance to suit your use cases. Note: Have a look at the plug-ins we provide to make your polylines have an edge up and suit your use cases in a more integrated manner.
    -   **Polygons**: Show a region in a spotlight with a polygon and show various localized data based on it.
    -   **Circles:** Circles are way of marking a territory without too much interaction by the user.You can draw a circle around a given location.
-   **Controls**: because we understand the use cases with a map we provide the below out of the box controls that can be turned off or on based on your requirement and because we care, we provide you to override our controls outlook by providing your own styles or CSS so that you can move them or customize them completely. Controls include:
    -   **Zoom Bar**: (appears by default at the centre on the right side). Helps to provide zoom in and zoom out functionality to the map by default.
    -   **Map Layer Control**: Allows to change the map view from basic to hybrid and regional. Also allows to show traffic layer on map.
  -   **Fullscreen Control**: Allows to view a full screen map.
  -   **Current Location Control**: Scopes the Map to the viewer’s current location.**  
	
        Note:**  The location settings must be turned on and must allow the site to fetch the location for this control to work.

**Please Note**: Mappls(MapmyIndia) may extend and enhance functionality for its interactive map API in future, which will be clearly documented in this section, and which will be available through the Mappls.Map class and Mappls.* set of classes generally.

## Getting Started

Now that you’re all caught up with the features let’s get down right to them and look at how can you integrate our Interactive Map to your Website from scratch.


### Initializing The Map

[Live Demo](https://www.mapmyindia.com/api/advanced-maps/WebSDK-LiveDemo/mapInitialization) 

The easiest way to start loading maps in a web page is with a “Hello World” sample code, you can download or view a working “Hello World” sample from the links for adding your first marker below.

#### Adding the Map Script to your web page

Follow the below steps to integrate MapmyIndia interactive Maps into your existing code base or even a File -> New Project.
- Declare application as HTML5:
Define `<!DOCTYPE html>` on top of your HTML.
- Integrate Interactive maps from Mappls into your browser application by simply including Mappls's interactive map API in your script source in the head section.

```html
    <script src="https://apis.mappls.com/advancedmaps/api/<key or token>/map_sdk?v=3.0&layer=vector"></script>
```

   **Important**: 

   - *bearer token* in place of `<key>`
   - *layer*: Vector/raster default vector

- Define a style in the head section to load in your CSS.
   
```html
    <style> html, body, #map1 {margin: 0;padding: 0;width: 100%;height: 100%;} </style>
```

- Define a div object in the body tag of the HTML where you want the Mappls Map to show up.

```html
    <div id="map"></div>;
```

- Initialize a Mappls Map by simply calling new Mappls.Map() in the JavaScript and passing it at the minimum, the div object in which you want the map populated. (All other parameters are optional.)

```js
    map = new Mappls.Map('map', {center:{lat:28.612964,lng:77.229463} });
```	

- **Hello World** 

```html    
  <html>
      <head>
      <title>Hello, World</title>
      <meta name="viewport" content="initial-scale=1.0">
      <meta charset="utf-8">
      <style>
          html,
          body,
          #map {
              margin: 0;
              padding: 0;
              width: 100%;
              height: 100vh;
              }
      </style>
      <script src="https://apis.mappls.com/advancedmaps/api/<key>/map_sdk?layer=vector&v=3.0&callback=loadMap" defer async></script>
      </head>
      <body>
          <div id="map"></div>
          <script>
              var map;
              function loadMap()
              { 
                  map = new Mappls.Map('map', {center: [28.544,77.5454]});
              } 
          </script>
      </body>
  </html>   
```
	
## Map Quick Reference:

   - Map Methods & Events
        - [Map Properties](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/mapProperties.md)
        - [Map Methods](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/mapMethods.md)
        - [Map Events](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/mapEvents.md) 

### Markers


Markers are effortless way of pointing to a location, so getting right to it, you can go ahead and add markers that we provide out of the box but just in case you want to add your own, we’ve got that covered for you as well. There are 3 main categories of markers that you can add namely,  
-  **Stock Markers**: The one you get out of the box using our Interactive Vector Maps SDK and you can select from a lot of choices.  
-  **Custom Marker**: Just in case you want to provide your own markers, we’ve handled that for you as well.  
-  **HTML Marker**: In case you don’t want to add in an image you can use HTML to create a marker and then plot it on the map as well.

For more details, please read article in [Markers](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/markers.md)

Now, that you have a basic understanding of Markers, Functions and Events let’s talk about Info Windows or Pop-Ups.

### Adding Your First Marker

[LIVE DEMO](https://www.mapmyindia.com/api/advanced-maps/WebSDK-LiveDemo/single-marker)

The easiest way to start loading maps with simple markers in a web page is with a “Hello World” sample code, you can download or view a working “Hello World” sample from the links above. 
  
In the sample, we have a case of a map scenario where objective is plotting a pushpin that says hello world on click. 

#### Method to add marker on map

**`new Mappls.Marker`**

##### Code to add marker on Map

```js
var marker = new Mappls.Marker({
    map: map,
    position: {"lat": 28.519467,"lng":77.223150}
	});
```

## Example

```html    
<html>
    <head>
    <title>First Marker</title>
    <meta name="viewport" content="initial-scale=1.0">
    <meta charset="utf-8">
    <style>
        html,
        body,
        #map {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100vh;
            }
    </style>
    <script src="https://apis.mappls.com/advancedmaps/api/<key or token>/map_sdk?layer=vector&v=3.0&callback=loadMap" defer async></script>
    </head>
    <body>
        <div id="map"></div>
        <script>
            var map;
            function loadMap()
            { 
                map = new Mappls.Map('map', {center: [28.544,77.5454]});
                map.addListener('load', function () {
                    var marker= new Mappls.Marker({
                    map: map,
                    position: {"lat": 28.544,"lng":77.5454}
                    });
                }); 
            }
            </script>
        </body>
    </html>
```

### Knowing Properties And Methods

You can interact with properties of the Map we provide to suite your use case and add additional customizability to your Map layer using the features it has to offer. These functions are a quick go to in case of an event. 

For details, please read article in [Marker Methods](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/markerMethods.md)

## Marker Quick Reference:

   - [**Marker Properties**](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/markerProperties.md)
   - [**Marker Methods**](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/markerMethods.md)
   - [**Marker Events**](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/markerEvents.md)

- [**Multiple Marker with cluster**](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/markers.md#Multiple-Marker-With-cluster)

- [**GeoJSON Bulk Marker**](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/markers.md#geojson-bulk-markers)

```js
    var geoData={
                "type": "FeatureCollection",
                "features": [{
                "type": "Feature",
                "properties": {"htmlPopup":"noida"},
                "geometry": {"type": "Point",
                "coordinates": [28.544,77.5454]}
                },{
                "type": "Feature",
                "properties": {"htmlPopup":"faridabad"},
                "geometry": {"type": "Point",
                "coordinates": [28.27189158,77.2158203125]}
                },{
                "type": "Feature",
                "properties": {"htmlPopup":"delhi"},
                "geometry": {"type": "Point",
                "coordinates": [28.549511,77.2678250]}
                }]
            };
    var marker=Mappls.Marker({map:map,position:geoData,icon_url:'https://apis.mappls.com/map_v3/1.png',clusters:true,fitbounds:true,fitboundOptions:{padding: 120,duration:1000},popupOptions:{offset: {'bottom': [0, -20]}}});
```


### Info Windows

[LIVE DEMO](https://www.mapmyindia.com/api/advanced-maps/WebSDK-LiveDemo/infowindow) 

Info Windows are a convenient way of showing data about a marker or in simple words: what that marker stands for. The Native behaviour of a user to know about any marker is to try and click on it to know what it’s all about and showing an info window would be the way to go about it:

**Please Note**: MapmyIndia interactive map SDK supports a default info window that you can leverage but we want you to have an option to customize your info window to fit in with your UI and you can do so in the CSS.

For a quick sample or a demo you can follow up with the links on top. 

You can declare an info window in your CSS and write up a quick function to generate data in that info window and on marker click event simple open that info window.

For details , please read article in [Info Windows](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/infoWindows.md)

## Example

```html    
    <html>
        <head>
        <title>Infowindow</title>
        <meta name="viewport" content="initial-scale=1.0">
        <meta charset="utf-8">
        <style>
            html,
            body,
            #map {
                margin: 0;
                padding: 0;
                width: 100%;
                height: 100vh;
                }
        </style>
        <script src="https://apis.mappls.com/advancedmaps/api/<key or token>/map_sdk?layer=vector&v=3.0&callback=loadMap" defer async></script>
        </head>
        <body>
            <div id="map"></div>
            <script>
                var map;
                function loadMap()
                { 
                    map = new Mappls.Map('map', {center: [28.544,77.5454]});
                    map.addListener('load', function () {
                        var window=new Mappls.InfoWindow({map:map,content:"MyMapContent",position:{lat: 28.529467 ,lng: 77.223150}});
                    }); 
                }
            </script>
        </body>
    </html>
```

## Info Window Quick Reference

- [**InfoWindow Properties**](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/infoWindows.md#InfoWindow-Properties)

- [**Remove InfoWindow**](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/infoWindows.md#Remove-InfoWindow)


### Polylines

[LIVE DEMO](https://www.mapmyindia.com/api/advanced-maps/WebSDK-LiveDemo/polyline) 

Polylines are a way of showing movement or transit on a map. We at Mappls understand the ways you can leverage the features offered by a map and one among them is a Polyline.

Polylines are continuous lines consisting of one or more line segments (preferably a geopath). To add a polyline, initialize map as shown in the previous sections and then create a data set. What is a data set? The Data set is the collection of points (latitude and longitude) over which you want the polyline to be drawn.

For details , please read article in [Polylines](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/polylines.md)

### Polyline Quick Reference

- [**Polyline Properties**](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/polyline.md#Polyline-Properties)

## Example:

 ```html    
	<html>
    <head>
    <title>Polyline</title>
    <meta name="viewport" content="initial-scale=1.0">
    <meta charset="utf-8">
    <style>
        html,
        body,
        #map {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100vh;
            }
    </style>
    <script src="https://apis.mappls.com/advancedmaps/api/<key or token>/map_sdk?layer=vector&v=3.0&callback=loadMap" defer async></script>
    </head>
    <body>
        <div id="map"></div>
        <script>
            var map;
            function loadMap()
            { 
                map = new Mappls.Map('map', {center: [28.544,77.5454]});
                map.addListener('load', function () {
                    
                    var pts=[{lat:28.55108, lng:77.26913},{lat:28.55106,lng: 77.26906},{lat:28.55105,lng: 77.26897},{lat:28.55101,lng:77.26872},{lat:28.55099, lng:77.26849},{lat:28.55097, lng:77.26831},{lat:28.55093, lng:77.26794},{lat:28.55089, lng:77.2676},{lat:28.55123, lng:77.26756},{lat:28.55145, lng:77.26758},{lat:28.55168, lng:77.26758},{lat:28.55175, lng:77.26759},{lat:28.55177, lng:77.26755},{lat:28.55179, lng:77.26753}];
                    var polyline = new Mappls.Polyline({
                        map:map,
                        paths: pts,
                        strokeColor: '#333',
                        strokeOpacity: 1.0,
                        strokeWeight: 5,
                        fitbounds:true
			        });
                }); 
            }
        </script>
    </body>
</html>
```

- [**Draw Editable Polyline**](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/polyline.md#Editable-Polyline)

*Drag polyline from anywhere & get callback polyline data. By default the value is false.*

```js
    editable: true 
```

- [**Draw Gradient In Polyline**](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/polyline.md#Gradient-Polyline)

- [**Draw Animated Polyline**](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/polyline.md#Animated-Polyline)

*Polyline draw point by point with speed*

```js
    animate: {path:true/false,speed:5}
```

- [**Animated Marker Along With Polyline**](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/polyline.md#Animated-Marker-Along-With-Polyline)

```js
    animate: { 
        speed:5 
        icon_width: 35 / “35”,
        icon_height: 15 / “15”,,
        icon_url: (icon_url),
        repeat: true/false,
    },
```

- [**Multi Colored Polyline**](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/polyline.md#Multi-Colored-Polyline)

- [**Polyline Marker Animation Methods**](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/polyline.md#polyline-marker-animation-methods)

- [**Polyline Events**](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/polyline.md#polyline-events)

**Remove Polyline**
```js
    Mappls.remove({map: map, layer: polyline);
```


In real case scenarios, you’ll need to get the data set on the fly or from a service and then you can leverage the events and functions we’ve learnt about how to plot the polyline. You also might need to beautify your polyline or add transitions for your UI to look marvelous. 

The polyline is just the beginning, but sometimes you’ll need to mark a territory to properly showcase your information. In such cases a polyline might not be the perfect fit but Polygons and Circles may be the apt choice.

### Polygons

Polygons are a way of showing a territory. In cases where you want to showcase data over an area, polygons are your best pick. You can use them to show Geozones as well.

It’s very like generating a polyline, the basic steps remain the same, create a Data set, generate a polygon and add it to the map.

For details , please read article in [Polygon](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/polygon.md)


**Simple Polygon**

[LIVE DEMO](https://www.mapmyindia.com/api/advanced-maps/WebSDK-LiveDemo/polygon) 

## Example

```html    
    <html>
        <head>
        <title>Polygon</title>
        <meta name="viewport" content="initial-scale=1.0">
        <meta charset="utf-8">
        <style>
            html,
            body,
            #map {
                margin: 0;
                padding: 0;
                width: 100%;
                height: 100vh;
                }
        </style>
        <script src="https://apis.mappls.com/advancedmaps/api/<key or token>/map_sdk?layer=vector&v=3.0&callback=loadMap" defer async></script>
        </head>
        <body>
            <div id="map"></div>
            <script>
                var map;
                function loadMap()
                { 
                    map = new Mappls.Map('map', {center: [28.544,77.5454]});
                    map.addListener('load', function () {
                        var pts=[{lat: 28.774, lng: 80.190},{lat: 28.466, lng: 76.118},{lat: 27.321, lng: 77.757},{lat: 27.771, lng: 80.757}];
                        new Mappls.Polygon({map:map,paths: pts,fillColor:"blue"});
                    }); 
                }
            </script>
        </body>
    </html>
```

- [**Polygon Properties**](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/polygon.md#polygon-properties)

- [**Polygon Events**](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/polygon.md#polygon-events)

### Draw Polyline/Polygons 

This method can draw polyline or polygon directly from map with click event with callback methods.

Double Click to finish draw event.

```js
//Polyline

    var polylineoptions={strokeColor: "blue",strokeOpacity:1.0,strokeWeight: 9,lineGap:0,popupHtml:'Route 1',popupOptions:{offset: {'bottom': [0, -20]}}} 

    Mappls.draw({map:map,type:'polyline',callback:draw_callback,options:polylineoptions});

//Polygon
var polygonoptions={fillColor:'#333'}
Mappls.draw({map:map,type:'polygon',callback:draw_callback,options:polygonoptions});

function draw_callback(data)
{
 console.log(data);
}
```

*Now that we’ve covered polygons let’s have a look at **Circles** which provide another way of showcasing territory.*

### Circles

Circles are way of marking a territory without too much interaction by the user. A circle only has two important values:

-   The Centre point of the circle (in this case it’ll be a latitude with a longitude).
-   The Radius of the circle.

With the two values, you can easily define a quick area of interest on a map.

For details , please read article in [Circle](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/circle.md)

```js
    Mappls.Circle()
```

[LIVE DEMO](https://www.mapmyindia.com/api/advanced-maps/WebSDK-LiveDemo/circle) 

## Example

```html    
	<html>
    <head>
    <title>Circle</title>
    <meta name="viewport" content="initial-scale=1.0">
    <meta charset="utf-8">
    <style>
        html,
        body,
        #map {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100vh;
            }
    </style>
    <script src="https://apis.mappls.com/advancedmaps/api/<key or token>/map_sdk?layer=vector&v=3.0&callback=loadMap" defer async></script>
    </head>
    <body>
        <div id="map"></div>
        <script>
            var map;
            function loadMap()
            { 
                map = new Mappls.Map('map', {center: [28.544,77.5454]});
                map.addListener('load', function () {
                    var mappls_circle = new Mappls.Circle({
                    map: map,
                    center: {"lat": 28.544 ,"lng": 77.5454},
                    radius: 1000});
                }); 
            }
        </script>
    </body>
</html>
```
- [**Circle Properties**](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/circle.md#circle-properties)

- [**Circle Events**](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/circle.md#circle-events)



## Heatmap Overlays

For details , please read article in [Heatmap Overlays](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/heatMap.md)

```js
    var pts=[ {lat: 28.774, lng: 80.190}, {lat: 28.466, lng: 76.118}, {lat: 27.321, lng: 77.757}, {lat: 27.774, lng: 80.190} ];

    var heat_map=new Mappls.HeatmapLayer({map:map,data:pts,fitbounds:true});
```

- [**Heatmap Properties**](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/heatMap.md#heatmap-properties)

[LIVE DEMO](https://www.mapmyindia.com/api/advanced-maps/WebSDK-LiveDemo/heatmaplayer) 

## Example

```html    
    <html>
        <head>
        <title>Heatmap</title>
        <meta name="viewport" content="initial-scale=1.0">
        <meta charset="utf-8">
        <style>
            html,
            body,
            #map {
                margin: 0;
                padding: 0;
                width: 100%;
                height: 100vh;
                }
        </style>
        <script src="https://apis.mappls.com/advancedmaps/api/<key or token>/map_sdk?layer=vector&v=3.0&callback=loadMap" defer async></script>
        </head>
        <body>
            <div id="map"></div>
            <script>
                var map;
                function loadMap()
                { 
                    map = new Mappls.Map('map', {center: [28.544,77.5454]});
                    map.addListener('load', function () {
                        var pts=[{lat:28.55108, lng:77.26913},{lat:28.55106,lng: 77.26906},{lat:28.55105,lng: 77.26897},{lat:28.55101,lng:77.26872},{lat:28.55099, lng:77.26849},{lat:28.55097, lng:77.26831},{lat:28.55093, lng:77.26794},{lat:28.55089, lng:77.2676},{lat:28.55123, lng:77.26756},{lat:28.55145, lng:77.26758},{lat:28.55168, lng:77.26758},{lat:28.55175, lng:77.26759},{lat:28.55177, lng:77.26755},{lat:28.55179, lng:77.26753}];

                        var gradient = [ 'rgba(0, 255, 255, 0)', 'rgba(0, 255, 255, 1)', 'rgba(0, 191, 255, 1)', 'rgba(0, 127, 255, 1)', 'rgba(0, 63, 255, 1)', 'rgba(0, 0, 255, 1)', 'rgba(0, 0, 223, 1)', 'rgba(0, 0, 191, 1)', 'rgba(0, 0, 159, 1)', 'rgba(0, 0, 127, 1)', 'rgba(63, 0, 91, 1)', 'rgba(127, 0, 63, 1)', 'rgba(191, 0, 31, 1)', 'brown' ]; 

                        var heat_map=new Mappls.HeatmapLayer({map:map,data:pts,gradient:gradient,fitbounds:true});
                    }); 
                }
            </script>
        </body>
    </html>
```


### Add geojson layer

For details, please read article in [GeoJSON ](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/geoJson.md)

[Live Demo](https://www.mapmyindia.com/api/advanced-maps/WebSDK-LiveDemo/addgeojson) 

*GeoJSON Supports marker, polyline and polygon*

***Marker Property support in geojson***

1. description
2. icon 
3. icon-size 
4. icon-offset
5. text 
6. text-size
7. text-offset

***polyline Property support in geojson:***

1. stroke
2. stroke-opacity
3. stroke-width

***polygon Property support in geojson:***

1. stroke
2. fill color
3. fill opacity

```js
    new Mappls.addGeoJson({map:map,data:geoData,fitbounds:true,cType:0});
```

- [**Add GeoJSON Properties**](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/geoJson.md#Add-GeoJSON-Properties)

## Example

```html    
    <html>
        <head>
        <title>Geojson Layer</title>
        <meta name="viewport" content="initial-scale=1.0">
        <meta charset="utf-8">
        <style>
            html,
            body,
            #map {
                margin: 0;
                padding: 0;
                width: 100%;
                height: 100vh;
                }
        </style>
        <script src="https://apis.mappls.com/advancedmaps/api/<key or token>/map_sdk?layer=vector&v=3.0&callback=loadMap" defer async></script>
        </head>
        <body>
            <div id="map"></div>
            <script>
                var map;
                function loadMap()
                { 
                    map = new Mappls.Map('map', {center: [28.544,77.5454]});
                    map.addListener('load', function () {
                        var mixjson={
                            "type": "FeatureCollection",
                            "features": [
                                {
                                    "type": "Feature",
                                    "geometry": {"type": "Point","coordinates": [28.54950,77.2678540]
                                    },
                                    "properties": {
                                        "name": "MapmyIndia old Office",
                                        "description": "Okhla delhi",
                                        "icon": "https://apis.mappls.com/map_v3/1.png",
                                        "icon-size":1,
                                        "text":"",
                                        "text-size":20,
                                        "text-offset":[0,0],
                                        "text-color":"red",
                                    }
                                },
                                {
                                    "type": "Feature",
                                    "geometry": {
                                        "type": "Point",
                                        "coordinates": [28.5510446,77.268952]
                                    },
                                    "properties": {
                                        "name": "<div onclick=\"function1()\">MapmyIndia New Office</div>",
                                        "description": "68,Okhla delhi",
                                        "icon": "https://apis.mappls.com/map_v3/1.png",
                                        "icon-size":0.55,
                                        "text":"1",
                                        "icon-offset":[0,-20],
                                    }
                                },
                                {
                                    "type": "Feature",
                                    "geometry": {
                                        "type": "LineString",
                                        "coordinates": [
                                            [28.551042,77.268953],
                                            [28.551005,77.268649],
                                            [28.550986,77.268392],
                                            [28.550967,77.268231],
                                            [28.550967,77.268177],
                                            [28.550958,77.268016],
                                            [28.55092,77.267587],
                                            [28.550722,77.267651],
                                            [28.55042,77.267823],
                                            [28.550128,77.267802],
                                            [28.549751,77.267995],
                                            [28.549652,77.268039]
                                        ]
                                    },
                                    "properties": {
                                        "name": "Direction1",
                                        "description": "Direction2",
                                        "stroke": "#33CC00",
                                        "stroke-opacity": 0.6509803921568628,
                                        "stroke-width": 10,
                                    }
                                },
                                {
                                    "type": "Feature",
                                    "geometry": {
                                        "type": "Polygon",
                                        "coordinates": [[
                                                [28.550868798522835,77.26878225803375],
                                                [28.550868798522835,77.26899683475493],
                                                [28.550383454405356,77.26903975009918],
                                                [28.550388166494926,77.26883590221404]
                                        ]]
                                    
                                    },
                                    "properties": {
                                        "name": "MapmyIndia Head Office",
                                        "stroke": "#33CC00",
                                        "stroke-opacity": 0.6509803921568628,
                                        "stroke-width": 3,
                                        "fill": "#33CC00",
                                        "fill-opacity": 0.6509803921568628
                                    }
                                }
                            ]
                        };
                    var jsonData=Mappls.addGeoJson({map:map,data:mixjson,fitbounds:true});
                    }); 
                }
            </script>
        </body>
    </html>
```

**Remove Layer**
```js
    new Mappls.remove({map:map,layer:jsonData});
```


### KML Overlay

**KML**: [Keyhole Markup Language](https://www.opengeospatial.org/standards/kml) is a file format used to display geographic data on maps.
Using this plugin, you can overlay KML data over Mappls Maps for web.

[LIVE DEMO](https://www.mapmyindia.com/api/advanced-maps/WebSDK-LiveDemo/kml) 

#### Important Notes to remember
1. Only KML data supported.
2. KML file **must** have absolute path or raw KML string 
(in variable or in textbox)
3. All internal URL's path **must** be absolute. 
(for icon path etc)
4. File must not be password protected.
5. File must be CORS enabled from the server where they are hosted.
6. File must follow KML standard strictly.

**How to allow**
add libraries=kml in initial load
ie.

```js
    <script src="https://apis.mappls.com/advancedmaps/api/<key or token>/map_sdk?v=3.0&layer=vector&libraries=kml"></script>
```

- **KML Method**

```js
    var url="https://www.mappls.com/api/advanced-maps/doc/sample/mmi.kml";
    Mappls.KmlLayer({map:map,url:url,cType:1,fitbounds:true,fitboundOptions:{padding:200}});
```

- [**KML Properties**:](https://github.com/mappls-api/mapmyindia-vector-maps-js-web-SDK/blob/master/docs/V3.0/kml.md#KML-Properties)


```html    
    <html>
        <head>
        <title>Geojson Layer</title>
        <meta name="viewport" content="initial-scale=1.0">
        <meta charset="utf-8">
        <style>
            html,
            body,
            #map {
                margin: 0;
                padding: 0;
                width: 100%;
                height: 100vh;
                }
        </style>
        <script src="https://apis.mappls.com/advancedmaps/api/<key or token>/map_sdk?layer=vector&v=3.0&libraries=kml&callback=loadMap" defer async></script>
        </head>
        <body>
            <div id="map"></div>
            <script>
                var map;
                function loadMap()
                { 
                    map = new Mappls.Map('map', {center: [28.544,77.5454]});
                    map.addListener('load', function () {
                        var url="https://www.mappls.com/api/advanced-maps/doc/sample/mmi.kml";
                        Mappls.KmlLayer({map:map,url:url,fitbounds:true,fitboundOptions:{padding:200}});
                    }); 
                }
            </script>
        </body>
    </html>
```


**Please Note**: For a more detailed code snippet follow the links provided above to see the sample code or see a live demo.

For any queries and support, please contact:

  

![](https://cdn.mapmyindia.com/mappls_web/maps_widget_v2/images/mappls.svg?service=google_gsuite)

Email us at [apisupport@mapmyindia.com](mailto:apisupport@mapmyindia.com)

  
  

![](https://www.mapmyindia.com/api/img/icons/stack-overflow.png)

[Stack Overflow](https://stackoverflow.com/questions/tagged/mapmyindia-api)

Ask a question under the mapmyindia-api

  

![](https://www.mapmyindia.com/api/img/icons/support.png)

[Support](https://www.mapmyindia.com/api/index.php#f_cont)

Need support? contact us!

  

![](https://www.mapmyindia.com/api/img/icons/blog.png)

[Blog](http://www.mapmyindia.com/blog/)

Read about the latest updates & customer stories

  
  

© Copyright 2022 CE Info Systems Ltd. All Rights Reserved.
