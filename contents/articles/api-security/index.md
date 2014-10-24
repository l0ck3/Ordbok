---
title: "Security"
author: adron-hall
date: 2014-12-29
template: article.jade
---

The production API is secured with SSL and only accessible via HTTPS. To make a request against the secured end points requires an API key.

For any requests against the test system at http://apitest.deconstructed.io/ the accounts in production are matched against test, but are autonomous and can be used for testing. Any high load jobs may be stopped since this is only a small sand box that is available for testing work flow and sending inbound data for sample processing and querying.

It's a good idea to setup any test, UAT, or other environments that are used before pushing things to production to point at the Deconstructed http://apitest.deconstructed.io/ API end points to confirm anything built to feed into the API will work appropriately before moving it to https://api.deconstructed.io/

> The following is an example cURL request. 

```shell
curl -H "Accept: application/json" -H "api_key: 67A2AEED-some-api9-key4-DD267A72C650" -X POST -d "{appropriate_data_goes_here}" https://localhost:3007/application
```