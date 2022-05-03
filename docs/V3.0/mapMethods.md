![MapmyIndia APIs](https://about.mappls.com/images/mappls-b-logo.svg)
# MapmyIndia Interactive Vector Maps JS SDK for Web !

You can get your api key to be used in this document here: [https://apis.mappls.com/console/](https://apis.mappls.com/console/)

Map Methods 

[Live Demo](https://www.mapmyindia.com/api/advanced-maps/WebSDK-LiveDemo/map-methods) | [JS Fiddle](https://jsfiddle.net/mapmyindia_map/9o8ezhys/)

## Map Methods Quick Reference: 

- **FitBounds:** Pans and zooms the map to contain its visible area within the specified geographical bounds. This function will also reset the map's bearing to 0 if bearing is nonzero.

**`mappls.fitBounds()`**

```js
    fitBounds = new mappls.fitBounds({
                    map:map,
                    cType:0, bounds:[[76.324462,27.024695],[77.215820,28.971891],[77.225820,28.273891]],
                    options:{
                        padding: 120,
                        duration:1000
                        }
                });
```

- **getBounds:** Returns the lat/lng bounds of the current viewport.

```js
    mapObject.getBounds();
```

- **getCenter:** Returns the position displayed at the center of the map.

```js
    mapObject.getCenter();
```

- **setCenter:** Sets the map's geographical centerpoint.

```js
    mapObject.setCenter({lat: lat,lng: lng});
```

- **getDiv**

```js
    mapObject.getDiv();
```

- **getHeading:** Returns the compass heading of aerial imagery.

```js
    mapObject.getHeading();
```


- **getZoom:** Returns the current zoom level.

```js
    mapObject.getZoom();
```

- **panBy:** Changes the center of the map by the given distance in pixels. If the distance is less than both the width and height of the map, the transition will be smoothly animated.

```js
    map.panBy(array of points([x,y]));
```

- **panTo:** Changes the center of the map to the given LatLng.

```js
    map_object.panTo({lat: lat,lng: lng});
```

- **setheading:** Sets the compass heading for aerial imagery measured in degrees from cardinal direction North.

```js
    map_object.setHeading(100);
```

- **setZoom:** Sets the Zoom level of the current Map.

```js
    map_object.setZoom(12);
```

- **setTilt:** Controls the automatic switching behavior for the angle of incidence of the map. The only allowed values are 0 to 60. setTilt(0) causes the map to always use a 0° overhead view regardless of the zoom level and viewport. setTilt(60) causes the tilt angle to automatically switch to 60 whenever 60° imagery is available for the current zoom level and viewport, and switch back to 0 whenever 60° imagery is not available (this is the default behavior).

```js
    map_object.setTilt(45);
```

- **getTilt:** Returns the current angle of incidence of the map, in degrees from the viewport plane to the map plane. The result will be 0 for imagery taken directly overhead or 60 for 60° imagery.

```js
    map_object.getTilt();
```

- **isMoving:** Returns true if the map is panning, zooming, rotating, or pitching due to a camera animation or user gesture.

```js
    map.isMoving();
```

- **isRotating:** Returns true if the map is rotating due to a camera animation or user gesture.

```js
    map.isRotating();
```

- **addLayer:** A layer defines how data from a specified source will be styled. The JSON of layer to be passed in the addLayer.

```js
    map.addLayer(layer);
```

- **removeLayer:** It removes the layer of the particular layerId you want to remove.

```js
    map.removeLayer();
```

- **getLayer:** Returns the layer with the specified ID in the map's style.

```js
    map.getLayer();
```

- **moveLayer:** Moves a layer to a different z-position.

```js
    map.moveLayer();
```
- **indoor floor:** In case of indoor callback.

```js
    map.floor_show({map: mapobj,floor:any floor no});
```

- **loaded:** Returns a Boolean indicating whether the map is fully loaded.
Returns `false` if the style is not yet fully loaded, or if there has been a change to the sources or style that has not yet fully loaded.

```js
    map.loaded();
```
- **setToken:** Returns a Boolean indicating whether the token set or not.
Returns `false` if the token is not valid else return true.

```js
    map.setToken('newToken');
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