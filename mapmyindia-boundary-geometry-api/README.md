![MapmyIndia APIs](https://www.mapmyindia.com/api/img/mapmyindia-api.png)

# MapmyIndia Boundary Geonmetry API - beta

**Easy To Integrate Maps & Location APIs & SDKs For Web & Mobile Applications**

Powered with India's most comprehensive and robust mapping functionalities.
**Now Available**  for Srilanka, Nepal, Bhutan and Bangladesh

You can get your api key to be used in this document here: [https://www.mapmyindia.com/api/signup](https://www.mapmyindia.com/api/signup)

## Disclaimer
The document contains sensitive information on parameters and responses that can be accessed only by MapmyIndia.
Redistribution without permissions is prohibited.
It is mandatory to take permissions from the author before sharing with any personnel outside MapmyIndia.

## Document Version History

| Version | Last Updated | Author |
| ---- | ---- | ---- |
| 0.0.1 | 16 May 2019 | MapmyIndia API Team ([KB](https://github.com/kunalbharti)) |

## API Version History

| Version | Last Updated | Author | Revised Sections |
| ---- | ---- | ---- | ---- |
| 200.16 | 2019-04-11 | MapmyIndia API Team ([VP](https://github.com/Vishwajit1986)) | Initial release |


## Introduction

### Boundary Geometry

A critical feature of any geographical based analytical operation is to be group data based on geographical areas and then applying big data derived  attributions to it. To accomplish this, the GIS tools supporting such analytics must be capable of visualizing the areas on the map. This API provides the basic functionality of querying the MapmyIndia Maps DB about the boundary geometry data of an area. The API takes in the unique eLoc of the administrative area and returns the multi-polygonal GeoJSON object defining the boundary of the area.
Supported region (countries) are India, Sri Lanka, Nepal, Bangladesh & Bhutan. 

## Security Type
- License key based authentication
- IP/domain based whitelisting


## Input Method
GET

## The API URL

```html
http://apis.mapmyindia.com/advancedmaps/v1/<your own REST API key>/getGeometry?place_ids=<eLoc of the area>&boundry=<boolean 0 or 1>
```

### Example URL: 
```html
http://apis.mapmyindia.com/advancedmaps/v1/assigned_REST_license_key/getGeometry?place_ids=4HUDNT&boundry=1
```
where: 
- "4HUDNT" is the chosen eLoc.


## Request Parameters

### Mandatory Parameters

1.  **`lic_key`**: Allocated REST API license key. (part of URL).
2.  **`place_ids`**(string): The unique place ID that is also called the eLoc of the area whose boundary or centre point needs to be determined. eLoc is provided in response by almost all search based APIs of MapmyIndia.


### Optional Parameters

1. *`boundry`*(boolean 0 or 1): A boolean value used to denote: 
	- `0`: Only centroid of the area's polygon is required as output.
	- `1`: GeoJSON geometry as well as centroid of the area is required as output.

## Response Parameters

1.	`responseCode`(integer): See the service dependent and general status codes.
2.	`version`(string): API’s version information.
3.	`results`(array of objects): array of results, each consisting of the following parameters:
	- `place_id`(string): The eLoc of the area whose centroid or boundary geometry details are requested.
	- `boundry`: The boundary geometry of the area in geoJSON format.
	- `c_point`: The centroid of the area in geoJSON format.

## Response Type
JSON: response will served as JSON


## Response Codes {as HTTP response code}

- 200: To denote a successful API call.
- 201: To denote that no content for this request is available.
- 204: DB Connection error.
- 400: Bad Request, User made an error while creating a valid request.
- 401: Unauthorized, Developer’s key is not allowed to send a request.
- 403: Forbidden, Developer’s key has hit its daily/hourly limit or IP or domain not white-listed.
- 404: HTTP not found
- 412: Precondition Failed, i.e. Mandatory parameter is missing
- 500: Internal Server Error, the request caused an error in our systems.
- 503: Service Unavailable, during our maintenance break or server down-times.

## Sample Input
```html
http://apis.mapmyindia.com/advancedmaps/v1/<assinged_REST_license_key>/getGeometry?place_ids=4HUDNT&boundry=1
```

## Sample Response

```json
{
    "responseCode": 200,
    "version": "200.16",
    "results": [
        {
            "place_id": "4HUDNT",
            "boundry": "{\"type\":\"MultiPolygon\",\"coordinates\":[[[[73.776855,20.001019],[73.776878,20.001189],[73.777054,20.001945],[73.77717,20.002533],[73.77725,20.00295],[73.777284,20.003093],[73.777362,20.003082],[73.777664,20.00304],[73.777819,20.003701],[73.777989,20.00443],[73.778149,20.00594],[73.778349,20.005947],[73.778347,20.005679],[73.778349,20.005411],[73.77835,20.005173],[73.778865,20.005204],[73.779306,20.005199],[73.779309,20.005395],[73.779315,20.005775],[73.779296,20.005905],[73.779291,20.00598],[73.779816,20.005999],[73.780416,20.006001],[73.781082,20.006018],[73.781082,20.005998],[73.781081,20.005973],[73.781066,20.005367],[73.781062,20.005182],[73.781058,20.004969],[73.781049,20.00458],[73.781039,20.004105],[73.781036,20.003896],[73.781033,20.003701],[73.781025,20.003235],[73.781013,20.003089],[73.780961,20.002992],[73.783314,20.002935],[73.782834,20.001589],[73.782749,20.001352],[73.782529,20.000741],[73.782441,20.000715],[73.782365,20.000704],[73.782275,20.000699],[73.782118,20.000694],[73.781351,20.000723],[73.780863,20.000754],[73.780434,20.000781],[73.779748,20.000805],[73.778327,20.000852],[73.777855,20.000867],[73.777062,20.000948],[73.776855,20.001019]]]]}",
            "c_point": "{\"type\":\"Point\",\"coordinates\":[73.7798417141965,20.0028819879532]}"
        }
    ]
}
```


## Live Demo

The API's can be visualized quite simply by rendering the GeoJSON data as an overlays on map.
To see a demo of the same on MapmyIndia Interactive Maps, 
[Click Here](https://jsfiddle.net/kunalbharti/nv1zqru2/)

### Important Note: 
- Currently, the API provides boundary data for the following administrative types aread within MapmyIndia Maps DB: 
	- `Locality` (e.g. "Police Staff Colony, Nashik" with eLoc 4HUDNT)
	- `SubLocality` (e.g. "Old CBS Pass Kendra, Police Staff Colony, Nashik" with eLoc O59U62)
	- `SubSubLocality` (e.g. "Government Housing Society, Old CBS Pass Kendra, Police Staff Colony, Nashik" with eLoc LXMZJF)

For any queries and support, please contact: 

![Email](https://www.google.com/a/cpanel/mapmyindia.co.in/images/logo.gif?service=google_gsuite) 
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


> © Copyright 2019. CE Info Systems Pvt. Ltd. All Rights Reserved. | [Terms & Conditions](http://www.mapmyindia.com/api/terms-&-conditions)
>  Written with [StackEdit](https://stackedit.io/) by MapmyIndia.