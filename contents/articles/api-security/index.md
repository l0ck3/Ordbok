---
title: "Security"
author: adron-hall
date: 2014-10-27
template: article.jade
---

The production API is secured with SSL and only accessible via HTTPS. To make a request against the secured end points requires an API key.

> The following is an example cURL request. 

```shell
curl -H "Accept: application/json" -H "api_key: 67A2AEED-some-api9-key4-DD267A72C650" -X POST -d "{appropriate_data_goes_here}" https://localhost:3007/application
```