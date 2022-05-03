![MapmyIndia APIs](https://about.mappls.com/images/mappls-b-logo.svg)

# [Set Mappls style](#Set-MapplsMaps-style)

Mappls offers a range of preset styles to rendering the map. The user has to retrieve a list of styles for a specific account. 
The listing api would help in rendering specific style as well as facilitate the switching of style themes. 

From the below reference code it would become quite clear that user has to specify style names and not URLs to use them. 

You can get your api key to be used in this document here: [https://apis.mappls.com/console/](https://apis.mappls.com/console/)

A default style is set for all account users to start with. 
To know more about available styles, kindly contact apisupport@mapmyindia.com

**This feature is available from version v2.0**

## [List of Available Styles](#list-of-available-styles)

To get the list of available styles :

**Method:**

mappls.getStyles();

Click for Live Demo: https://www.mapmyindia.com/api/advanced-maps/WebSDK-LiveDemo/map_style

Mappls Map Styles contains below parameters:

 1. `description(String)`: Description of the style
 2. `displayName(string)`: Generic Name of style mostly used in Mappls content.
 3. `imageUrl(String)`: Preview Image of style
 4. `name(String)`: Name of style used to change the style.

## [Set Mappls Styles](#Set-Mappls-Styles)


To set the Mappls style refer the code below :

**Method:**

mappls.setStyles();

For eg:

```
mappls.setStyle(‘grey-day’);
```

That's all!

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
