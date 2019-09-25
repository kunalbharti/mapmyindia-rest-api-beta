[![N|Solid](https://mmi-api-team.s3.ap-south-1.amazonaws.com/mappls/mappls.png=160x80)](https://www.mapmyindia.com/api/)

# Mappls Reverse Geocoding API

**Easy To Integrate Maps & Location APIs & SDKs For Web & Mobile Applications**

Powered with world's most comprehensive and robust mapping functionalities.

**Available Worldwide**

You can get your api key to be used in this document here: [https://www.mapmyindia.com/api/signup](https://www.mapmyindia.com/api/signup)

## Introduction
Reverse Geocoding is a process to give the closest matching address to a provided geographical coordinates (latitude/longitude). Mappls reverse geocoding API provides real addresses along with nearest popular landmark for any such geo-positions on the map.

## Security Type
This APIs follow OAuth2 based security. **To know more on how to create your authorization tokens, please use our authorization token URL. More details available**  [here](https://www.mapmyindia.com/api/advanced-maps/doc/authentication-api.php)

## Request Headers

The API leverages OAuth 2.0 based security. Hence, the developer would need to send a request for access token using their client_id and client_secret to the OAuth API. Once validated from the OAuth API, the access_token and the token_type need to be sent as Authorization header with the value: “{token_type} {access_token}”.

-  `Authorization:  “token_type access_token”`.

## Input Method

GET

## Input URL

[https://apis.mappls.com/advancedmaps/v1/reverse?](https://apis.mappls.com/advancedmaps/v1/reverse?)

## Request Parameters

### Mandatory Parameters:
1.  **`lat`**:  The latitude of the location for which the address is required.
2.  **`lon`**: The longitude of the location for which the address is required.

## Response Parameters

1. `place_id`(integer): the unique Id of the location.
2. `licence`(string): the description of license information.
3. `lat`(double): the latitude for the location.
4. `lon`(double): the longitude for the location.
5. `display_name`(string): the complete address for the location. eg: 38, Richardson Street, Rochester, Strafford County, New Hampshire, 03867, USA.
6. `address` (object): 
	- `category`(string): The name of the category of the result. e.g. of category - house_number / building / address / cafe / car / car_wash / castle / cinema / clothes / community_centre / convenience / courthouse / doctors / estate_agent / fast_food / fire_station / fuel / garden / golf_course / hospital / hotel / library / mall / museum / nightclub / parking / pharmacy etc.
	- `road` / `pedestrian`(string): The street or road of the location
	- `neighbourhood` / `suburb` / `locality`(string): The locality name of the location, if available
	- `town`(string): The town name of the location, if available
	- `hamlet` / `village`(string): The hamlet/village name of the location, if available
	- `city`(string): The city name of the location, if available
	- `city_district`(string): The city_district of the location, if available
	- `county`(string): The county name of the location, if available
	- `state_district`(string): The state_district name of the location, if available
	- `state`(string): The state name of the location
	- `postcode`(string): The Zipcode of the location
	- `country`(string): The country of the location
	- `country_code`(string): The country code of the location
7. `boundingbox`(string): Array of bounding coordinates of the location.

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
https://apis.mappls.com/advancedmaps/v1/reverse?lat=30.274665&lon=-97.740553
```

## Sample Response

```json
{
	"place_id": 87528310,
	"licence": "Data © OpenStreetMap contributors, ODbL 1.0. https://osm.org/copyright",
	"lat": "30.27468705",
	"lon": "-97.7404049121679",
	"display_name": "Texas State Capitol, 112, East 11th Street, Dirty Sixth, Austin, Travis County, Texas, 78701, USA",
	"address": {
	"address29": "Texas State Capitol",
	"house_number": "112",
	"road": "East 11th Street",
	"neighbourhood": "Dirty Sixth",
	"city": "Austin",
	"county": "Travis County",
	"state": "Texas",
	"postcode": "78701",
	"country": "USA",
	"country_code": "us"
	},
	"boundingbox": [
		"30.2742361",
		"30.2751226",
		"-97.7411986",
		"-97.7394981"
	]
}
```


For any queries and support, please contact: 

[![N|Solid](https://mmi-api-team.s3.ap-south-1.amazonaws.com/mappls/mappls.png =150x100)](https://www.mapmyindia.com/api/)
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
