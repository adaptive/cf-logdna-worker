# cf-dnalog-worker
simple cloudflare worker recipe to send logs into [logdna](https://logdna.com/)

## how to use
copy index.js content into your worker
change myApp and myHostName into whatever you want, read the logdna [Ingest API](https://docs.logdna.com/v1.0/reference#api)

* requestsPerBatch - how many requests to maximum batch per request
* maxRequestsAge - how much time to maximum old requests in the memory before sending it 

## about compiledPass

you should precompile your logdna ingestion key and store it in the compilePass parameters, you can simply type in console `btoa(username+':'+password)` where username is your ingestion key and password keep empty, and put the results into the parameter to save some cpu time(probably)


I left all the console.log command to better help you debug

### logged parameters:

+ user agent
+ referer
+ ip
+ countryCode
+ url
+ colo
+ method
+ x_forwarded_for
+ asn
