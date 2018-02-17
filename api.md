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
### API-url
The API can be accessed from the root of the liveresults webb (for example http://liveresultat.orientering.se/api.php). There is no authentication to use the API

### Response-format
All responses are JSON-formatted, all data is cached for 15 seconds so there is **NO idea** to call the methods more frequent than that.

### Runner statuses
Runners in the responses all have a status-field indicating the status of the runner in the competition.

Valid statuses are: 
0 - OK  
1 - DNS (Did Not Start)  
2 - DNF (Did not finish)  
3 - MP (Missing Punch)  
4 - DSQ (Disqualified)  
5 - OT (Over (max) time)  
9 - Not Started Yet  
10 - Not Started Yet  
11 - Walk Over (Resigned before the race started)  
12 - Moved up (The runner have been moved to a higher class)  
