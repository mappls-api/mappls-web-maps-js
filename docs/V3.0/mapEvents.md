![MapmyIndia APIs](https://about.mappls.com/images/mappls-b-logo.svg)
# MapmyIndia Interactive Vector Maps JS SDK for Web !

You can get your api key to be used in this document here: [https://apis.mappls.com/console/](https://apis.mappls.com/console/)

Map Event 

[Live Demo](https://www.mapmyindia.com/api/advanced-maps/WebSDK-LiveDemo/mapEvent) | [JS Fiddle](https://jsfiddle.net/mapmyindia_map/70rn461b/)

## Map Events Quick Reference: 

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

- **contextmenu:** Fired when the right button of the mouse is clicked or the context menu key is pressed within the map.

```js
        map.addListener('contextmenu', function () { console.log('contextmenu');});
```

- **wheel:** Fired when a wheel event occurs within the map.

```js
        map.addListener('wheel', function () { console.log('wheel');});
```

- **touchend:** Fired when a touchend event occurs within the map.

```js
        map.addListener('touchend', function () { console.log('touchend');});
```

- **move:** Fired repeatedly during an animated transition from one view to another.

```js
        map.addListener('move', function () { console.log('move');});
```

- **moveend:** Fired just after the map completes a transition from one view to another.

```js
        map.addListener('moveend', function () { console.log('moveend');});
```

- **rotate:** Fired repeatedly during a "drag to rotate" interaction.

```js
        map.addListener('rotate', function () { console.log('rotate');});
```

- **pitchend:** Fired immediately after the map's pitch (tilt) finishes changing as the result of either user interaction or methods.

```js
        map.addListener('pitchend', function () { console.log('pitchend');});
```

**Event System**:

1. `addListener:` Pass Event & Callback
2. `clearListeners:` Remove Event
3. `addListenerOnce:` Same as addListener but call once

**Example**

```js
    map.addListener('load', function () { console.log('loaded');}); 
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