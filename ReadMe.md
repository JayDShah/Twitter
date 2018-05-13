---
title: Get Twitter Trends By Place
weight: 1
---

# Twitter Trends By Place
This activity allows get trending HashTags given a placeId, PlaceId here is WOEID(Where On Earth ID), you may get  WOEID from http://woeid.rosselliot.co.nz/lookup.
This activity is developed by Team AllStars.
## Installation
### Flogo CLI
```bash
flogo install github.com/adireddevil/twittertrendsbyplace
```

### Third-party libraries used
- #### package anaconda - "github.com/ChimeraCoder/anaconda":
	Anaconda is a simple, transparent Go package for accessing version 1.1 of the Twitter API.Successful API queries return native Go structs that can be used immediately, with no need for type assertions
## Schema
Inputs and Outputs:

```json
 "inputs":[
    {
		"name": "consumerKey",
		"type": "string",
    "required": true
	},
	{
		"name": "consumerSecret",
		"type": "string",
      "required": true

	},
	{
		"name": "accessToken",
		"type": "string",
      "required": true

	},
	{
		"name": "accessTokenSecret",
		"type": "string",
      "required": true

	},
	{
		"name": "placeId",
		"type": "int",
    "required": true

	}

  ],
  "outputs": [
    {
      "name": "statusCode",
      "type": "string"
    },
    {
      "name": "message",
      "type": "any"
    }
  ]
```
## Settings
| Setting     | Required | Description |
|:------------|:---------|:------------|
| consumerKey | True     | The consumerKey of your Twitter account |         
| consumerSecret   | True    | The consumerSecret of your Twitter account|
| accessToken       | True    | The accessToken of your Twitter account |
| accessTokenSecret   | True    | The accessTokenSecret of your Twitter account|
| placeId   | True    | Provide a valid WOEID to get the trending HashTags for the place,Global information is available by using 1 as the WOEID . |

Note: You may use below URL to generate your Twitter tokens: https://www.slickremix.com/docs/how-to-get-api-keys-and-tokens-for-twitter/
## Examples
Please refer activity_test.go 


## Response Codes
### TrendsByPlace
| ResponseCode     | Type | Description |
|:------------|:---------|:------------|
|200 |OK| The request operation was successful.|
|101 |INVALID INPUT| Consumer Key field is blank.|
|102 |INVALID INPUT| Consumer Secret field is blank.|
|103 |INVALID INPUT| Access Token field is blank.|
|104 |INVALID INPUT| Access Token Secret field is blank.|
|105 |INVALID INPUT| PlaceId is blank.|

Refer : https://developer.twitter.com/en/docs/basics/response-codes for additional Response codes
