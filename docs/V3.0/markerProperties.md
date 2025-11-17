[<img src="https://about.mappls.com/images/mappls-b-logo.svg" height="60"/> </p>](https://about.mappls.com/api)
[< Back to Table of Contents](../../README.md)
# MapmyIndia Interactive Vector Maps JS SDK for Web !

## Marker Properties Quick Reference:

For access, you can get your api key from [Mappls Console](https://auth.mappls.com/console)


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
