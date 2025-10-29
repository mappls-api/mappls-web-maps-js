[<img src="https://about.mappls.com/images/mappls-b-logo.svg" height="60"/> </p>](https://www.mapmyindia.com/api)
[< Back to Table of Contents](../../README.md)
# MapmyIndia Interactive Vector Maps JS SDK for Web !

For access, you can get your api key from [Mappls Console](https://auth.mappls.com/console)

Map Events -
[Mappls Live Demo](https://www.mapmyindia.com/api/advanced-maps/WebSDK-LiveDemo/mapEvent)

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


![](https://www.mapmyindia.com/api/img/icons/support.png)
[Support](https://about.mappls.com/contact/)
Need support? contact us!

<br></br>
<br></br>

[<p align="center"> <img src="https://www.mapmyindia.com/api/img/icons/stack-overflow.png"/> ](https://stackoverflow.com/questions/tagged/mappls-api)[![](https://www.mapmyindia.com/api/img/icons/blog.png)](https://about.mappls.com/blog/)[![](https://www.mapmyindia.com/api/img/icons/gethub.png)](https://github.com/Mappls-api)[<img src="https://mmi-api-team.s3.ap-south-1.amazonaws.com/API-Team/npm-logo.one-third%5B1%5D.png" height="40"/> </p>](https://www.npmjs.com/org/mapmyindia) 



[<p align="center"> <img src="https://www.mapmyindia.com/june-newsletter/icon4.png"/> ](https://www.facebook.com/Mapplsofficial)[![](https://www.mapmyindia.com/june-newsletter/icon2.png)](https://twitter.com/mappls)[![](https://www.mapmyindia.com/newsletter/2017/aug/llinkedin.png)](https://www.linkedin.com/company/mappls/)[![](https://www.mapmyindia.com/june-newsletter/icon3.png)](https://www.youtube.com/channel/UCAWvWsh-dZLLeUU7_J9HiOA)




<div align="center">@ Copyright 2022 CE Info Systems Ltd. All Rights Reserved.</div>

<div align="center"> <a href="https://about.mappls.com/api/terms-&-conditions">Terms & Conditions</a> | <a href="https://about.mappls.com/about/privacy-policy">Privacy Policy</a> | <a href="https://about.mappls.com/pdf/mapmyIndia-sustainability-policy-healt-labour-rules-supplir-sustainability.pdf">Supplier Sustainability Policy</a> | <a href="https://about.mappls.com/pdf/Health-Safety-Management.pdf">Health & Safety Policy</a> | <a href="https://about.mappls.com/pdf/Environment-Sustainability-Policy-CSR-Report.pdf">Environmental Policy & CSR Report</a>

<div align="center">Customer Care: +91-9999333223</div>
