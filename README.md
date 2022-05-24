[<img src="https://about.mappls.com/images/mappls-b-logo.svg" height="60"/> </p>](https://www.mapmyindia.com/api)

# Mappls Web Maps JS

Explore the largest directory of APIs & SDKs for maps, routes and search.

Our APIs, SDKs, and live updating map data available for [200+ countries & territories](https://github.com/MapmyIndia/mapmyindia-rest-api/blob/master/docs/countryISO.md)<sup>2</sup> give developers tools to build better mapping, navigation, and search experiences across platforms.

This page will be continually enhanced to offer more insights and reference material on how to best utilize our Vector Maps JS SDK for Web.

You can get your api key to be used in this document here: [https://apis.mappls.com/console/](https://apis.mappls.com/console/)


## Documentation History

| Version | Remarks | Author |
|--|--|--|
| 3.0 | Initial Commit  |Mappls API Team ([MS](https://github.com/mamtasharma117))|

## Introduction
The Mappls Web Maps JS SDK helps render and display map for India & the world<sup>2</sup> while customizing the map's look and feel on mobile or web browser. Mappls (MapmyIndia) is India's leading Map provider, and produces various JS for mobile-friendly interactive maps which are easy to use & high on performance. 
This JS is a collection of classes and functions that can be used to implement a host of map features.

**Features:**

-   **`Zoom`**: Pan-able map of India 22 zoom level being the highest (most detailed) and 1 being the lowest (world level) map display.
-   **`Overlays`**: The map is the key for any sort of business and understanding this, we at Mappls provide quick default overlays to reduce the boiler plate code for your code base.
    -   **`Map Markers (Pushpins)`**: Point to any location using default pushpin behaviors and provide it your own style to make it look more tailored for your application. Note: Have a look at the Plug-ins section to find out what makes it cooler.
    -   **`Info Windows (Pop-ups)`**: On a Map Clicking is a native behavior understanding this, we provide out of the box info windows such that if a pushpin is clicked an info window pops up open and you can show your content related to that location there. You can style it to make it behave as required for your UI to be magnificent.
    -   **`Polylines`**: Connect any two points or even more with out of the box Mappls polylines dedicated to high customizability and performance to suit your use cases. Note: Have a look at the plug-ins we provide to make your polylines have an edge up and suit your use cases in a more integrated manner.
    -   **`Polygons`**: Show a region in a spotlight with a polygon and show various localized data based on it.
    -   **`Circles`:** Circles are way of marking a territory without too much interaction by the user.You can draw a circle around a given location.
-   **`Controls`**: because we understand the use cases with a map we provide the below out of the box controls that can be turned off or on based on your requirement and because we care, we provide you to override our controls outlook by providing your own styles or CSS so that you can move them or customize them completely. Controls include:
    -   **`Zoom Bar`**: (appears by default at the centre on the right side). Helps to provide zoom in and zoom out functionality to the map by default.
    -   **`Map Layer Control`**: Allows to change the map view from basic to hybrid and regional. Also allows to show traffic layer on map.
  -   **`Fullscreen Control`**: Allows to view a full screen map.
  -   **`Current Location Control`**: Scopes the Map to the viewer’s current location.**  
	
        Note:**  The location settings must be turned on and must allow the site to fetch the location for this control to work.

**Please Note**: Mappls(MapmyIndia) may extend and enhance functionality for its interactive map API in future, which will be clearly documented in this section, and which will be available through the Mappls.Map class and Mappls.* set of classes generally.

## Getting Started

Now that you’re all caught up with the features let’s get down right to them and look at how can you integrate our Interactive Map to your Website from scratch.

## Add Map

[Live Demo](https://about.mappls.com/api/web-sdk/vector-map-example/Maps/mappls-default-map) 

The easiest way to start loading maps in a web page is with a “Hello World” sample code, you can download or view a working “Hello World” sample from the links for adding your first marker below.

#### Adding the Map Script to your web page

Follow the below steps to integrate Mappls interactive Maps into your existing code base or even a File -> New Project.
- Declare application as HTML5:
Define `<!DOCTYPE html>` on top of your HTML.
- Integrate Interactive maps from Mappls into your browser application by simply including Mappls's interactive map API in your script source in the head section.

    ```html
        <script src="https://apis.mappls.com/advancedmaps/api/<token>/map_sdk?v=3.0&layer=vector"></script>
    ```    
    **Important:**
    - Please ensure that you insert your *bearer token* in place of `<token>`
    - *`v`*: This is the version. Please keep as the latest version: `3.0`.
    - *`layer`*: The type of map applicable for the project. The default is `vector`. Alternate value is `raster`. 
    
    Please discuss with [apisupport@mappls.com](mailto:apisupport@mappls.com) before changing values for either variables.

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
        map = new mappls.Map('map', {center:{lat:28.612964,lng:77.229463} });
    ```	

### Learn about Map Methods & Events


- [Map Properties](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/mapProperties.md)
- [Map Methods](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/mapMethods.md)
- [Map Events](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/mapEvents.md) 


## Markers

Markers are effortless way of pointing to a location, so getting right to it, you can go ahead and add markers that we provide out of the box but just in case you want to add your own, we’ve got that covered for you as well. There are 3 main categories of markers that you can add namely,  
-  **`Stock Markers`**: The one you get out of the box using our Interactive Vector Maps SDK and you can select from a lot of choices.  
-  **`Custom Marker`**: Just in case you want to provide your own markers, we’ve handled that for you as well.  
-  **`HTML Marker`**: In case you don’t want to add in an image you can use HTML to create a marker and then plot it on the map as well.

For more details, please read article in [Markers](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/markers.md)

Now, that you have a basic understanding of Markers, Functions and Events let’s talk about Info Windows or Pop-Ups.

## Add Markers

[LIVE DEMO](https://about.mappls.com/api/web-sdk/vector-map-example/Markers/mappls-singlemarker)

The easiest way to start loading maps with simple markers in a web page is with sample code given on the link above, you can download or view a working sample with your keys. 



### Method to add marker on map

**`mappls.Marker`**

```js
var marker = new mappls.Marker({
    map: map,
    position: {"lat": 28.519467,"lng":77.223150}
	});
```

### **Knowing Marker Properties And Methods**

You can interact with properties of the Map we provide to suite your use case and add additional customizability to your Map layer using the features it has to offer. These functions are a quick go to in case of an event. 

### Markers Quick Reference:

- [Marker Properties](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/markerProperties.md)
- [Marker Methods](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/markerMethods.md)
- [Marker Events](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/markerEvents.md)

- [Multiple Marker with cluster](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/markers.md#Multiple-Marker-With-cluster)

- [GeoJSON Bulk Marker](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/markers.md#geojson-bulk-markers)

### View Sample Codes for Quick Reference

- [Single Marker](https://about.mappls.com/api/web-sdk/vector-map-example/Markers/mappls-singlemarker)
- [Multiple Marker](https://about.mappls.com/api/web-sdk/vector-map-example/Markers/mappls-multiplemarker)
- [Advance Cluster Marker](https://about.mappls.com/api/web-sdk/vector-map-example/Markers/mappls-advancecluster)
- [Bouncing Marker](https://about.mappls.com/api/web-sdk/vector-map-example/Markers/mappls-bouncing-marker)
- [Cluster Marker](https://about.mappls.com/api/web-sdk/vector-map-example/Markers/mappls-cluster)
- [Dragable Marker](https://about.mappls.com/api/web-sdk/vector-map-example/Markers/mappls-draggablemarker)
- [Marker Dropdown](https://about.mappls.com/api/web-sdk/vector-map-example/Markers/mappls-dropdown-marker)
- [Marker Dropup](https://about.mappls.com/api/web-sdk/vector-map-example/Markers/mappls-dropup-marker)
- [Marker using HTML](https://about.mappls.com/api/web-sdk/vector-map-example/Markers/mappls-htmlmarker)
- [Linked Marker](https://about.mappls.com/api/web-sdk/vector-map-example/Markers/mappls-linked-marker)
- [Marker with Custom Popup](https://about.mappls.com/api/web-sdk/vector-map-example/Markers/mappls-marker-custompopup)
- [Marker with Popup](https://about.mappls.com/api/web-sdk/vector-map-example/Markers/mappls-markerpopup)
- [Multiple Marker using GeoJSON](https://about.mappls.com/api/web-sdk/vector-map-example/Markers/mappls-multiplemarker-geojson)



## Info Windows

[LIVE DEMO](https://about.mappls.com/api/web-sdk/vector-map-example/InfoWindow/mappls-infowindow) 

Info Windows are a convenient way of showing data about a marker or in simple words: what that marker stands for. The Native behaviour of a user to know about any marker is to try and click on it to know what it’s all about and showing an info window would be the way to go about it:

**Please Note**: Our JS supports a default info window that you can leverage but we want you to have an option to customize your info window to fit in with your UI and you can do so in the CSS.

For a quick sample or a demo you can follow up with the links on live Demo

For details , please read article in [Info Windows](https://github.com/mappls-api/mappls-web-maps-js/blob/main/docs/V3.0/infoWindows.md)

### Info Window Quick Reference

- [InfoWindow Properties](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/infoWindows.md#InfoWindow-Properties)

- [Remove InfoWindow](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/infoWindows.md#Remove-InfoWindow)

### Using Info Window Sample Codes for Quick Reference

- [Simple InfoWindow](https://about.mappls.com/api/web-sdk/vector-map-example/InfoWindow/mappls-infowindow)
- [Custom InfoWindow](https://about.mappls.com/api/web-sdk/vector-map-example/InfoWindow/mappls-custom-infowindow)
- [InfoWindow with Header](https://about.mappls.com/api/web-sdk/vector-map-example/InfoWindow/mappls-infowindow-with-header)


## Polylines

[LIVE DEMO](https://about.mappls.com/api/web-sdk/vector-map-example/Polyline/mappls-polyline) 

Polylines are a way of showing movement or transit on a map. We at Mappls understand the ways you can leverage the features offered by a map and one among them is a Polyline.

Polylines are continuous lines consisting of one or more line segments (preferably a geopath). To add a polyline, initialize map as shown in the previous sections and then create a data set. What is a data set? The Data set is the collection of points (latitude and longitude) over which you want the polyline to be drawn.

For details , please read article in [Polylines](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/polylines.md)

### Polyline Quick Reference - Check out our vast list of sample codes for polylines.

- [Polyline](https://about.mappls.com/api/web-sdk/vector-map-example/Polyline/mappls-polyline)
- [Animated Polyline](https://about.mappls.com/api/web-sdk/vector-map-example/Polyline/mappls-animated-polyline)
- [Animated Marker with Polyline](https://about.mappls.com/api/web-sdk/vector-map-example/Polyline/mappls-animatedmarker-Polyline)
- [Bezier Curve Dashed Polyline](https://about.mappls.com/api/web-sdk/vector-map-example/Polyline/mappls-curve-dashed-polyline)
- [Bezier Curve Polyline](https://about.mappls.com/api/web-sdk/vector-map-example/Polyline/mappls-curve-polyline)
- [Dashed Polyline](https://about.mappls.com/api/web-sdk/vector-map-example/Polyline/mappls-dashed-polyline)
- [Editable Polyline](https://about.mappls.com/api/web-sdk/vector-map-example/Polyline/mappls-editable-polyline)
- [Gradient Polyline](https://about.mappls.com/api/web-sdk/vector-map-example/Polyline/mappls-gradient-polyline)
- [Multi Colored Dashed Polyline](https://about.mappls.com/api/web-sdk/vector-map-example/Polyline/mappls-multicolored-dashed-polyline)
- [Multi Colored Polyline](https://about.mappls.com/api/web-sdk/vector-map-example/Polyline/mappls-multicolored-polyline)


**Remove Polyline**
```js
    mappls.remove({map: map, layer: polyline);
```


In real case scenarios, you’ll need to get the data set on the fly or from a service and then you can leverage the events and functions we’ve learnt about how to plot the polyline. You also might need to beautify your polyline or add transitions for your UI to look marvelous. 

The polyline is just the beginning, but sometimes you’ll need to mark a territory to properly showcase your information. In such cases a polyline might not be the perfect fit but Polygons and Circles may be the apt choice.

## Polygons

Polygons are a way of showing a territory. In cases where you want to showcase data over an area, polygons are your best pick. You can use them to show Geozones as well.

It’s very like generating a polyline, the basic steps remain the same, create a Data set, generate a polygon and add it to the map.

For details , please read article in [Polygon](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/polygon.md)

### Polygon Quick Reference - Check out our vast list of sample codes for polygons.

- [Simple Polygon](https://about.mappls.com/api/web-sdk/vector-map-example/Polygon/mappls-polygon)

- [Polygon Properties](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/polygon.md#polygon-properties)

- [Polygon Events](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/polygon.md#polygon-events)

- [Editable Polygon](https://about.mappls.com/api/web-sdk/vector-map-example/Polygon/mappls-editable-polygon)

- [Polygon with Popup](https://about.mappls.com/api/web-sdk/vector-map-example/Polygon/mappls-polygon-withpopup)

- [Transparent Polygon](https://about.mappls.com/api/web-sdk/vector-map-example/Polygon/mappls-transparent-polygon)
- [Check Position In Polygon](https://about.mappls.com/api/web-sdk/vector-map-example/Polygon/mappls-check-position-polygon)

*Now that we’ve covered polygons let’s have a look at **Circles** which provide another way of showcasing territory.*

## Circles

Circles are way of marking a territory without too much interaction by the user. A circle only has two important values:

-   The Centre point of the circle (in this case it’ll be a latitude with a longitude).
-   The Radius of the circle.

With the two values, you can easily define a quick area of interest on a map.

For details , please read article in [Circle](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/circle.md)

```js
    mappls.Circle()
```

[LIVE DEMO](https://about.mappls.com/api/web-sdk/vector-map-example/Circle/mappls-circle) 

### Circle Quick Reference 


- [Simple Circle](https://about.mappls.com/api/web-sdk/vector-map-example/Circle/mappls-transparent-circle)

- [Transparent Circle](https://about.mappls.com/api/web-sdk/vector-map-example/Circle/mappls-transparent-circle)

- [Circle Properties](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/circle.md#circle-properties)

- [Circle Events](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/circle.md#circle-events)



## Heat Map Overlays

For details , please read article in [Heatmap Overlays](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/heatMap.md)

[LIVE DEMO](https://about.mappls.com/api/web-sdk/vector-map-example/HeatmapOverlays/mappls-heatmap) 

### HeatMap Quick Reference 

- [Heatmap on Click](https://about.mappls.com/api/web-sdk/vector-map-example/HeatmapOverlays/mappls-heatmap-onclick)
- [Heatmap on Overmouse](https://about.mappls.com/api/web-sdk/vector-map-example/HeatmapOverlays/mappls-heatmap-overmouse)
- [HeatMap](https://about.mappls.com/api/web-sdk/vector-map-example/HeatmapOverlays/mappls-heatmap)

- [Heatmap Properties](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/heatMap.md#heatmap-properties)



## Add Geojson layer

For details, please read article in [GeoJSON ](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/geoJson.md)

[Live Demo](https://about.mappls.com/api/web-sdk/vector-map-example/GeoJSON/mappls-geojson) 

*GeoJSON Supports marker, polyline and polygon*

***Marker Property support in geojson***

1. description
2. icon 
3. icon-size 
4. icon-offset
5. text 
6. text-size
7. text-offset

***Polyline Property support in geojson:***

1. stroke
2. stroke-opacity
3. stroke-width

***Polygon Property support in geojson:***

1. stroke
2. fill color
3. fill opacity

```js
    new mappls.addGeoJson({map:map,data:geoData,fitbounds:true,cType:0});
```

### Geojson Quick Reference 

- [Add GeoJSON](https://about.mappls.com/api/web-sdk/vector-map-example/GeoJSON/mappls-geojson)
- [Dashed Polyline Using GeoJson](https://about.mappls.com/api/web-sdk/vector-map-example/GeoJSON/mappls-geojson-dashed-polyline)
- [Multi Colored Dashed Polyline Using GeoJson](https://about.mappls.com/api/web-sdk/vector-map-example/GeoJSON/mappls-geojson-multicolored-dashed-polyline)
- [Multiple Marker Using Geojson](https://about.mappls.com/api/web-sdk/vector-map-example/Markers/mappls-multiplemarker-geojson)

- [Add GeoJSON Properties](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/geoJson.md#Add-GeoJSON-Properties)


**Remove Layer**
```js
    new mappls.remove({map:map,layer:jsonData});
```


## KML Overlay

**KML**: [Keyhole Markup Language](https://www.opengeospatial.org/standards/kml) is a file format used to display geographic data on maps.
Using this plugin, you can overlay KML data over Mappls Maps for web.

[LIVE DEMO](https://about.mappls.com/api/web-sdk/vector-map-example/KML/mappls-kml) 

#### Important Notes to remember
1. Only KML data supported.
2. KML file **must** have absolute path or raw KML string 
(in variable or in textbox)
3. All internal URL's path **must** be absolute. 
(for icon path etc)
4. File must not be password protected.
5. File must be CORS enabled from the server where they are hosted.
6. File must follow KML standard strictly.


- **KML Method**

```js
    var url="https://www.mappls.com/api/advanced-maps/doc/sample/mmi.kml";
    Mappls.KmlLayer({map:map,url:url,cType:1,fitbounds:true,fitboundOptions:{padding:200}});
```

- [**KML Properties**:](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/kml.md#KML-Properties)

For details, please read article in [KML Overlay](https://github.com/mappls-api/mappls-web-maps-js/blob/main/docs/V3.0/kml.md)


## Set mappls style

Mappls offers a range of preset styles to rendering the map. The user has to retrieve a list of styles for a specific account. 
The listing api would help in rendering specific style as well as facilitate the switching of style themes. 
For details, please read article in [MapStyles ](https://raw.githubusercontent.com/mappls-api/mappls-web-maps-js/main/docs/V3.0/Set-mappls-Style.md)

**Please Note**: For a more detailed code snippet follow the links provided above to see the sample code or see a live demo.

<br>

**Footnotes**: 
- <sup>2: Country/territory list provided above.</sup>
- 

<br>

For any queries and support, please contact: 

[<img src="https://about.mappls.com/images/mappls-logo.svg" height="40"/> </p>](https://about.mappls.com/api/)
Email us at [apisupport@mappls.com](mailto:apisupport@mappls.com)


![](https://www.mapmyindia.com/api/img/icons/support.png)
[Support](https://about.mappls.com/contact/)
Need support? contact us!

<br></br>
<br></br>

[<p align="center"> <img src="https://www.mapmyindia.com/api/img/icons/stack-overflow.png"/> ](https://stackoverflow.com/questions/tagged/mappls-api)[![](https://www.mapmyindia.com/api/img/icons/blog.png)](https://about.mappls.com/blog/)[![](https://www.mapmyindia.com/api/img/icons/gethub.png)](https://github.com/Mappls-api)[<img src="https://mmi-api-team.s3.ap-south-1.amazonaws.com/API-Team/npm-logo.one-third%5B1%5D.png" height="40"/> </p>](https://www.npmjs.com/org/mapmyindia) 



[<p align="center"> <img src="https://www.mapmyindia.com/june-newsletter/icon4.png"/> ](https://www.facebook.com/Mapplsofficial)[![](https://www.mapmyindia.com/june-newsletter/icon2.png)](https://twitter.com/mappls)[![](https://www.mapmyindia.com/newsletter/2017/aug/llinkedin.png)](https://www.linkedin.com/company/mappls/)[![](https://www.mapmyindia.com/june-newsletter/icon3.png)](https://www.youtube.com/channel/UCAWvWsh-dZLLeUU7_J9HiOA)




<div align="center">@ Copyright 2022 CE Info Systems Ltd. All Rights Reserved.</div>

<div align="center"> <a href="https://about.mappls.com/api/terms-&-conditions">Terms & Conditions</a> | <a href="https://about.mappls.com/about/privacy-policy">Privacy Policy</a> | <a href="https://about.mappls.com/pdf/mapmyIndia-sustainability-policy-healt-labour-rules-supplir-sustainability.pdf">Supplier Sustainability Policy</a> | <a href="https://about.mappls.com/pdf/Health-Safety-Management.pdf">Health & Safety Policy</a> | <a href="https://about.mappls.com/pdf/Environment-Sustainability-Policy-CSR-Report.pdf">Environmental Policy & CSR Report</a>

<div align="center">Customer Care: +91-9999333223</div>
