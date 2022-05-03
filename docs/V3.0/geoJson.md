![MapmyIndia APIs](https://about.mappls.com/images/mappls-b-logo.svg)
# MapmyIndia Interactive Vector Maps JS SDK for Web !

You can get your api key to be used in this document here: [https://apis.mappls.com/console/](https://apis.mappls.com/console/)


## GeoJSON Overlay

### Supported Object Types

#### 1. Markers
#### 2. Polylines
#### 3. Polygons

### Overlaying Objects via GeoJSON on map

#### [**Add GeoJSON Properties**](#Add-GeoJSON-Properties)

### *Required*

- **Map**
- **data:** This could be be in the form of mixjson.

```json
	{
		"type": "FeatureCollection",
		"features": [
		{
			"type": "Feature",
			"geometry": {"type": "Point","coordinates": [28.54950,77.2678540]
			},
			"properties": {
				"name": "MapmyIndia old Office",
				"description": "Okhla delhi",
				"icon": "https://apis.mapmyindia.com/map_v3/1.png",
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
				"icon": "https://apis.mapmyindia.com/map_v3/1.png",
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
```

### *Optional*

- **fitbounds:** Fits in the map layer automatically to a bound on which geoJson has made.

```js
	{
		fitbounds: true
	}
```

- **fitboundOptions:** This shows the options aailable on the fitBound property.

```js
	{
		fitboundOptions: {padding: 120,duration:1000}
	}
```

- **cType:** It is for geojson data geometry<br>
    - 0: for lat,lng combination (Default)<br>
    - 1: for lng,lat conbination

```js
    {
        cType: 1
    }
```

#### addGeoJson Method

**`mappls.addGeoJson()`**

```js
	for marker can use : "icon": "1.png", "icon-size":0.55, "icon-offset":[0,-20],
	var mixjson={ 
		"type": "FeatureCollection", 
		"features": [
			{ 
				"type": "Feature", 
				"geometry": {
					"type": "Point",
					"coordinates": [ 77.268038, 28.549652, 0 ] 
					}, 
				"properties": { 
					"name": "MapmyIndia old Office", 
					"description": "Okhla delhi", 
					"styleUrl": "#mmi_office", 
					"styleHash": "-3cca3c32", 
					"icon": "1.png", 
					"stroke": "#33CC00", 
					"stroke-opacity": 0.6509803921568628, 
					"stroke-width": 10, 
					"fill": "#FF0000", 
					"fill-opacity": 0.10196078431372549 
					} 
			}, 
			{ 
				"type": "Feature", 
				"geometry": { 
					"type": "Point", 
					"coordinates": [ 77.268952, 28.5510446, 0 ] 
					}, 
				"properties": { 
					"name": "MapmyIndia New Office", 
					"description": "68,Okhla delhi", 
					"styleUrl": "#mmi_office", 
					"styleHash": "-3cca3c32", 
					"icon": "1.png", 
					"stroke": "#33CC00", 
					"stroke-opacity": 0.6509803921568628, 
					"stroke-width": 10, 
					"fill": "#FF0000", 
					"fill-opacity": 0.10196078431372549 
					} 
			}, 
			{ 
				"type": "Feature", 
				"geometry": { 
					"type": "LineString", 
					"coordinates": [[ 77.268953, 28.551042 ], [ 77.268649, 28.551005 ], 
						[ 77.268392, 28.550986 ], [ 77.268231, 28.550967 ], 
						[ 77.268177, 28.550967 ], [ 77.268016, 28.550958 ], 
						[ 77.267587, 28.55092 ], [ 77.267651, 28.550722 ], 
						[ 77.267823, 28.55042 ], [ 77.267802, 28.550128 ], 
						[ 77.267995, 28.549751 ], [ 77.268039, 28.549652 ]]
					}, 
				"properties": { 
					"name": "Direction1", 
					"styleUrl": "#mmi_office", 
					"styleHash": "-3cca3c32", 
					"icon": "1.png", 
					"description": "Direction2", 
					"stroke": "#33CC00", 
					"stroke-opacity": 0.6509803921568628, 
					"stroke-width": 10, 
					"fill": "#FF0000", 
					"fill-opacity": 1.10196078431372549 
					} 
				}, 
				{ 
					"type": "Feature", 
					"geometry": { 
						"type": "Polygon", 
						"coordinates": [[ 77.2687822, 28.550868 ],[ 77.268996, 28.550868 ],
							[ 77.269039, 28.550383 ], [ 77.268835, 28.550388]] 
						}, 
					"properties": { 
						"name": "MapmyIndia Head Office", 
						"styleUrl": "#mmi_area", 
						"styleHash": "5617b970", 
						"stroke": "#33CC00", 
						"stroke-opacity": 0.6509803921568628, 
						"stroke-width": 3, 
						"fill": "#33CC00", 
						"fill-opacity": 0.6509803921568628 
						} 
				}] 
		};
	var mix=mappls.addGeoJson({
		map:map,
		data:mixjson,
		overlap:false, //or false; default: true; not mandatory for markers.
		preserveViewport:true
	});
```

#### Additional Properties for Markers

```js
	"icon": "1.png",  //for customizing marker
	"icon-size":1,  // size percentage of the marker: ranging from 
	"text":"2",  // text on marker
	"text-size":10,  // font size on marker
	"text-offset":[0,0],  //map anchor offset from the center of icon image.
	"text-color":"red" //color of text on marker
```

### Remove GeoJSON Layer

```js
	mappls.remove({map:map,layer:geoJSONLayer});
```

For any queries and support, please contact: 

![Email](https://cdn.mapmyindia.com/mappls_web/maps_widget_v2/images/mappls.svg?service=google_gsuite) 
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


© Copyright 2022 CE Info Systems  Ltd. All Rights Reserved. 