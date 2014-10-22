---
title: "Interaction"
author: adron-hall
date: 2014-10-01
template: article.jade
---

`POST https://api.deconstructed.io/interaction`
	
To use this end point submit a POST with the API key, the content type and accept headers. This end point is the primary end point to have data from any type of device or system application stored and converged via consociation in the Deconstructed system. A sample cURL request is shown below:


In any case, upon the write of the data the key is then returned via the response as a simple JSON pair as shown:

`{"key":"F0DB4493-13A1-4EA6-840A-719FEA3F1C13"}`

***Currently it is disabled for testing***, but in the future, if only the "value" part of the key value pair is sent in, the key will actually be generated. This is why the Deconstructed API will return the key after the interaction is sent and written into the system.


```shell
curl -X POST -H "Accept: application/json" -H "Content-Type: application/json" -H "apikey: f996f23b-fake-47ef-a4e8-a110f99c6791" -d '{"key":"F0DB4493-13A1-4EA6-840A-719FEA3F1C13","value":{"knownids":[{"email":"the@future.com"},{"homeaddress":"unique/long/lat"}],"anyOtherJSONdata":"goes here...","andMoreJSON":"goes here.","event": "anImportantEvent"}}' http://apitest.deconstructed.io/interaction
```
