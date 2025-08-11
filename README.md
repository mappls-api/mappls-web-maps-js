## **Important Note** – Please read first

> The [main](https://github.com/mappls-api/mappls-web-maps-js/tree/main) branch contains the documentation for releases using the updated Authorization & Authentication mechanism introduced in August 2025.  
> If you wish to use the releases that use the legacy authentication method based on OAuth 2.0, please refer to the [auth-legacy](https://github.com/mappls-api/mappls-web-maps-js/tree/auth-legacy) branch.
<br>



[<img src="https://about.mappls.com/images/mappls-b-logo.svg" height="60"/> </p>](https://www.mapmyindia.com/api)

# Mappls Web Maps JS

Explore the largest Mappls directory of APIs & SDKs for maps, routes and search.

Our APIs, SDKs, and live updating map data available for [200+ countries & territories](https://github.com/MapmyIndia/mapmyindia-rest-api/blob/master/docs/countryISO.md) to give developer's tool to build better mapping, navigation, and search experiences across different platforms.

This page will be continually enhanced to offer more insights and reference materials on how to best utilize our Vector Maps JS SDK for Web.

You can get your api key to be used for access here: [https://auth.mappls.com/console](https://auth.mappls.com/console)

## [Table Of Content]()
- [Mappls Web Maps JS](#mappls-web-maps-js)
  - [Table Of Content](#table-of-content)
  - [Introduction](#introduction)
  - [Web Map Features](#web-map-features)
  - [Getting Access](#getting-access)
  - [Authentication Object - `access_token` mandatory query parameter.](#authentication-object---access_token-mandatory-query-parameter)
  - [Getting Started](#getting-started)
  - [Understanding Map Methods, Events \& Properties](#understanding-map-methods-events--properties)
      - [Adding the Map Script to your web page](#adding-the-map-script-to-your-web-page)
    - [Map Methods, Events \& Properties](#map-methods-events--properties)
  - [Markers](#markers)
    - [Types of Markers](#types-of-markers)
    - [Marker Implementation](#marker-implementation)
    - [Marker Methods,Events \& Properties](#marker-methodsevents--properties)
    - [Markers Quick Reference:](#markers-quick-reference)
    - [View Sample Codes for Quick Reference](#view-sample-codes-for-quick-reference)
  - [Heat Map Overlays](#heat-map-overlays)
    - [HeatMap Quick Reference](#heatmap-quick-reference)
  - [Add Geojson layer](#add-geojson-layer)
    - [Geojson Quick Reference](#geojson-quick-reference)
  - [KML Overlay](#kml-overlay)
      - [Important Notes to remember](#important-notes-to-remember)
  - [Info Windows](#info-windows)
    - [Types of Information windows](#types-of-information-windows)
    - [Info Window Quick Reference](#info-window-quick-reference)
  - [Feature Classes](#feature-classes)
  - [Polylines](#polylines)
    - [Polyline Quick Reference - Check out our vast list of sample codes for different polylines styles.](#polyline-quick-reference---check-out-our-vast-list-of-sample-codes-for-different-polylines-styles)
  - [Polygons](#polygons)
    - [Polygon Quick Reference - Check out our vast list of sample codes for polygons.](#polygon-quick-reference---check-out-our-vast-list-of-sample-codes-for-polygons)
  - [Circles](#circles)
    - [Circle Quick Reference](#circle-quick-reference)
  - [Set mappls style](#set-mappls-style)

| Version | Remarks | Author |
|--|--|--|
| 1.0 | Initial Commit  |Mappls API Team ([PK](https://github.com/prabhjot729/))|



## Introduction

The Mappls Web Maps JavaScript SDK is a tool that enables the creation and customization of interactive maps for both India and the global context. Developed by Mappls (MapmyIndia) India's leading Map provider, this SDK is designed to produce mobile-friendly maps with a user-friendly interface and excellent performance. It consists of a set of classes and functions that allow developers to incorporate a wide range of map features into their web and mobile applications.

## Web Map Features

 - **`Zoom`**: A map of India that can be panned or scrolled, allowing users to explore it in various levels of detail. The highest level of detail is achieved at a zoom level of 22, while the lowest level provides a global view at zoom level 1.
  - **`Overlays`**: We recognize the significance of maps in businesses, and that's why, at Mappls, we offer pre-made overlays that can be easily integrated into your code, streamlining the process and reducing the need for repetitive code.
  -  **`Map Markers (Pushpins)`**: You can pinpoint any location using the default map markers (pushpin) feature, and then you have the flexibility to customize its appearance to align with the unique style of your application. Check out the Plug-ins section for additional enhancements that can elevate your customization options.
 -  **`Info Windows (Pop-ups)`**: When a user clicks on a pushpin, an information window automatically appears, allowing user to display location-specific content. You have the flexibility to customize its appearance and behavior to perfectly match your UI and enhance its appeal.
 - **`Polylines`**: Connect any two points or even more with out of the box Mappls polylines dedicated to high customizability and performance to suit your use cases. Note: Have a look at the plug-ins we provide to make your polylines have an edge up and suit your use cases in a more integrated manner.
-  **`Polygons`**: Show a region in spotlight with a polygon and show various localized data based on it.
 - **`Circles`:** Circles are way of marking a territory without too much interaction by the user.You can draw a circle around a given location.
-   **`Controls`**: We understand the different use cases a user can come accross with a map, so we provide the flexibility of control that can be turned off or on based on your requirement and override our controls outlook by providing your own styles or CSS so that you can move them or customize them completely. Controls include:
    -  **`Zoom Bar`**: (appears by default at the centre on the right side). Helps to provide zoom in and zoom out functionality to the map by default.
     - **`Map Layer Control`**: Allows to change the map view from basic to hybrid and regional. Also allows to show traffic layer on map.
    - **`Fullscreen Control`**: Allows to view a full screen map.
    - **`Current Location Control`**: Scopes the Map to the viewer’s current location.**  
	
`Note`:**The location settings must be turned on and must allow the site to fetch the location for this control to work.**

**Please Note**: Mappls(MapmyIndia) may extend and enhance functionality for its interactive map API in future, which will be documented in this section, and which will be available through the Mappls.

## Getting Access

Before using the API in the your solution, please ensure that the related access is enabled in the [Mappls Console](https://auth.mappls.com/console/), within your app - be it for Mobile OR Web or Cloud integration.

1. Copy and paste the key from your `credentials` section from your API [keys](https://auth.mappls.com/console/) into the `access_token` query parameter.
    - Your static key can be secured by whitelisting its usage for particular IPs (in case of cloud app usage) OR a set of domains (in case of a web app)
    - Your static key obtained from your Console is to be passed as a query parameter: `access_token`.

## Authentication Object - `access_token` mandatory query parameter.

-  `access_token`: "hklmgbwzrxncdyavtsuojqpiefrbhqplnm".

## Getting Started

Now that you’re all caught up with the features let’s get down right to them implementing and look at how can you integrate our interactive Map to your Website from scratch.

## Understanding Map Methods, Events & Properties

[Mappls Live Demo](https://about.mappls.com/api/web-sdk/vector-map-example/Maps/mappls-default-map) | [CodePen Implementation](https://codepen.io/mappls/pen/BaJYqLz)

The easiest way to start loading maps in a web page is with a “Hello World” sample code, you can download or view a working “Hello World” sample from the links for adding your first marker below.

#### Adding the Map Script to your web page

Follow the below steps to integrate Mappls interactive Maps into your existing code base or even a File -> New Project.
- Declare application as HTML5:
Define `<!DOCTYPE html>` on top of your HTML.
- Integrate Interactive maps from Mappls into your browser application by simply including Mappls's interactive map API in your script source in the head section.

    ```html
      <script src="https://sdk.mappls.com/map/sdk/web?v=3.0&access_token=<Static Key>"></script>
    ```    
    **Important:**
    - Please ensure that you insert your *static key* in place of `<Static Key>`
    - *`v`*: This is the version. Please keep as the latest version: `3.0`.
    - *`layer`*: The type of map applicable for the project. The default is `vector`. Alternate value is `raster`. 
    
    Please discuss with [apisupport@mappls.com](mailto:apisupport@mappls.com) for futher clarification and support.

- Define style in the head section to load your CSS. CSS can be defined as per the developers requirement (Extenal, Internal and inline)
   
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

### Map Methods, Events & Properties

- [Map Properties](./docs/V3.0/mapProperties.md)
- [Map Methods](./docs/V3.0/mapMethods.md)
- [Map Events](./docs/V3.0/mapEvents.md) 


## Markers

Utilizing markers to pinpoint locations is a hassle-free approach. You have the option to use the markers we provide as the default choice, and if you wish to use your own custom markers, we've got that aspect covered as well. 

### Types of Markers

-  **`Stock Markers`**: The one you get out of the box using our Interactive Vector Maps SDK and you can select from a lot of choices.
-  **`Custom Marker`**: In case you want to add your own markers, we’ve handled that for you as well.
-  **`HTML Marker`**: In case you don’t want to add in an image you can use HTML to create a marker and then plot it on the map as well.

For more details, please read article in [Markers](./docs/V3.0/markers.md)


### Marker Implementation

[Mappls Live Demo](https://about.mappls.com/api/web-sdk/vector-map-example/Markers/mappls-singlemarker) | [Code Pen Implementation](https://codepen.io/mappls/pen/XWVZBXL)

The easiest way to start loading maps with simple markers in a web page is with sample code given on the link above, you can download or view a working sample with your authorized access keys. 



**Method to add marker on map**

**`mappls.Marker`**

```js
var marker = new mappls.Marker({
    map: map,
    position: {"lat": 28.519467,"lng":77.223150}
	});
```

### Marker Methods,Events & Properties

You can fine-tune the map methods, events and properties we offer to align with your unique requirements and amplify the level of customization for your map layer. These functions serve as a handy resource for promptly addressing specific events or scenarios.

### Markers Quick Reference:

- [Marker Properties](./docs/V3.0/markerProperties.md)
- [Marker Methods](./docs/V3.0/markerMethods.md)
  
- [Marker Events](./docs/V3.0/markerEvents.md)

- [Multiple Marker with cluster](./docs/V3.0/markers.md#Multiple-Marker-With-cluster)

- [GeoJSON Bulk Marker](./docs/V3.0/markers.md#geojson-bulk-markers)

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

## Heat Map Overlays

For details , please read article in [Heatmap Overlays](./docs/V3.0/heatMap.md)

[Mappls Live Demo](https://about.mappls.com/api/web-sdk/vector-map-example/HeatmapOverlays/mappls-heatmap) | [Code Pen Implementation](https://codepen.io/mappls/pen/MWrQqaK)

### HeatMap Quick Reference 

- [Heatmap on Click](https://about.mappls.com/api/web-sdk/vector-map-example/HeatmapOverlays/mappls-heatmap-onclick)
  
- [Heatmap on Overmouse](https://about.mappls.com/api/web-sdk/vector-map-example/HeatmapOverlays/mappls-heatmap-overmouse)
  
- [HeatMap](https://about.mappls.com/api/web-sdk/vector-map-example/HeatmapOverlays/mappls-heatmap)

- [Heatmap Properties](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/heatMap.md#heatmap-properties)

## Add Geojson layer

For details, please read article in [GeoJSON ](./docs/V3.0/geoJson.md)

[Mappls Live Demo](https://about.mappls.com/api/web-sdk/vector-map-example/GeoJSON/mappls-geojson) | [Code Pen Implementation](https://codepen.io/mappls/pen/GRyQXpY)

*GeoJSON Supports marker, polyline and polygon addition and Style properties*

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


**Remove Layer Method**
```js
    new mappls.remove({map:map,layer:jsonData});
```


## KML Overlay

**KML**: [Keyhole Markup Language](https://www.opengeospatial.org/standards/kml) is a file format employed to showcase geographical data on maps. With this plugin, you have the capability to superimpose KML data onto Mappls Maps for web applications.

[Mappls Live Demo](https://about.mappls.com/api/web-sdk/vector-map-example/KML/mappls-kml) | [Code Pen Implementation](https://codepen.io/mappls/pen/VwyQGZy)

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

- [**KML Properties**:](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/kml.md)
 #KML-Properties

For details, please read article in [KML Overlay](./docs/V3.0/kml.md)

## Info Windows

[Mappls Live Demo](https://about.mappls.com/api/web-sdk/vector-map-example/InfoWindow/mappls-infowindow) | [Code Pen Implementation](https://codepen.io/mappls/pen/KKZQxwK)

Info Windows provide a user-friendly method for displaying information related to a marker, essentially explaining the purpose of that marker. When users encounter a marker, their natural instinct is to click on it to discover more details, and presenting an info window is the ideal approach to fulfill this expectation.

**Please Note**: Our JS supports a default info window that you can leverage but we want you to have an option to customize your info window to fit in with your UI and you can do so by manipulating the CSS.

For a quick sample or a demo you can follow up with the links on live Demo

For more details , please read article in [Info Windows](./docs/V3.0/infoWindows.md)

### Types of Information windows

- [Simple InfoWindow](https://about.mappls.com/api/web-sdk/vector-map-example/InfoWindow/mappls-infowindow)
  
- [Custom InfoWindow](https://about.mappls.com/api/web-sdk/vector-map-example/InfoWindow/mappls-custom-infowindow)
  
- [InfoWindow with Header](https://about.mappls.com/api/web-sdk/vector-map-example/InfoWindow/mappls-infowindow-with-header)


### Info Window Quick Reference

- [Info Window Properties](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/infoWindows.md#InfoWindow-Properties)

- [Remove Info Window](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/infoWindows.md#Remove-InfoWindow)


## Feature Classes

## Polylines

[Mappls Live Demo](https://about.mappls.com/api/web-sdk/vector-map-example/Polyline/mappls-polyline) | [Code Pen Implementation](https://codepen.io/mappls/pen/BaJYPOO)

Polylines are a means of visualizing movement or routes on a map, and at Mappls, we recognize the various ways you can make use of a map's capabilities, with Polylines being one of them.

Polylines are essentially uninterrupted lines formed by one or more line segments, preferably represented as a geopath. To include a polyline, follow the initial map setup as described in the earlier sections, and then establish a dataset. What exactly is a dataset? It's the assembly of points (latitude and longitude coordinates) that defines the path along which you wish the polyline to be depicted.

For details , please read article in [Polylines](./docs/V3.0/polyline.md)

### Polyline Quick Reference - Check out our vast list of sample codes for different polylines styles.

- ##### [Polyline](https://about.mappls.com/api/web-sdk/vector-map-example/Polyline/mappls-polyline)

- ##### [Animated Polyline](https://about.mappls.com/api/web-sdk/vector-map-example/Polyline/mappls-animated-polyline)
- ##### [Animated Marker with Polyline](https://about.mappls.com/api/web-sdk/vector-map-example/Polyline/mappls-animatedmarker-Polyline)
- ##### [Bezier Curve Dashed Polyline](https://about.mappls.com/api/web-sdk/vector-map-example/Polyline/mappls-curve-dashed-polyline)
- ##### [Bezier Curve Polyline](https://about.mappls.com/api/web-sdk/vector-map-example/Polyline/mappls-curve-polyline)
- ##### [Dashed Polyline](https://about.mappls.com/api/web-sdk/vector-map-example/Polyline/mappls-dashed-polyline)
- ##### [Editable Polyline](https://about.mappls.com/api/web-sdk/vector-map-example/Polyline/mappls-editable-polyline)
- ##### [Gradient Polyline](https://about.mappls.com/api/web-sdk/vector-map-example/Polyline/mappls-gradient-polyline)
- ##### [Multi Colored Dashed Polyline](https://about.mappls.com/api/web-sdk/vector-map-example/Polyline/mappls-multicolored-dashed-polyline)
- ##### [Multi Colored Polyline](https://about.mappls.com/api/web-sdk/vector-map-example/Polyline/mappls-multicolored-polyline)


**Remove Polyline Method in JS**
```js
    mappls.remove({map: map, layer: polyline);
```


In real case scenarios, you’ll need to get the data set on the fly or from a service and then you can leverage the events and functions we’ve learnt about how to plot the polyline. You also might need to beautify your polyline or add transitions for your UI to look marvelous. 

The polyline is just the beginning, but sometimes you’ll need to mark a territory to properly showcase your information. In such cases a polyline might not be the perfect fit but Polygons and Circles may be the apt choice.

## Polygons

Polygons are a way of showing a territory. In cases where you want to showcase data over an area, polygons are your best pick. You can use them to show Geozones as well.

It’s very like generating a polyline, the basic steps remain the same, create a Data set, generate a polygon and add it to the map.

For details , please read article in [Polygon](./docs/V3.0/polygon.md)

### Polygon Quick Reference - Check out our vast list of sample codes for polygons.

  - ##### [Simple Polygon](https://about.mappls.com/api/web-sdk/vector-map-example/Polygon/mappls-polygon)

 - ##### [Polygon Properties](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/polygon.md#polygon-properties)

 - ##### [Polygon Events](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/polygon.md#polygon-events)

  - ##### [Editable Polygon](https://about.mappls.com/api/web-sdk/vector-map-example/Polygon/mappls-editable-polygon)

  - ##### [Polygon with Popup](https://about.mappls.com/api/web-sdk/vector-map-example/Polygon/mappls-polygon-withpopup)

 - ##### [Transparent Polygon](https://about.mappls.com/api/web-sdk/vector-map-example/Polygon/mappls-transparent-polygon)
 - ##### [Check Position In Polygon](https://about.mappls.com/api/web-sdk/vector-map-example/Polygon/mappls-check-position-polygon)


## Circles

[Mappls Live Demo](https://about.mappls.com/api/web-sdk/vector-map-example/Circle/mappls-circle) | [Code Pen Implementation](https://codepen.io/mappls/pen/RwxQBzy)

Circles are a method for designating an area on a map with minimal user interaction. A circle is characterized by just two key attributes:

- The central point of the circle, specified by its latitude and longitude coordinates.
- The radius of the circle.
  
With these two values, you can effortlessly outline a specific region of interest on a map.

For more details , please read article in [Circle](./docs/V3.0/circle.md)

```js
    mappls.Circle()
```


### Circle Quick Reference 


  - ##### [Simple Circle](https://about.mappls.com/api/web-sdk/vector-map-example/Circle/mappls-transparent-circle)

  - ##### [Transparent Circle](https://about.mappls.com/api/web-sdk/vector-map-example/Circle/mappls-transparent-circle)

  - ##### [Circle Properties](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/circle.md#circle-properties)

  - ##### [Circle Events](https://github.com/mappls-api/mappls-web-maps-js/blob/master/docs/V3.0/circle.md#circle-events)


## Set mappls style

Mappls provides various pre-defined map styles for rendering purposes. Users can access a list of styles associated with their particular account. The listing API allows for both displaying a specific style and enabling the switching of style themes. For more comprehensive information, please refer to doc for [MapStyles](./docs/V3.0/Set-mappls-style.md)

**Please Note**: For a more detailed code snippet follow the links provided above to see the sample code or see a live demo.

For any queries and support, please contact: 

[<img src="https://about.mappls.com/images/mappls-logo.svg" height="40"/> </p>](https://about.mappls.com)
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

