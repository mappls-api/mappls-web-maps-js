![MapmyIndia APIs](https://about.mappls.com/images/mappls-b-logo.svg)

# MapmyIndia Interactive Vector Maps JS SDK for Web !

You can get your api key to be used in this document here: [https://apis.mappls.com/console/](https://apis.mappls.com/console/)

## Marker Properties Quick Reference:

### *Required*

- **Map Object**
- **Position:** Lat Lng Object

### Optional

- **fitbounds:** Pans and zooms the map to contain its visible area within the specified geographical bounds. This function will also reset the map's bearing to 0 if bearing is nonzero. By default it is false.

```js
    {
        fitbounds: true
    }
```

- **fitboundOptions:** Options in fitbounds like padding and time duration.

```js
    {
        fitboundOptions: {padding: 120,duration:1000}
    }
```

- **icon:** Enter the url of the icon for marker.<br> CORS should be enabled for absolute URL.

```js
    {
        icon: 'icon_url'
    }
```

- **offset:** Offset is used to set the correct position on the marker.

```js
    {
        offset: [x,y]
    }
```

- **width:** Define the icon width of the marker.

```js
    {
        width: 25
    }
```

- **height:** Define the icon height of the marker.

```js
    {
        height: 25
    }
```

- **html:** DOM element to use as a marker.

```js
    html: '<div style="white-space:nowrap;font-size:10px;padding left:15px;color:#fff">Hello World</div>'
```

- **popupOptions:** This includes the options to be used in showing the popup.

```js
    {
        popupOptions: {offset: {'bottom': [0, -20]}}
    }
```

- **popupHtml:** This shows the HTML you want on marker popup.

```js
    {
        popupHtml: 'MapmyIndia'
    }
```

- **draggable:** This property meant to drag the markers on the map. By default the value is false.

```js
    {
        draggable: false
    }
```

- **clusters:** To show the cluster on the map in case of multiple markers by geoJson. By default the value is true.

```js
    {
        clusters: true
    }
```

- **clustersOptions:** To show the multiple options we have on showing clusters on the map in case of multiple markers by geoJson.

```js
    {
        clustersOptions: {"color": "blue","bgcolor":"red"}
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