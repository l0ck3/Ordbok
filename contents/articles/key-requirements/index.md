---
title: "API Key Requirements"
author: adron-hall
date: 2014-10-26
template: article.jade
---

Whenever any request is made to the system there are a set number of data elements that must be sent, retrieved or otherwise manipulated for a complete interaction with the Deconstructed System.

1. The API key sent with each request needs to match against whatever organization the API key belongs to, the organization key is then used to segment the data so that only the organization can save, interact and otherwise manipulate that organziation's data.
* The API key must exist in the system, be active and belong to the organization, and have the appropriate permissions set for the actions that are being requested with the key.
