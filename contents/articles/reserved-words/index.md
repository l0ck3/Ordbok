---
title: "Reserved Words"
author: adron-hall
date: 2015-12-31
template: article.jade
---

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
 	  
Other data can be sent in with the event that will be stored and added to the record and consociated will be converged into a single profile, which will provide the extra data for query searches.