[<img src="https://about.mappls.com/images/mappls-b-logo.svg" height="60"/> </p>](https://about.mappls.com/api)
[< Back to Table of Contents](../../README.md)
# MapmyIndia Interactive Vector Maps JS SDK for Web !
For access, you can get your api key from [Mappls Console](https://auth.mappls.com/console)

## Map Properties

[Mappls Live Demo](https://about.mappls.com/api/web-sdk/vector-map-auth2/Maps/mappls-set-tilt-map) 

#### Map Properties Quick Reference: 

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


<br>

For any queries and support, please contact: 

[<img src="https://about.mappls.com/images/mappls-logo.svg" height="40"/> </p>](https://about.mappls.com/api/)
Email us at [apisupport@mappls.com](mailto:apisupport@mappls.com)


![](https://about.mappls.com/api/img/icons/support.png)
[Support](https://about.mappls.com/contact/)
Need support? contact us!

<br></br>
<br></br>

[<p align="center"> <img src="https://about.mappls.com/api/img/icons/stack-overflow.png"/> ](https://stackoverflow.com/questions/tagged/mappls-api)[![](https://about.mappls.com/api/img/icons/blog.png)](https://about.mappls.com/blog/)[![](https://about.mappls.com/api/img/icons/gethub.png)](https://github.com/Mappls-api)[<img src="https://mmi-api-team.s3.ap-south-1.amazonaws.com/API-Team/npm-logo.one-third%5B1%5D.png" height="40"/> </p>](https://www.npmjs.com/org/mapmyindia) 



[<p align="center"> <img src="https://about.mappls.com/june-newsletter/icon4.png"/> ](https://www.facebook.com/Mapplsofficial)[![](https://about.mappls.com/june-newsletter/icon2.png)](https://twitter.com/mappls)[![](https://about.mappls.com/newsletter/2017/aug/llinkedin.png)](https://www.linkedin.com/company/mappls/)[![](https://about.mappls.com/june-newsletter/icon3.png)](https://www.youtube.com/channel/UCAWvWsh-dZLLeUU7_J9HiOA)




<div align="center">@ Copyright 2022 CE Info Systems Ltd. All Rights Reserved.</div>

<div align="center"> <a href="https://about.mappls.com/api/terms-&-conditions">Terms & Conditions</a> | <a href="https://about.mappls.com/about/privacy-policy">Privacy Policy</a> | <a href="https://about.mappls.com/pdf/mapmyIndia-sustainability-policy-healt-labour-rules-supplir-sustainability.pdf">Supplier Sustainability Policy</a> | <a href="https://about.mappls.com/pdf/Health-Safety-Management.pdf">Health & Safety Policy</a> | <a href="https://about.mappls.com/pdf/Environment-Sustainability-Policy-CSR-Report.pdf">Environmental Policy & CSR Report</a>

<div align="center">Customer Care: +91-9999333223</div>
