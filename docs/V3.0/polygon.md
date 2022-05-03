![MapmyIndia APIs](https://about.mappls.com/images/mappls-b-logo.svg)

# MapmyIndia Interactive Vector Maps JS SDK for Web !

You can get your api key to be used in this document here: [https://apis.mappls.com/console/](https://apis.mappls.com/console/)


## Polygon

```js
	new mappls.Polygon
```

### Drawing Polygon

#### [Polygon Properties](#polygon-properties)

### *Required*

- **Map**
- **Path:** This could be be the array of lat lng.

### Example

```js
	mappls_polygon = new mappls.Polygon({
		map: map,
		paths: [{"lng":"77.26872","lat": "28.55101"},
			{"lng":"77.26849","lat":"28.55099"},{"lng":"77.26831","lat":"28.55097"},
			{"lng":"77.26794","lat":"28.55093"},{"lng":"77.2676","lat":"28.55089"},
			{"lng":"77.26756","lat":"28.55123"},{"lng":"77.26758","lat":"28.55145"},
			{"lng":"77.26758","lat":"28.55168"},{"lng":"77.26759","lat":"28.55172"}]
	});
```

### *Optional*

- **fillcolor:** Fills the color of the polygon and All CSS3 colors are supported except for extended named colors.

```js
	{
		fillcolor: "red"
	}
```

- **fillOpacity:** Fills the opacity of the polygon.

```js
	{
		fillOpacity: 0.8
	}
```

- **strokeColor:** Fills the Stroke color of the polygon.

```js
	{
		strokeColor: "blue"
	}
```

- **strokeOpacity:** Fills the Stroke opacity of the polygon.

```js
	{
		strokeOpacity: "black"
	}
```

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

- **popupHtml:** This shows the message you want to print while clicking on the polygon.

```js
	{
		popupHtml: 'Route 1'
	}
```

- **popupOptions:** Options available in printing the message through popupHtml.

```js
	{
		popupOptions: {offset: {'bottom': [0, -20]}}
	}
```


## Example

```js
	mappls_polygon = new mappls.Polygon({
		map: map,
		paths: [{"lng":"77.26872","lat": "28.55101"},
			{"lng":"77.26849","lat":"28.55099"},{"lng":"77.26831","lat":"28.55097"},
			{"lng":"77.26794","lat":"28.55093"},{"lng":"77.2676","lat":"28.55089"},
			{"lng":"77.26756","lat":"28.55123"},{"lng":"77.26758","lat":"28.55145"},
			{"lng":"77.26758","lat":"28.55168"},{"lng":"77.26759","lat":"28.55172"}],
		fillColor: "red",
		fillOpacity: 0.8,
		strokeColor: "red",
		strokeOpacity: 0.8,
		fitbounds: true
		fitboundOptions: {padding: 120,duration:1000},
		popupHtml: 'Route 1',
		popupOptions: {offset: {'bottom': [0, -20]}}
	});
```

### Remove Polygon

```js
	mappls.remove({map: map_object, layer: Polygon_object);
```

### Polygon Events

#### click

```js
	Polygon_object.addListener(('click')), function() {
			alert(`Click Event Works`);
	});
```

#### dblclick

```js
	Polygon_object.addListener(('dblclick')), function() {
			alert(`Double Click Event Works`);
	});
```

#### drag

```js
	Polygon_object.addListener(('drag')), function() {
			alert(`Drag Event Works`);
	});
```

#### dragstart

```js
	Polygon_object.addListener(('dragstart')), function() {
			alert(`Drag Start Event Works`);
	});
```

#### dragend

```js
	Polygon_object.addListener(('dragend')), function() {
			alert(`Dragend Event Works`);
	});
```

#### mousemove

```js
	Polygon_object.addListener(('mousemove')), function() {
			alert(`Mouse Move Event Works`);
	});
```

#### mouseover

```js
	Polygon_object.addListener(('mouseover')), function() {
			alert(`Mouse Over Event Works`);
	});
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