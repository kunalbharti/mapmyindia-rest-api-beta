<a href="https://www.mapmyindia.com/api/"><img src="https://mmi-api-team.s3.ap-south-1.amazonaws.com/mappls/mappls.png" width="160" height="80" /></a>

# Mappls Search API

**Easy To Integrate Maps & Location APIs & SDKs For Web & Mobile Applications**

Powered with world's most comprehensive and robust mapping functionalities.

**Available Worldwide**

You can get your api key to be used in this document here: [https://www.mapmyindia.com/api/signup](https://www.mapmyindia.com/api/signup)

## Introduction
Search API is a service that aims to provide information about a list of places on the basis of a text string entered by the user. It uses the location information that is provided along with the query to try to understand the request.


## Security Type
This APIs follow OAuth2 based security. **To know more on how to create your authorization tokens, please use our authorization token URL. More details available**  [here](https://www.mapmyindia.com/api/advanced-maps/doc/authentication-api.php)

## Request Headers

The API leverages OAuth 2.0 based security. Hence, the developer would need to send a request for access token using their client_id and client_secret to the OAuth API. Once validated from the OAuth API, the access_token and the token_type need to be sent as Authorization header with the value: “{token_type} {access_token}”.

-  `Authorization:  “token_type access_token”`.

## Input Method
GET

## Input URL

[https://apis.mappls.com/advancedmaps/v1/search?q=](https://apis.mappls.com/advancedmaps/v1/search?q=)

## Request Parameters

### Mandatory Parameters:
1.  **`q`** (string): query or address to be searched e.g. Montgomery Street, Jersey City; 111, Manhattan; etc.

## Response Parameters

1.  `place_id`(integer): The unique id of the location.
2. `license`(string): The description of license information.
3. `boundingbox`(string): Array of bounding coordinates of the location.
4. `lat`(double): Latitude of the location.
5. `lon`(double): Longitude of the location.
6. `display_name`(string): : The complete address for the location. eg: 38, Richardson Street, Rochester, Strafford County, New Hampshire, 03867, USA.
7. `class`(string): Type of the location. (e.g. amenity, building, place, boundary, highway, landuse, etc).
8. `Type`(string): Subtype of the location. (e.g. residential, restaurant, school, etc).
9. `Importance`(double): The confidence score/ rank for the result. It ranges between 1 and 0. Multiple results are sorted with descending Importance.

## Response Type

JSON

## Response Codes {as HTTP response code}

### Success:

1. `200`: To denote a successful API call. 
2. `204`: To denote the API was a success but no results we’re found.

### Client-Side Issues:
1. `400`: Bad Request, User made an error while creating a valid request. 
2. `401`: Unauthorized, Developer’s key is not allowed to send a request with restricted parameters. 
3. `403`: Forbidden, Developer’s key has hit its daily/hourly limit

### Server-Side Issues:
1. `500`: Internal Server Error, the request caused an error in our systems. 
2. `503`: Service Unavailable, during our maintenance break or server downtime.


## Sample Input
```html
https://apis.mappls.com/advancedmaps/v1/search?q=eiffel tower
```

## Sample Response

```json
[
	{
		"place_id": 28111555,
		"licence": "Data © OpenStreetMap contributors, ODbL 1.0. https://osm.org/copyright",
		"boundingbox": [
			"51.33355",
			"51.33365",
			"-116.23505",
			"-116.23495"
		],
		"lat": "51.3336",
		"lon": "-116.235",
		"display_name": "Eiffel Tower, Alberta, Canada",
		"class": "natural",
		"type": "peak",
		"importance": 0.5,
	},
	{
		"place_id": 67395914,
		"licence": "Data © OpenStreetMap contributors, ODbL 1.0. https://osm.org/copyright",
		"boundingbox": [
			"36.2869263",
			"36.2870263",
			"-88.301576",
			"-88.301476"
		],
		"lat": "36.2869763",
		"lon": "-88.301526",
		"display_name": "Eiffel Tower, Maurice Fields Drive, Paris, Henry County, Tennessee, 38242, USA",
		"class": "tourism",
		"type": "attraction",
		"importance": 0.201,
	}
]
```


For any queries and support, please contact: 

<a href="https://www.mapmyindia.com/api/"><img src="https://mmi-api-team.s3.ap-south-1.amazonaws.com/mappls/mappls.png" width="150" height="100" /></a>
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


> © Copyright 2019. CE Info Systems Pvt. Ltd. All Rights Reserved. |  
> 'Mappls' & 'MapmyIndia' are registered trademarks of CE Info Systems Pvt. Ltd.
> [Terms & Conditions](http://www.mapmyindia.com/api/terms-&-conditions)
> © Copyright 2019. OpenStreetMap contributors, ODbL 1.0. https://osm.org/copyright |

