![MapmyIndia APIs](https://about.mappls.com/images/mappls-b-logo.svg)
# MapmyIndia Interactive Vector Maps JS SDK for Web !

You can get your api key to be used in this document here: [https://apis.mappls.com/console/](https://apis.mappls.com/console/)


## KML Overlay

### Supported Object Types

#### 1. Markers
#### 2. Polylines
#### 3. Polygons


### Overlaying KML on map

#### [KML Properties](#KML-Properties)

### *Required*

- **Map**
- **url:** URL of the KML file.

### *Optional*

- **fitbounds:** Fits in the map layer automatically to a bound on which geoJson has made. By default it is false.

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

#### KmlLayer Method

**`Mappls.KmlLayer()`**

```js
	var url="https://www.mapmyindia.com/api/advanced-maps/doc/sample/mmi.kml"; 
	new mappls.KmlLayer({
		map:map_object,
		url:url,
		cType:1,
		preserveViewport:true
	});
```

### Remove KML Overlay

```js
	mappls.remove({map:map_object,layer:KmlLayer_object});
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