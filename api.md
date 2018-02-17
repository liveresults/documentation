# Liveresults public API
If you have built an 3rd party app your welcome to contact Peter Löfås (PETER @ LOFAS . SE) with inforamtion about it. We'll probably release an official list over 3rd party apps in the future

## Changelog
### September 10th 2014 
* Minor corrections of errors in the documentation and added informatiom about runner statuses

### Hash to minimize transfer
Most methods in the API contains the possibility to supply a last_hash parameter in the query to only receive a new response if something have changed. This way datatransfer out from the servers can be minimized and data cached better to please use this functionality!

When data have not changed the API will return this response instead
```
    { "status" : "NOT MODIFIED" } 
```
You don't need to calculate the hash yourself, it's returned in the responses as a property 
```
{ 
     ....
    "hash" : "abcdef....." 
    }
```
