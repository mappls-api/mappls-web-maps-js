![MapmyIndia APIs](https://about.mappls.com/images/mappls-b-logo.svg)
# MapmyIndia Interactive Vector Maps JS SDK for Web !

You can get your api key to be used in this document here: [https://apis.mappls.com/console/](https://apis.mappls.com/console/)

Map Properties

[Live Demo](https://www.mapmyindia.com/api/advanced-maps/WebSDK-LiveDemo/map-properties) | [JS Fiddle](https://jsfiddle.net/mapmyindia_map/0pru8dxo/)

## Map Properties Quick Reference: 

- **Background Color:** `backgroundColor` used for the background of the Map div. This color will be visible when tiles have not yet loaded as the user pans. This option can only be set when the map is initialized.

```js
    {
        backgroundColor: '#fff'
    }
```

- **Disable Double Click Zoom:** Enables/disables zoom and center on double click. Enabled by default i.e. `true`.

```js
    {
        disableDoubleClickZoom: true
    }
```

- **Draggable:** Prevents the map from being dragged. Dragging is enabled by default i.e. `true`.

```js
    {
        draggable: true
    }
```

- **Full Screen Control:** It shows the icon of the full screen on the map. fullscreenControl is enabled by default i.e. `true`.

```js
    {
        fullscreenControl: true
    }
```

- **Heading:** The `heading` for aerial imagery in degrees measured clockwise from cardinal direction North. Headings are snapped to the nearest available angle for which the imagery is available. By default it is 0.

```js
    {
        heading: 100
    }
```

- **maxZoom:** The maximum zoom level which will be displayed on the map. If omitted, or set to null, the maximum zoom from the current map type is used instead. Valid values: Integers between 5 to 18 are supported in zoom level.

```js
    {
        maxZoom: 15
    }
```

- **minZoom:** The minimum zoom level which will be displayed on the map. If omitted, or set to null, the minimum zoom from the current map type is used instead. Valid values: Integers between 5 to 18 are supported in zoom level.

```js
    {
        minZoom: 8
    }
```

- **rotateControl:** The enabled/disabled state of the Rotate control. By default is it `true`.

```js
    {
        rotateControl: true
    }
```

- **rotateControlOptions:** The display options for the Rotate control. By default it is `true`.

```js
    {
        rotateControlOptions: true
    }
```

- **scaleControl:** The initial enabled/disabled state of the Scale control. By default it is `true`.

```js
    {
        scaleControl: true
    }
```

- **scaleControlOptions:** The initial display options for the Scale control. by default it is `true`.

```js
    {
        scaleControlOptions: true
    }
```

- **scrollwheel:** If false, disables zooming on the map using a mouse scroll wheel. The scrollwheel is enabled by default i.e `true`.<br>
*Note: This property is not recommended. To disable zooming using scrollwheel, you can use the gestureHandling property, and set it to either "cooperative" or "none".*

```js
    {
        scrollWheel: true
    }
```

- **tilt:** Controls the automatic switching behavior for the angle of incidence of the map. The only allowed values are 0 to 60. The value 0 causes the map to always use a 0° overhead view regardless of the zoom level and viewport. The value 60 causes the tilt angle to automatically switch to 60 whenever 60° imagery is available for the current zoom level and viewport, and switch back to 0 whenever 60° imagery is not available (this is the default behavior).<br> ***Note:** getTilt returns the current tilt angle, not the value specified by this option. Because getTilt and this option refer to different things, do not bind() the tilt property; doing so may yield unpredictable effects.*

```js
    {
        tilt: 30
    }
```

- **Zoom:** The Initial Map `zoom` level.<br>Valid values: Integers between 5 and 18 zoom level.

```js
    {
        zoom: 5
    }
```

- **zoomControl:** The enabled/disabled state of the Zoom control. By default it is enabled i.e `true`.

```js
    {
        zoomControl: true
    }
```

- **zoomControlOptions:** Any values from the following are possible:
    - `TOP_CENTER`
    - `TOP_LEFT`
    - `TOP_RIGHT`
    - `LEFT_TOP`
    - `RIGHT_TOP`
    - `LEFT_CENTER`
    - `RIGHT_CENTER`
    - `LEFT_BOTTOM`
    - `RIGHT_BOTTOM`
    - `BOTTOM_CENTER`
    - `BOTTOM_LEFT`
    - `BOTTOM_RIGHT`

```js
    {
        zoomControlOptions: {
            position:mappls.ControlPosition.RIGHT_CENTER
            }
    }
```

- **Interactive:** By default value is `true`, if `false` no mouse, touch, or keyboard listeners will be attached.

```js
    {
        interactive: true
    }
```

- **scrollZoom:** By default value is `true`, if `false` scroll to zoom interaction is disabled.

```js
    {
        scrollZoom: true
    }
```

- **traffic:** By default value is `true`, To show traffic control on map.

```js
    {
        traffic: true
    }
```

- **Clickable Icons:** A map icon represents a point of interest, also known as a POI. By default map icons are clickable i.e. `true`.

```js
    {
        clickableIcons: true
    }
```

- **Clickable Icons Callback:** Callback method

```js
    {
        clickableIconsCallback: callBackMethod
    }
    
    callBackMethod(e){
        console.log(e);
    }
```
- **token_callback:**(Optional) Callback method for any token related issues. return error like  {error: "Token Expired", code: 401}

```js
    {
        token_callback: callBackMethod
    }
    
    token_callback(e){ if(e.error='Token Expired') mapObj.setToken('newToken');
        console.log(e);
    }
```
- **Indoor: To show indoor floor plans in Vector SDK. This property should set to True** 

```js
    {
        indoor: true
    }
```
- **Indoor_callback: Indoor Callback Method** 

```js
    {
        indoor_callback: show_ind
    }
```
- **Indoor_position:**  Any values from the following are possible:
    - `TOP_CENTER`
    - `TOP_LEFT`
    - `TOP_RIGHT`
    - `LEFT_TOP`
    - `RIGHT_TOP`
    - `LEFT_CENTER`
    - `RIGHT_CENTER`
    - `LEFT_BOTTOM`
    - `RIGHT_BOTTOM`
    - `BOTTOM_CENTER`
    - `BOTTOM_LEFT`
    - `BOTTOM_RIGHT` 

```js
    {
        indoor_position: 'bottom-left'
    }
```

**Example**:

```js
    map = new mappls.Map(document.getElementById('map'), 
    {
        zoom: 5,
        center: [28.544,77.5454],
        backgroundColor: '#999',
        disableDoubleClickZoom: false,
        zoomControl: false,
        zoomControlOptions: {
                position:mappls.ControlPosition.RIGHT_CENTER
            }, 
        draggable: false,
        scrollwheel: false ,
        minZoom: 5, 
        maxZoom: 18, 
        clickableIcons: false,
        clickableIcons_callback: call_method_name,
        heading: 100,
        tilt: 45,
        indoor: true,
        indoor_callback: show_ind,
        indoor_position: 'bottom-left'
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