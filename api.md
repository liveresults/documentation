# Liveresults public API
If you have built an 3rd party app your welcome to contact Peter Löfås (PETER @ LOFAS . SE) with inforamtion about it. We'll probably release an official list over 3rd party apps in the future

## Changelog
### September 10th 2014 
* Minor corrections of errors in the documentation and added informatiom about runner statuses

## Hash to minimize transfer
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
## API-url
The API can be accessed from the root of the liveresults webb (for example http://liveresultat.orientering.se/api.php). There is no authentication to use the API

## Response-format
All responses are JSON-formatted, all data is cached for 15 seconds so there is **NO idea** to call the methods more frequent than that.

## Runner statuses
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

## API-Methods
### getcompetitions
api.php?method=getcompetitions  
Returns a list of competitions that are available  

Example-response:
```
{ competitions : [  
     {   "id" : 10278, 
         "name" : "Demo #1", 
         "organizer" : "TestOrganizer", 
         "date" : "2012-06-01",
         "timediff" : 0},
    { "id" : 10279, 
      "name" : "Demo #2", 
      "organizer" : "TestOrganizer", 
       "date" : "2012-06-02",
       "timediff" : 1,
       "multidaystage" : 1,
       "multidayfirstday" : 10278
    }
]}
```
* timediff represents number of hours that the timezone of the competition is + or - **compared to Central European time (CET)**
* multidaystage and multidayparent are set if the competition is part of a multi day competition. stage refers to the stage of the competition (1,2,4,...,n) and firstday always refers to the competition id of the first stage

### getcompetitioninfo
_api.php?method=getcompetitioninfo&comp=xxx_  
Return information about a single competition  

Example-response:
```
{ "id" : 10278, 
"name" : "Demo #1", 
"organizer" : "TestOrganizer", 
"date" : "2012-06-01",
"timediff" : 0,
"multidaystage" : 1,
"multidayfirstday" : 10278
}
```
* timediff represents number of hours that the timezone of the competition is + or - **compared to Central European time (CET)**
* multidaystage and multidayparent are set if the competition is part of a multi day competition. stage refers to the stage of the competition (1,2,4,...,n) and firstday always refers to the competition id of the first stage

### getlastpassings
_api.php?method=getlastpassings&comp=XXXX&last_hash=abcdefg_  
Returns a list of competitions that are available  
**Parameters**
* comp - ID for competition
* last_hash - Hash of last response to only retreive when response have changed

Example-response:
```
{ 
     "status" : "OK", "passings" : [  
     {   "passtime" : "10:05:23", 
         "runnerName" : "TestRunner 1", 
         "class" : "Men Elite", 
         "control" : 1000,
         "controlName" : "Finish",
         "time" : 23430},
     {   "passtime" : "10:05:22", 
         "runnerName" : "TestRunner 3", 
         "class" : "Men Elite", 
         "control" : 1000,
         "controlName" : "Finish",
         "time" : 23330}
   ],
   "hash" : "abcdef...."
}
```
### getclasses
_api.php?method=getclasses&comp=XXXX&last_hash=abcdefg_  
Returns a list of classes in the competition  
**Parameters**  
* comp - ID for competition
* last_hash - Hash of last response to only retreive when response have changed

Example-response:
```
{ 
 "status": "OK", 
 "classes" : [
         {"className": "Öppen-1"},
         {"className": "Öppen-10"},
         ....
        {"className": "Öppen-8"}], 
"hash": "84b1fdfe67a524a1580132baa174cce1"
}
```
### getclassresults
_api.php?comp=10259&method=getclassresults&unformattedTimes=true&class=Öppen-1_  
Returns results for the class  
**Parameters**  
* comp - ID for competition
* unformattedTimes - if response should include unformattedTimes or if time should be formatted 
* class - the class to retreive results for 
* last_hash - Hash of last response to only retreive when response have changed

Example-response:
```
{
   "status":"OK",
   "className":"Gul h",
   "splitcontrols":[

   ],
   "results":[
      {
         "place":"1",
         "name":"Anton Mörkfors",
         "club":"Järfälla OK",
         "result":"17:02",
         "status":0,
         "timeplus":"+00:00",
         "progress":100,
         "start":6840000
      },
      {
         "place":"2",
         "name":"Leif Mörkfors",
         "club":"Järfälla OK",
         "result":"18:23",
         "status":0,
         "timeplus":"+01:21",
         "progress":100,
         "start":6840000
      },
      {
         "place":"3",
         "name":"Martin Kvarnefalk",
         "club":"Järfälla OK",
         "result":"21:07",
         "status":0,
         "timeplus":"+04:05",
         "progress":100,
         "start":6840000
      }
   ],
   "hash":"883fae6e4b8f0727b6ffabb7c403277c"
}
```

