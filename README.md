# LiveResults for Orienteering
This page includes documentation about the liveresults system using in many orienteering events. It's divided into information for [organizers](#organizer), [developers](#developer) and [users](#user).

## Download
LiveResults Client is used for uploading results from your event

Download [LiveResults Client 2022-04-12](https://github.com/petlof/liveresults/releases/download/Release20220412_2/LiveResults.Client-2022-04-12.zip)  
Released: 2022-04-12
Changelog: See [changelog](https://github.com/petlof/liveresults/releases/tag/Release20220412_2)

## Background
The system have been used during many international events among others WOC2017, WOC2016, WOC2015, WOC2014, EOC2012, WUOC2010, JWOC2008, JWOC2007, WOC2006, WOC2004
and numerous national events such as FIN-5, Swedish Elitserien 2006-, and 1000+ other events since 2006

The system is free and open source and dependent on contributions for continious development. If you like it - please give a contribution for further development.

[![PayPal - The safer, easier way to pay online!](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=peter%40lofas%2ese&lc=US&item_name=Orienteering%20LiveResults&currency_code=EUR&bn=PP%2dDonationsBF%3abtn_donateCC_LG%2egif%3aNonHosted)

<a name="organizer"></a>
## Information for Organizers
The system currently supports uploading results from the Swedish OLA system, SSFTiming, MEOS, OLEinzel (and OLStaffel) and other system that support output of IOF-XML continously.

If you would like to upload from an event system not listed above, please contact peter@lofas.se with information about the system and example export files.

* [Guide for publishing Live Results when using SportSoftware (OE/OS) for event administration](uploadingsportsoftware.md)
* [Guide for publishing Live Results when using OLA for event administration](uploadingola.md)

### Events with many expected online viewers or customized layout
If you host a big international event and expect a large number of online visitors or want to have a customized logotype on the liveresults-page there is a possibility to rent cloud-based servers to a low cost (about 10EUR for one week) that will handle the traffic and show your logo. Please contact peter @ lofas .se if your are interested in this.

<a name="developer"></a>
## For Developers
The system exposes a public free api that can be used for 3:rd party developers that want to create applications using data from the liveresults (for example Apps for Mobile Phones).
Read more about the [Liveresults Public API](api.md)

<a name="user"></a>
## For Users
