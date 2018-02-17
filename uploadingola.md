# Uploading from OLA
This guide explains how to upload live results when using Swedish system OLA for event administration.

Live results are commonly used at major events where elite classes have several radio controls. 
But it may also be interesting to publish the final times for smaller events, without having any radio controls.

## Förberedelser
Om **MySQL** används som databas för tävlingen i OLA och LiveResults.Client (uppladdningsklienten) körs på en annan dator **MÅSTE** port **3306** vara öppen för inkommande trafik till servern.

* Gå in på http://liveresultat.orientering.se/adm/admincompetitions.php och sätt upp tävlingen.
* Notera CompetitionID.
* Ladda hem LiveResults.Client från [https://liveresults.github.io/documentation/](https://liveresults.github.io/documentation/) och
installera.
