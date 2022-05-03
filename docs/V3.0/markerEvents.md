![MapmyIndia APIs](https://about.mappls.com/images/mappls-b-logo.svg)
# MapmyIndia Interactive Vector Maps JS SDK for Web !

You can get your api key to be used in this document here: [https://apis.mappls.com/console/](https://apis.mappls.com/console/)

## Marker Events Quick Reference: 

### Listening to Marker Events via addListener()

- **click:** Fired when a pointing device (usually a mouse) is pressed on the marker.

```js
        marker.addListener('click', function () { console.log('click');}); 
```

- **cursor_changed:** Fired when a pointing device (usually a mouse) is pressed and released at the same point on the marker.

```js
        marker.addListener('cursor_changed', function () { console.log('cursor_changed');});
```

- **dblclick:** Fired when a pointing device (usually a mouse) is clicked twice at the same point on the marker.

```js
        marker.addListener('dblclick', function () { console.log('dblclick');});
```

- **drag:** Fired repeatedly during a "drag to pan" interaction.

```js
        marker.addListener('drag', function () { console.log('drag');});
```

- **dragstart:** Fired when a "drag to pan" interaction starts.

```js
        marker.addListener('dragstart', function () { console.log('dragstart');});
```

- **dragend:** Fired when a "drag to pan" interaction ends.

```js
        marker.addListener('dragend', function () { console.log('dragend');});
```

- **draggable_changed:** This event is fired when the marker's draggable property changes.

```js
        marker.addListener('draggable_changed', function () { console.log('draggable_changed');});
```

- **mousedown:** This event is fired for a mousedown on the marker.

```js
        marker.addListener('mousedown', function () { console.log('mousedown');});
```

- **mouseout:** This event is fired when the mouse leaves the area of the marker icon..

```js
        marker.addListener('mouseout', function () { console.log('mouseout');});
```

- **mouseover:** This event is fired when the mouse enters the area of the marker icon.

```js
        marker.addListener('mouseover', function () { console.log('mouseover');});
```

- **mouseup:** This event is fired for a mouseup on the marker.

```js
        marker.addListener('mouseup', function () { console.log('mouseup');});
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