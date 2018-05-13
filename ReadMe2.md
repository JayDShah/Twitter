---
title: Get User TimeLine
weight: 1
---

# Twitter Get User Timeline
This activity allows fetch your User timeline.
This activity is developed by Team AllStars.
## Installation
### Flogo CLI
```bash
flogo install github.com/adireddevil/twittergetusertimeline
```

### Third-party libraries used
- #### package anaconda - "github.com/ChimeraCoder/anaconda":
	Anaconda is a simple, transparent Go package for accessing version 1.1 of the Twitter API. Successful API queries return native Go structs that can be used immediately, with no need for type assertions
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
		"name": "sinceId",
		"type": "int",
    "required": false

	},
    {
      "name": "pageCount",
      "type": "int",
      "required": false

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
| sinceId   | False    | Returns results with an ID greater than (that is, more recent than) the specified ID. There are limits to the number of Tweets that can be accessed through the API. If the limit of Tweets has occured since the since_id, the since_id will be forced to the oldest ID available.|
| pageCount   | False    | Specifies the number of Tweets to try and retrieve, up to a maximum of 200 per distinct request. The value of count is best thought of as a limit to the number of Tweets to return because suspended or deleted content is removed after the count has been applied. We include retweets in the count, even if include_rts is not supplied.|
Note: You may use below URL to generate your Twitter tokens: https://www.slickremix.com/docs/how-to-get-api-keys-and-tokens-for-twitter/
## Examples
Please refer activity_test.go 


## Response Codes
### UserTimeline
| ResponseCode     | Type | Description |
|:------------|:---------|:------------|
|200 |OK| The request operation was successful.|
|101 |INVALID INPUT| Consumer Key field is blank.|
|102 |INVALID INPUT| Consumer Secret field is blank.|
|103 |INVALID INPUT| Access Token field is blank.|
|104 |INVALID INPUT| Access Token Secret field is blank.|

Refer : https://developer.twitter.com/en/docs/basics/response-codes for additional Response codes
