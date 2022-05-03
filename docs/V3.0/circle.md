![MapmyIndia APIs](https://about.mappls.com/images/mappls-b-logo.svg)
# MapmyIndia Interactive Vector Maps JS SDK for Web !

You can get your api key to be used in this document here: [https://apis.mappls.com/console/](https://apis.mappls.com/console/)


## Circle



#### [Circle Properties](#circle-properties)

### *Required*

- **Map**
- **center:** This could be be the array of lat lng.
- **radius:** Radius of the circle.
```js
	{
		radius: 500
	}
```
 
### *Optional*

- **fillcolor:** Fills the color of the circle and is supports all color of CSS3.

```js
	{
		fillcolor: "red"
	}
```

- **fillOpacity:** Fills the opacity of the circle.

```js
	{
		fillOpacity: 0.8
	}
```

- **strokeColor:** Fills the Stroke color of the circle.

```js
	{
		strokeColor: "blue"
	}
```

- **strokeOpacity:** Fills the Stroke opacity of the circle.

```js
	{
		strokeOpacity: "black"
	}
```

- **strokeWeight:** The stroke width in pixels.

```js
	{
		strokeWeight: 2
	}
```

#### Circle Method

**`Mappls.Circle()`**

```js
mappls_circle = new mappls.Circle({
	center: {"lat": "28.519467" ,"lng": "77.223150"},
	map: map,
	radius: 100,
	strokeColor: red,
	strokeOpacity: 0.8,
	strokeWeight: 2,
	fillColor: red,
	fillOpacity: 0.8
});
```

### Remove Circle

```js
	mappls.remove({map: map, layer: circle);
```

### [Circle Events](#circle-events)

#### click

```js
	circle.addListener(('click')), function() {
			alert(`Click Event Works`);
	});
```

#### dblclick

```js
	circle.addListener(('dblclick')), function() {
			alert(`Double Click Event Works`);
	});
```

#### drag

```js
	circle.addListener(('drag')), function() {
			alert(`Drag Event Works`);
	});
```

#### dragstart

```js
	circle.addListener(('dragstart')), function() {
			alert(`Drag Event Works`);
	});
```

#### dragend

```js
	circle.addListener(('dragend')), function() {
			alert(`Dragend Event Works`);
	});
```

#### mousemove

```js
	circle.addListener(('mousemove')), function() {
			alert(`Mouse Move Event Works`);
	});
```

#### mouseover

```js
	circle.addListener(('mouseover')), function() {
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