![MapmyIndia APIs](https://about.mappls.com/images/mappls-b-logo.svg)
# MapmyIndia Interactive Vector Maps JS SDK for Web !

You can get your api key to be used in this document here: [https://apis.mappls.com/console/](https://apis.mappls.com/console/)


## Raster Source Overlay - To add 3rd Party Raster tile Sources

### Overlaying a Raster Source on map


Method Name :  **`addTile({tiles:tileUrl})`**

```js
var myTile=mappls.addTiles({
	map:map,
	tiles:[
		'https://apis.mappls.com/advancedmaps/v1/<key>/bhuvan_imagery/{z}/{x}/{y}.png'
		]
});
```

### Remove Raster Source

```js
mappls.remove({map:map_object,layer:rastersource_object});
```


For any queries and support, please contact: 

![Email](https://cdn.mapmyindia.com/mappls_web/maps_widget_v2/images/mappls.svg) 

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


> © Copyright 2022 CE Info Systems  Ltd. All Rights Reserved. 