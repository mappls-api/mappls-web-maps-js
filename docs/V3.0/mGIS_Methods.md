[<img src="https://about.mappls.com/images/mappls-b-logo.svg" height="60"/> </p>](https://www.mapmyindia.com/api)

# mGIS Module for Mappls SDK

## Introduction 

mGIS offers a complete set of tools for mapping, data analysis, and visualization, empowering you to gain deeper insights from your location data. Leverage the power of geospatial AI to uncover hidden patterns, predict trends, and make smarter decisions.

## Document Version History

| Version | Remarks | Author |
| ---- | ---- | ---- |
| 1.0 | Document Update |SDK Product Team ([PK](https://github.com/prabhjot729/))|



## Getting Access

Before using the methods in the your solution, please ensure that the related access is enabled in the [Mappls Console](https://apis.mappls.com/console/).

1. Copy and paste the generated `access token` from your API [keys](https://apis.mappls.com/console/) available in the dashboard in the sample code for interactive map development.
    - This APIs follow OAuth2 based security.
    - `Access Token` can be generated using Token Generation API.
    - To know more on how to create your access tokens, please use our authorization API URL. More details available [here](https://about.mappls.com/api/advanced-maps/doc/authentication-api.php)
    - The `access token` is a valid by default for 24 hours from the time of generation. This can be configured by you in the API console.
2. The sample codes are provided on our domain to help you understand the very basic functionality of Mappls Tracking Plugin. [Javascript Code Example - WIP]() & [Working NPM Code - WIP]()

  


## Implementation

### Step 1: Initialize mGIS SDK in the script tag
```js
 <script src="https://maps-preprod.mapmyindia.in/mgis_sdk/?v=1.0"></script>
```

### Step 2 : Add map under div container in your project

 ```js
   <div id="map"></div>
 ```

### Step 3 : Initialize Map 

```js
var trackingCallBackData;
map = new mappls.Map('map', {
    center: [28.62988695137534, 77.4224575062193],
    zoom: 12
});
```

## List Of Methods :

### getLayerList()

Fetches the list of datasets on your mGIS account.

### Parameters

- `access_token (required)`: The Mappls API access token.

#### Example Usage:

```js
new mappls.getLayerList({
    access_token: '5d581ca4-53af-43d1-9a1c-979b2bc78376',
}, function(data) {
    console.log(data);
});
```

### getMap()

Visualize your dataset on map using WMS layer. mGIS methods will render your data of all feature classes like - point,polyline and polygon.

### Parameters
- `map (required)`: The map instance to which the dataset layer should be added.
- `datasetName (required)`: The name of the dataset. Example: 'ward_demo_census'.
- `access_token (required)`: The API access token.
- `bbox (optional)`: Bounding box of the dataset in EPSG:3857 projection.
- `srs (optional)`: Spatial reference system, default is 'EPSG:3857'.
- `service (optional)`: Type of service (e.g., 'WMS').
- `version (optional)`: Version of the service (e.g., '1.1.1').
- `format (optional)`: Image format for the layer, default is 'image/png'.
- `transparent (optional)`: Whether the layer is transparent, default is true.
- `crossOrigin (optional)`: CORS configuration, default is 'anonymous'.
- `zIndex (optional)`: Z-index value for layer stacking, default is 10.
- `styles (optional)`: Style to be applied to the dataset.

#### Example Usage
```js
new mappls.getMap({
    map: map,
    id:'abc', /* for set to top */
    datasetName: 'ward_demo_census',
    access_token: '5d581ca4-53af-43d1-9a1c-979b2bc78376',
    service: 'WMS',
    version: '1.1.1',
    format: 'image/png',
    transparent: true,
    zIndex: 10,
}, function(data) {
    console.log(data);
});
```

## getFeatureInfo()
Fetch all the information and attributes of a single feature using mGIS's getFeatureInfo method.

### Parameters
- `map (required)`: The map instance where the event occurs.
- `datasetName (required)`: The name of the dataset.
- `x (required)`: The x-coordinate (pixel value) of the click event.
- `y (required)`: The y-coordinate (pixel value) of the click event.
- `access_token (required)`: The API access token.
- `style (optional)`: The style to apply to the feature info.


#### Example Usage
```js
map.addListener('click', function(e) {
    var point = map.project(e.lngLat);
    var params = {
        map: map,
        datasetName: 'ward_demo_census',
        x: parseInt(point.x),
        y: parseInt(point.y),
        access_token: '5d581ca4-53af-43d1-9a1c-979b2bc78376',
        style: 'city',
    };
    new mappls.getCatalogFeatureInfo(params, function(data) {
        console.log(data);
    });
});
```


## getLegendImage()
Fetch the Legend image of the data rendered on map.

### Parameters
- `map (required)` : The map instance where the legend will be shown.
- `datasetName (required)`: The name of the dataset.
- `styles (optional)`: The style applied to the dataset.
- `access_token (required)`: The API access token.
- `position (optional)`: Position of the legend on the map, e.g., 'top-left'.
- `draggable (optional)`: Whether the legend can be dragged, default is true.

#### Example Usage:

```js
new mappls.getLegendImage({
    map: map,
    datasetName: 'ward_demo_census',
    styles: 'ward_demo_census',
    position: 'top-left',
    draggable: true,
}, function(data) {
    console.log(data);
});
```


## getStyles() 
Fetch the applied style of the layer.

### Parameters
- `datasetName (required)`: The name of the dataset.
- `styleType (required)`: The style type for the dataset (e.g., 'ward_demo_census').
- `access_token (required)`: The API access token.

#### Example Usage:
```js

new mappls.getStyles({
    datasetName: 'ward_demo_census',
    styleType: 'ward_demo_census',
    access_token: '5d581ca4-53af-43d1-9a1c-979b2bc78376',
}, function(data) {
    console.log(data);
});
```

## setLayerStyle()

Apply style on the layer

### Parameters

- `datasetName (required)`: The name of the dataset.
- `styleType (required)`: this parameter is used to determine which type of style is being manipulated or created for the dataset. For example - (basic, icon_based, cluster, heat, category_based, bubble, graduated, heat_attr,d3_bubble, chart, rule_based)
- `access_token (required)`: The API access token.
- `style properties (optional)`:
  - `polygonfillcolor` : set hex color without '#' of the polygon/s. eg- '003049'.
  - `polygonfillopacity` : opacity of polygon/s ranging from 0-1
  - `polygonType`: It signifies what kind of fill should be used, can have the following values => simple, circle, hatchfill [default = simple]
  - `polygongraphicbordercolor` : Sets the color of graphic border if graphic is being used in the fill pattern [default = 000000]
  - `polygongraphicborderwidth`: This can be used to define the width of the border of graphic used [default = 1], in case of polygonType = "hatchfill" this param can be used to increase the width of the pattern used in hatchfill
  - `polygongraphicborderopacity`:This can be used to define the opacity of the border of graphic ranging from 0-1 [default = 1]
  - `polygonGraphicSize` :sets the size of graphic in pixels if it is being used in the fill pattern, for example in lineType circle, polygonGraphicSize can be used to set size of circle[default = 16]
  - `linestrokecolor`: Set hex color without '#' of the line(s). eg- '003049'.
  - `linestrokewidth`: Width of the line/s in pixels [linestrokewidth should be greater than zero and should be less than 13]
  - `linestrokeopacity`: Opacity of line/s ranging from 0-1
  - `lineType` :It signifies what kind of line should be used, can only have the following values => simple line, dashed line, dotted line, railroad, crossroad, xroad, vertline, slash, backslash [default = simple line]
  - `lineGraphicSize` : Sets the size of graphic in pixels if it is being used in the line pattern, for example in lineType dotted line, lineGraphicSize can be used to set size of circle or dots [default = 4]
  - `lineGraphicSpacing` : This can be used to define the space between the repeating pattern in line[default= 2]
  - `lineGraphicFillColor` : This can be used to set the color of the graphic that is being used as a pattern in line, not applicable in simple and dashed line [default = c8c9cc]
  - `pointfillcolor` : Set hex color without '#' of the point(s). eg- '003049'.
  - `pointfillopacity` : Opacity of point/s ranging from 0-1
  - `pointbordercolor` : Hex color without '#' for the border of point features [default: 000000]
  - `pointborderwidth` : Width of border in pixels for point features [default: 0] (therefore not visible by default) [pointborderwidth should be greater than zero and should be less than 7]
  - `pointborderopacity` : Opacity of border (ranging between 0-1) for point features [default: 1]
  - `pointsize` : Size of point/s in pixels [pointsize should be greater than 5 and less than 33]
  - `pointmarker` : The type of marker in default style for point features, can have the following values => [circle | square | triangle | star | cross | x] OR ttf://<FONT_NAME>#0x<SYMBOL_HEXCODE> Example => ttf://Webdings#0x68
  - `icon` : Url of the image file that needs to be used as icon [make sure the url points to a valid image]
  - `iconsize` : Size of icon is pixel. for example if 20 is used then icon will be of dimension 20 * 20 pixels [iconsize should be greater than 7 and less than 49]
  - `heatColors` : Have effect only when used in combination with parameter styleType = heat . It is the array of colors .This array of colors is used to create color gradient depicting density , where heatColors[0] is the starting color[0.01%](least dense) and heatColors[n-1] is the ending color[100%](most dense) where n is the number of colors in heatColors. For best visual gradient provide either 2 or 5 colors.
  - `heatOpacity` : Opacity of heatmap(density based) (ranging between 0-1) for point features [default: 0.6]
  - `clusterfillcolor` : Defines the color of cluster, it's value should be hexcode of color without hash symbol.
  - `clusterfillopacity` : Can be used to change the opacity of the clusters, it’s value ranges from 0 to 1 with the decimal precision of upto 1 digit [default -> 0.9]
  - `clusterlabelcolor` : Can be used to change the color label in clusters [default -> FFFFFF]
  - `showClusterLabel` : Can be used to toggle on or off label in cluster style [can have value true]
  - `clusterpointmarker` : Can be used to change marker used for clusters [can values like triangle, circle, cross, etc.]
  - `minZoom` : Zoomed in zoom level that is allowed [a good starting value would be 18, 19 upto 23] [default: 23] should be positive integer less than 24, minZoom should be greater than maxZoom
  - `maxZoom` : Zoomed out zoom level that is allowed [a good starting value should be 0,1, upto 22] [default: 0] should be positive integer less than 23, maxZoom should be less than minZoom.
  - `columnName` : Used in case, styleType = heat(weighted attribute). name of column on which weighted heatmap should created.
  - `radius` : Used in case, styleType = heat(weighted attribute).radius parameter, which controls the “spread” of the heatmap around each point
  - `unit` : Used in case, styleType = heat(weighted attribute).unit parameter, which controls the resolution at which the heatmap raster is computed.
  - `styleJSON` (object) :Used in case, styleType=category_based OR styleType=bubble OR styleType=heat_attr OR styleType=chart OR styleType=d3_bubble (contains information for creating/updating bubble style/category based style/heat[attribute based] style/chart style)
  - `label` (object) : Use this parameter only when user wants label to be added/edited



#### Example Usage
```js
new mappls.setStyle({
    datasetName: 'ward_demo_census',
    styleType: 'basic',
    access_token: '5d581ca4-53af-43d1-9a1c-979b2bc78376',
    polygonfillcolor: 'af0bff',
    lineGraphicFillColor: 'c8c9cc',
    linestrokecolor: '2ce622',
    maxZoom: 3,
}, function(data) {
    console.log(data);
});
```

## getBoundingBox()

Fetch Bounding box of a layer, that is rendered on the map.

### Parameters

- `access_token (required)`: The Mappls API access token.
- `datasetName (required)`: The name of the dataset.
- `query (optional)`: A query filter for specific features.
- `dataStoreName (optional)`: The data store name.
- `layerType (optional)`: The type of layer.
- `countryName (optional)`: Name of the country for bounding box constraints.
  
#### Example Usage
```js
new mappls.getBoundingBox({
    access_token: '5d581ca4-53af-43d1-9a1c-979b2bc78376',
    datasetName: 'ward_demo_census',
}, function(data) {
    console.log(data);
});
```

## getFeatureCentroid()

Fetch Centroid of a single feature of a layer. This method can be used to fetch feature centroid of both your dataset as well as of Mappls Catalog datasets (Administrative Layers)

### Parameters

- `access_token (required)`: The API access token.
- `datasetName (required)`: The name of the dataset.
- `featureID (required)`: The unique feature ID.
- `datastorename(optional)` : If centroid is fetched for catalog layera this parameter will be used with value `Admin`.
  
#### Example Usage
```js
new mappls.getFeatureCentroid({
    access_token: '5d581ca4-53af-43d1-9a1c-979b2bc78376',
    datasetName: 'ward_demo_census',
    featureID: 'ward_demo_census.1',
}, function(data) {
    console.log(data);
});
```

## getCatalogMap()

Visualize your Catalog dataset (Administrative Layers) on map. mGIS method `getCatalogMap()` will render your data from Mappls catalog.

### Parameters

- `map (required)`: The map instance to display the catalog map.
- `datasetName (required)`: The dataset name to be used (e.g., 'district').
- `dataStoreName (required)`: The data store name to query the catalog.
- `layers (optional)`: List of layers to be included.
- `layerType (optional)`: Type of layer (e.g., 'admin').
- `access_token (required)`: The API access token.

#### Example Usage:

```js
new mappls.getCatalogMap({
    map: map,
    id:'abc', /* for set to top */
    datasetName: 'district',
    dataStoreName: 'mmidatacatalog',
    layers: 'city',
    layerType: 'admin',
    access_token: '5d581ca4-53af-43d1-9a1c-979b2bc78376',
}, function(data) {
    console.log(data);
});
```

## getCatalogFeatureInfo() 

Fetch Centroid of a single feature the Catalog dataset (Administrative Layers)

### Parameters

- `map (required)`: The map instance where the event occurs.
- `datasetName (required)`: The name of the dataset.
- `dataStoreName (required)`: The name of the data store.
- `x (required)`: The x-coordinate (pixel value) of the click event.
- `y (required)`: The y-coordinate (pixel value) of the click event.
- `access_token (required)`: The API access token.
- `style (optional)`: The style to apply to the feature info.


#### Example Usage

```js
map.addListener('click', function(e) {
    var point = map.project(e.lngLat);
    var params = {
        map: map,
        datasetName: 'district',
        dataStoreName: 'mmidatacatalog',
        x: parseInt(point.x),
        y: parseInt(point.y),
        access_token: '5d581ca4-53af-43d1-9a1c-979b2bc78376',
        style: 'city',
    };
    new mappls.getCatalogFeatureInfo(params, function(data) {
        console.log(data);
    });
});
```

## getCatalogLegendImage()
Fetch the Legend image of the Mappls catalog data rendered on map.

### Parameters

- `map (required)`: The map instance where the legend will be added.
- `datasetName (required)`: The dataset name.
- `styles (required)`: The style to apply.
- `position (optional)`: The position of the legend, default is 'top-left'.
- `type (required)`: The type of layer ('admin' or other types).
- `draggable (optional)`: Whether the legend is draggable, default is false.
- `access_token (required)`: The API access token.

#### Example Usage
```js
new mappls.getCatalogLegendImage({
    map: map,
    datasetName: 'panchayat',
    styles: 'panchayat',
    position: 'top-left',
    type: 'admin',
    draggable: false,
}, function(data) {
    console.log(data);
});
```

## getRasterCatalogMap()
Visualize Raster dataset (Administrative Layers) on map. mGIS method `getRasterCatalogMap()` will render raster data from Mappls raster catalog.

### Parameters

`map (required)`: The map instance to which the raster catalog should be added.
`datasetName (required)`: The name of the dataset to be used. E.g., 'India_Night_Light_2021'.
`access_token (required)`: The access token associated with your Mappls API account.

#### Example Usage:
```js
new mappls.getRasterCatalogMap({
    map: map, 
    id:'abc', /* for set to top */
    datasetName: 'India_Night_Light_2021', 
    access_token: '5d581ca4-53af-43d1-9a1c-979b2bc78376',
}, function(data) {
    console.log(data);
});
```




<br>
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




<div align="center">@ Copyright 2025 CE Info Systems Ltd. All Rights Reserved.</div>

<div align="center"> <a href="https://about.mappls.com/api/terms-&-conditions">Terms & Conditions</a> | <a href="https://about.mappls.com/about/privacy-policy">Privacy Policy</a> | <a href="https://about.mappls.com/pdf/mapmyIndia-sustainability-policy-healt-labour-rules-supplir-sustainability.pdf">Supplier Sustainability Policy</a> | <a href="https://about.mappls.com/pdf/Health-Safety-Management.pdf">Health & Safety Policy</a> | <a href="https://about.mappls.com/pdf/Environment-Sustainability-Policy-CSR-Report.pdf">Environmental Policy & CSR Report</a>

<div align="center">Customer Care: +91-9999333223</div>
