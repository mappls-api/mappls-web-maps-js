[<img src="https://about.mappls.com/images/mappls-b-logo.svg" height="60"/> </p>](https://www.mapmyindia.com/api)
# MapmyIndia Interactive Vector Maps JS SDK for Web !

You can get your api key to be used in this document here: [https://apis.mappls.com/console/](https://apis.mappls.com/console/)


## Info Windows Quick Reference

### Drawing Info Windows

### [InfoWindow Properties](#InfoWindow-Properties)

### *Required*

- **Map Object**
- **Position**

**Example:**

```js
    Var infowindow =new mappls.InfoWindow({
            map:map,
            position: {"lng":"77.64534","lat":"28.5454"},
        });
```

### *Optional*

- **Content:** It shows the popup content on the Info Window.

```js
    {
		content: "MapmyIndia"
	}
```

- **Class:** It shows the custom class name on the Info Window.

```js
    {
		class: info_class
	}
```

- **Offset:** It sets the exact location of the Info Window.

```js
    {
		offset: [0,10]
	}
```

- **MaxWidth:** It sets the width in pixels of the Info Window.

```js
    {
		maxWidth: 200
	}
```

- **closeButton:** It shows the Close button on the Info Window. By default it is `true`

```js
    {
		closeButton: true
	}
```

**Example**

```js
	infoWindow_object =new Mappls.InfoWindow({
		position: {"lng":"77.64534","lat":"28.5454"},
		class: info_class ( optional ),
		map: map_object,
		content: "MapmyIndia",
		offset: [0,10],
		maxWidth: 200
	});
```

### [Remove InfoWindow](#Remove-InfoWindow)

```js
	Mappls.remove({map: map_object, layer: infoWindow_object);
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