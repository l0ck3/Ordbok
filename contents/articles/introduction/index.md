---
title: "Introduction"
author: adron-hall
date: 2020-10-20
template: article.jade
---

Welcome to the Deconstructed API documentation.  Deconstructed uses data you send to automatically create profiles of each user using your websites or applications. Through a continuous process called consociation, we use data you send to map a user to the different cookies, apps and services from which you send data about them.

Deconstructed’s user profiles can be searched in real-time to drive in-app or on-site personalization and contextualization, to drive user-level dashboarding and reporting, or to power the activities of other services in your stack.

Our Platform also provides a system of rules-based triggers and notifications which allow you to notify or push updates to any other services when a user meets the conditions you define in a rule.

For reference to how this documentation is built, and the code that is used to produce this documentation, check out the code repositories on github at:

 * [Ordbok](https://github.com/Deconstructed/Ordbok) - The actual documentation repo you're looking at right now.
 * [slate](http://github.com/tripit/slate) - Developer's documentation site.
 * [wintersmith](http://wintersmith.io/) - Node.js static site generator.

### Security

The production API is secured with SSL and only accessible via HTTPS. To make a request against the secured end points requires an API key.

For any requests against the test system at http://apitest.deconstructed.io/ the accounts in production are matched against test, but are autonomous and can be used for testing. Any high load jobs may be stopped since this is only a small sand box that is available for testing work flow and sending inbound data for sample processing and querying.

It's a good idea to setup any test, UAT, or other environments that are used before pushing things to production to point at the Deconstructed http://apitest.deconstructed.io/ API end points to confirm anything built to feed into the API will work appropriately before moving it to https://api.deconstructed.io/

> The following is an example cURL request. 

```shell
curl -H "Accept: application/json" -H "api_key: 67A2AEED-some-api9-key4-DD267A72C650" -X POST -d "{appropriate_data_goes_here}" https://localhost:3007/application
```

### Reserved Words

#### Reserved JSON Names with Interactions
When sending data into the Deconstructed services the data is accepted with a few key names that are reserved. They're broken out to root level items, which is simply the *key* and *value* and then the secondary level for reserved names in the value JSON data.

***Root Level:***
At the root level there are two required elements:

 * key - The key of the data. This can be left empty and the system will populate the key. The key must be of a GUID/UUID format of `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`.
 * value - The value name pair is simple the JSON object of data to be processed with Deconstructed. The reserved names for this are below.

***Secondary Level:***
In the value that stores the JSON, there is one required name. The other names are not required, except for having Deconstructed take actions or provide searching abilities against the data after the fact. More information is detailed by each:

 * knownids - (*Required*) The known id is an array of name value pairs that list each identifier that Deconstructed will use to converge data against. In the example above the knownid has three name value pairs, two are for *email* and one for *homeaddress*. The two emails are converged from two email addresses an inidvidual has used, and the long lat would have been something else that was added that the end user would have opted to connect data by. This way knownids go through process that takes consociate data and converges it all together into known graphed (relationships) to a profile.
 * event - (*Optional*) This reserved word is used to designate a user defined event having occured. An event might be something like `createUser`, `email sent`, or `user session started`. The event names can be anything that is a alphanumeric string. No special characters or wingdings. These names are then used as user defined event triggers which are queryable and used to initiate rules and actions after data processing is completed. For specific event criteria, see the list of reserved words around that. If a custom event with more specific detail needs to be added an event can be sent with the following additional reserved words that add capabilities to the event:
 	 * stamp - Adding this with the epoch of the time you want the event set to provides a user defined timeline of events, so that even though the event was received at X date and time it can also be checked & queried against this custom user defined date and time.
 	 * details - JSON data can be saved along with the event. This can be used for determining actions or other related things that might be specific just to the event itself.
 	  
Any other name value pairs sent will be stored as attributes of the user.
 
### API Key Requirements

Whenever any request is made to the system there are a set number of data elements that must be sent, retrieved or otherwise manipulated for a complete interaction with the Deconstructed System.

1. The API key sent with each request needs to match against whatever organization the API key belongs to, the organization key is then used to segment the data so that only the organization can save, interact and otherwise manipulate that organziation's data.
* The API key must exist in the system, be active and belong to the organization, and have the appropriate permissions set for the actions that are being requested with the key.
