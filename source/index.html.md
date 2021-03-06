---
title: Loceye Documentation

language_tabs: # must be one of https://git.io/vQNgJ
  - responses|requests
  

toc_footers:
  - <a href='http://www.loceye.io'>Documentation for Loceye.io</a>

includes:
  - errors

search: true
---

# Introduction

Hello there, you came here cause you are or you want to be a part of <strong>Loceye</strong> family.

We strive to understand where an everyday user is watching on his/her screen. Mobile or Web.

This API documentation page was created to help you move faster and help us build more powerful with no confusions and bottlenecks Web Applications.

# Survey Page

> The rersponse for the Get request:

```responses

If the SurveyID is valid then a proper webpage should render and
an Ajax POST request should be done.

```

> The first AJAX request.

```responses
Request Format:
{"x":"<Width of screen>",
     "y":"<Height of screen>"}

Response Format :

{"error":"<Error Code>","uuid":"<UUID4 code>","duration":<Duration in seconds>}

```

When landing to the survey url with the format `https://www.loceye.io/survey/<SurveyID>` a GET request is done.






# Experiment Page

## Request Link



> process "start"  Response:

```json
  {
    "error": <Error Code>,
    "imgURL": <URL of the survey Image to display>
  }
  " Note: If error code is 1 then no URL will be presented at the response. ""
```
> process "calib"  Request:

```json
  {
    "process":"calib",
    "x":<position of the calibration point in X axis>,
    "y":<position of the calibration point in Y axis>,
    "imgData":<imgBase64 formatted>
  }
```
> process "run"  Request:

```json
  
 {
    "process":"run",
    "imgData":<imgBase64 formatted>
  }

```
> process "finish"  Request:

```json
  
  {
    "process":"finish"
  }

```

`POST https://www.loceye.io/ajax/<UUID>`


### Query Parameters



Parameter |  Description
--------- |  -----------
process | Proper Values: start,calib, run, finish.
xPoint | At Calibration post gives the x coordinate of the point.
yPoint | At Calibration post gives the y coordinate of the point.
imgBase64 | The base64 encoded image of the user.




## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete


<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

