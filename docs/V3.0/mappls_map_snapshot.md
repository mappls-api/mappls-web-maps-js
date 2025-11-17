[<img src="https://about.mappls.com/images/mappls-b-logo.svg" height="60"/> </p>](https://about.mappls.com/api)

# Mappls MapSnapshot

## Introduction

The mappls mapSnapshot  allows you to capture an image of the current map. The snapshot can includes watermarks of Mappls or MapmyIndia depending on the snapshot size, and can be downloaded directly as an image. This functionality is typically useful for generating static map images or sharing a fixed view of the map in your application.

## Document Version History

| Version | Last Updated  | Author                                                        |Remarks
| ------- | ------------- | ------------------------------------------------------------- |-------------- |
| 1.0  | 7 Dec 2024 | MapmyIndia API Team ([PK](https://github.com/prabhjot729)) | Initial Commit



### Getting Started

#### Steps for Using mappls.mapSnapshot
- **Load the Map SDK**: First, you need to load the Map SDK script in your HTML document. This is necessary for accessing the map and its associated methods.
```js 
<script src="https://sdk.mappls.com/map/sdk/web?v=3.0&access_token=<Static Key>&layer=vector&callback=initMap1&mapsnapshot" defer async></script>
```
- The callback parameter (initMap1 in this case) is the function that will be triggered once the map SDK is successfully loaded.
    - The layer parameter specifies the map layer. Here, it's set to a vector.
    - The v=3.0 specifies the version of the Map SDK.
    - The &mapsnapshot specifies that you capture an image of the current map.

  
### **Initialize the Map with mapSnapshot**
After loading the Map SDK, initialize your map object in the initMap1 function. This will create a map instance that you can later use to capture the snapshot.

#### Code Snippet:
```js
function initMap1() {
    const map = new mappls.Map('map-container', {
        center: [27.634320502688186, 77.21964825705418], // Center coordinates
        zoom: 10 
    });
    
    // Now you can call mapSnapshot function after initializing the map
    captureSnapshot(map);
}

//Capture the Snapshot: 
//To capture the snapshot, call the mappls.mapSnapshot method. Pass the map instance and configuration options like imageWidth, imageHeight, etc. 


function captureSnapshot(map) {
    mappls.mapSnapshot({
        map: map,  // Required: Your map instance
        imageWidth: 150, // Optional: Width of the image (default 200)
        imageHeight: 150, // Optional: Height of the image (default 200)
        Optional: Specify a custom image type (e.g., 'jpeg', default is 'png')
        imageType: 'jpeg', 
        imagePlaceId: 'imagePlaceId' // Optional: ID of an element to show the image in
	   centerCoordinate:[27.634320502688186, 77.21964825705418], // optional
    }, function(imageUrl) {
        // Callback function that gets triggered once the snapshot is created
        console.log('Snapshot created with watermark!',imageUrl.data);
        // You can use imageUrl.data to display or save the image
    });
}

```

### Explanation of Parameters:
- **map**: Required – The map instance that you want to capture.
- **imageWidth**: Optional – The width of the generated image in pixels (default: 200).
- **imageHeight**: Optional – The height of the generated image in pixels (default: 200).
- **imageType**: Optional – The type of image to be generated. You can specify 'jpeg' or 'png'. If not provided, the default is 'png'.
- **centerCoordinate**: Optional – The center coordinate of the map, used to specify a custom center point before capturing the snapshot.
- **imagePlaceId**: Optional – The ID of an HTML element where the generated snapshot image will be inserted. If this is provided, the image will be displayed in the element specified by this ID.

### Callback Function

The second parameter passed to mappls.mapSnapshot is a callback function. This function is called once the snapshot is successfully created. The function receives an imageUrl object, which contains the data field where the URL to the snapshot image is stored.

```js
function(imageUrl) {
    // Handle the generated snapshot image URL
    console.log(imageUrl.data);  // Logs the URL of the generated image
}

```


## Complete Sample Implementation

```js
Example of Full Implementation:

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Map Snapshot Example</title>
    <script src="https://sdk.mappls.com/map/sdk/web?v=3.0&access_token=<Static Key>&layer=vector&callback=initMap1&mapsnapshot" defer async></script>
</head>
<body>
    <div id="map-container" style="height: 500px; width: 100%"></div>
    <div id="imagePlaceId" style="height: 100px; width: 100px; clear:both;"></div>
    <script>
        function initMap1() {
            const map = new mappls.Map('map-container', {
                center: [27.634320502688186, 77.21964825705418],
                zoom: 10
            });
		setTimeout(() => { 
// Call the function to capture the snapshot
            	captureSnapshot(map);
}, 1000);
        }

        function captureSnapshot(map) {
            mappls.mapSnapshot({
                map: map,
                imageWidth: 150,
                imageHeight: 150,
centerCoordinate: [27.634320502688186, 77.21964825705418], 
                imagePlaceId: 'imagePlaceId'
            }, function(imageUrl) {
                console.log('Snapshot created with watermark!', imageUrl.data);
                // You can use the imageUrl.data to display or download the image
            });
        }
    </script>
</body>
</html>

```














<br><br><br>

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




<div align="center">@ Copyright 2024 CE Info Systems Ltd. All Rights Reserved.</div>

<div align="center"> <a href="https://about.mappls.com/api/terms-&-conditions">Terms & Conditions</a> | <a href="https://about.mappls.com/about/privacy-policy">Privacy Policy</a> | <a href="https://about.mappls.com/pdf/mapmyIndia-sustainability-policy-healt-labour-rules-supplir-sustainability.pdf">Supplier Sustainability Policy</a> | <a href="https://about.mappls.com/pdf/Health-Safety-Management.pdf">Health & Safety Policy</a> | <a href="https://about.mappls.com/pdf/Environment-Sustainability-Policy-CSR-Report.pdf">Environmental Policy & CSR Report</a>

<div align="center">Customer Care: +91-9999333223</div>

