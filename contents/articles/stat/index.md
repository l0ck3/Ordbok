---
title: "Status"
author: adron-hall
date: 2014-02-15
template: article.jade
---

`GET https://api.deconstructed.io/stat`

Submit a get against this API end point to receive a system status. At this time it just reports 'alive'. Eventually the intent is to have it report back the status of the nodes within the distributed system that is api.deconstructed.io, that will provide a status page of the entire Deconstructed ecosystem.

> To determine system status, issue a get request like this:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```