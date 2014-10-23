# Interaction By

`https://api.deconstructed.io/interaction/by/`

This end point is used for searching for specific application data. To use this end point submit a POST request with API key in the header. Inside the body of the request submit the appropriate key to be searched on as shown below in the cURL requests.

This first example shows how to retrieve a data element based on the actual key of the data element that was previously sent to Deconstructed. This key is the key that the sender created and sent with the data when submitting it to the https://api.deconstructed.io/interaction end point or the key the system generated and returned after receiving data without a key.

	curl -X POST -H "Accept: application/json" -H "Content-Type: application/json" -H "api_key: 67A2AEED-fake-api9-key4-DD267A72C650" -d '{"key":"application_data_key_identifier"}' http://apitest.deconstructed.io/interaction/by
	
This example shows how to search and retrieve a record or records based on some identifiers that would be matched against the knownid section of the data elements passed into the Deconstructed system.

	curl -X POST -H "Accept: application/json" -H "Content-Type: application/json" -H "api_key: 67A2AEED-fake-api9-key4-DD267A72C650" -d '{"knownid":[{"email":"the@future.com"},{"email":"the@future.com"}]}' http://apitest.deconstructed.io/interaction/by
	
This example is similar to the example above except with an additional knownid being sent called EmailId.

	curl -X POST -H "Accept: application/json" -H "Content-Type: application/json" -H "api_key: 67A2AEED-fake-api9-key4-DD267A72C650" -d '{"knownid":[{"email":"the@future.com"},{"email":"the@future.com"}]}' http://apitest.deconstructed.io/interaction/by

The knownid element can have as many identifiers sent in with the request as necessary.