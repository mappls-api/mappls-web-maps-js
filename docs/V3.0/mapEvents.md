[<img src="https://about.mappls.com/images/mappls-b-logo.svg" height="60"/> </p>](https://about.mappls.com/api)
[< Back to Table of Contents](../../README.md)
# MapmyIndia Interactive Vector Maps JS SDK for Web !

For access, you can get your api key from [Mappls Console](https://auth.mappls.com/console)

Map Events -
[Mappls Live Demo](https://about.mappls.com/api/web-sdk/vector-map-auth2/Maps/mappls-map-load-event)

## Map Events Quick References 

### Listening to Map Events via addListener()

- **load:** 

```js
        map.addListener('load', function () { console.log('load');}); 
```

- **click:** Fired when a pointing device (usually a mouse) is pressed and released at the same point on the map.

```js
        map.addListener('click', function () { console.log('click');});
```

- **dblclick:** Fired when a pointing device (usually a mouse) is clicked twice at the same point on the map.

```js
        map.addListener('dblclick', function () { console.log('dblclick');});
```

- **drag:** Fired repeatedly during a "drag to pan" interaction.

```js
        map.addListener('drag', function () { console.log('drag');});
```

- **dragstart:** Fired when a "drag to pan" interaction starts.

```js
        map.addListener('dragstart', function () { console.log('dragstart');});
```

- **dragend:** Fired when a "drag to pan" interaction ends.

```js
        map.addListener('dragend', function () { console.log('dragend');});
```

- **idle:** Fired after the last frame rendered before the map enters an "idle" state:
    - No camera transitions are in progress
    - All currently requested tiles have loaded
    - All fade/transition animations have completed

```js
        map.addListener('idle', function () { console.log('idle');});
```

- **mousemove:** Fired when a pointing device (usually a mouse) is moved within the map.

```js
        map.addListener('mousemove', function () { console.log('mousemove');});
```

- **mouseout:** Fired when a point device (usually a mouse) leaves the map's canvas

```js
        map.addListener('mouseout', function () { console.log('mouseout');});
```

- **mouseover:** Fired when a pointing device (usually a mouse) is moved within the map.

```js
        map.addListener('mouseover', function () { console.log('mouseover');});
```

- **mouseup:** Fired when a pointing device button (usually the left mouse button) is released after being pressed on the map.

```js
        map.addListener('mouseup', function () { console.log('mouseup');});
```

- **mousedown:** Fired when a pointing device button (usually the left mouse button) is pressed down on the map.

```js
        map.addListener('mousedown', function () { console.log('mousedown');});
```

- **mouseenter:** Fired when a pointing device (usually a mouse) enters the boundary of a map layer or feature that has event listeners attached.

```js
        map.addListener('mouseenter', function () { console.log('mouseenter');});
```

- **mouseleave:** Fired when a pointing device (usually a mouse) leaves the boundary of a map layer or feature that has event listeners attached.

```js
        map.addListener('mouseleave', function () { console.log('mouseleave');});
```

- **contextmenu:** Fired when the right button of the mouse is clicked or the context menu key is pressed within the map.

```js
        map.addListener('contextmenu', function () { console.log('contextmenu');});
```

- **wheel:** Fired when a wheel event occurs within the map.

```js
        map.addListener('wheel', function () { console.log('wheel');});
```

- **touchstart:** Fired when one or more fingers touch the map’s surface. This event marks the beginning of a touch interaction.

```js
        map.addListener('touchstart', function () { console.log('touchstart');});
```

- **touchmove:** Fired continuously as a finger moves across the map’s surface during a touch interaction.

```js
        map.addListener('touchmove', function () { console.log('touchmove');});
```

- **touchend:** Fired when a touchend event occurs within the map.

```js
        map.addListener('touchend', function () { console.log('touchend');});
```

- **touchcancel:** Fired when a touch interaction is interrupted or canceled unexpectedly — for example, if an alert box appears or the system cancels the gesture.
```js
        map.addListener('touchcancel', function () { console.log('touchcancel');});
```


- **movestart:** Fired when the map movement (panning, zooming, rotating, or pitching) starts, usually at the beginning of an animated transition or user interaction.

```js
        map.addListener('movestart', function () { console.log('movestart');});
```

- **move:** Fired repeatedly during an animated transition from one view to another.

```js
        map.addListener('move', function () { console.log('move');});
```

- **moveend:** Fired just after the map completes a transition from one view to another.

```js
        map.addListener('moveend', function () { console.log('moveend');});
```

- **rotatestart:** Fired when the map’s bearing (rotation) starts changing, either by user interaction (drag to rotate) or programmatically.

```js
        map.addListener('rotatestart', function () { console.log('rotatestart');});
```

- **rotate:** Fired continuously while the map’s bearing (rotation) is changing during a drag or animation.

```js
        map.addListener('rotate', function () { console.log('rotate');});
```

- **rotateend:** Fired when the map’s bearing (rotation) finishes changing, after the rotation interaction or animation completes.
```js
        map.addListener('rotateend', function () { console.log('rotateend');});
```

- **pitchstart:** Fired when the map’s tilt (pitch) starts changing, either by user interaction or methods.

```js
        map.addListener('pitchstart', function () { console.log('pitchstart');});
```

- **pitch:** Fired continuously while the map’s tilt (pitch) is changing due to user interaction or methods.
```js
        map.addListener('pitch', function () { console.log('pitch');});
```

- **pitchend:** Fired immediately after the map's pitch (tilt) finishes changing as the result of either user interaction or methods.

```js
        map.addListener('pitchend', function () { console.log('pitchend');});
```

- **zoomstart:** Fired when zooming starts.

```js
        map.addListener('zoomstart', function () { console.log('zoomstart');});
```

- **zoom:** Fired continuously during zoom interactions.

```js
        map.addListener('zoom', function () { console.log('zoom');});
```

- **zoomend:** Fired when a zoom interaction ends.

```js
        map.addListener('zoomend', function () { console.log('zoomend');});
```

- **render:** Fired whenever the map is repainted. This occurs frequently during animations, movements, or visual updates on the map.

```js
        map.addListener('render', function () { console.log('render');});
```

- **sourcedataloading:** Fired when the map starts loading data for a source, such as vector tiles, GeoJSON, or raster imagery. It indicates that the source data request has been initiated.

```js
        map.addListener('sourcedataloading', function () { console.log('sourcedataloading');});
```

- **sourcedata:** Fired when the map successfully loads or updates data from a source. This event helps you track when source data (like tiles or features) has finished loading and is ready for use.

```js
        map.addListener('sourcedata', function () { console.log('sourcedata');});
```

- **styledataloading:** Fired when the map begins loading a new style or when style resources (such as layers, sources, or images) are being fetched or reloaded.

```js
        map.addListener('styledataloading', function () { console.log('styledataloading');});
```

- **styledata:** Fired when the map’s style data has finished loading or updating. This means all style elements (like layers and sources) are fully available for rendering.

```js
        map.addListener('styledata', function () { console.log('styledata');});
```

- **data:** Fired whenever any map data (such as style, source, or tile information) is loaded or updated. This helps track ongoing updates that affect rendering, including new tiles or modified layers.

```js
        map.addListener('data', function () { console.log('data');});
```

- **resize:** Fired when the map’s container is resized. This event occurs whenever the map’s dimensions change — for example, when the browser window is resized or the map container’s CSS size changes.

```js
        map.addListener('resize', function () { console.log('resize');});
```

- **remove:** Fired when the map instance is removed from the DOM using map.remove(). This signals that the map’s WebGL context and event listeners are being cleaned up.

```js
        map.addListener('remove', function () { console.log('remove');});
```

- **error:** Fired when the map encounters an error while loading resources, sources, or rendering. This event is useful for debugging and handling unexpected map failures.

```js
        map.addListener('error', function () { console.log('error');});
```

- **webglcontextlost:** Fired when the map’s WebGL context is lost, usually due to GPU resource limits or browser tab suspension. During this time, rendering stops until the context is restored.

```js
        map.addListener('webglcontextlost', function () { console.log('webglcontextlost');});
```

- **webglcontextrestored:** Fired when the WebGL context that was previously lost is successfully restored. This allows the map to resume rendering after a graphics reset.

```js
        map.addListener('webglcontextrestored', function () { console.log('webglcontextrestored');});
```

**Event System**:

1. `addListener:` Pass Event & Callback
2. `clearListeners:` Remove Event
3. `addListenerOnce:` Same as addListener but call once

**Example**

```js
    map.addListener('load', function () { console.log('loaded');}); 
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
