---
title: "Status"
author: adron-hall
date: 2014-10-17
template: article.jade
---

`GET https://api.deconstructed.io/stat`

Submit a get against this API end point to receive a system status. At this time it just reports 'alive'. Eventually the intent is to have it report back the status of the nodes within the distributed system that is api.deconstructed.io, that will provide a status page of the entire Deconstructed ecosystem.

> To determine system status, issue a get request like this:

```shell
curl https://api.deconstructed.io
```
