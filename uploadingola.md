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

## Förberedelser i OLA
Definiera först klasser och banor som vanligt.

## Vid tävlingen
* Gå in på http://liveresultat.orientering.se/adm/admincompetitions.php och gör tävlingen tillgänglig för visning. Markera Public och tryck Save.
* Starta programmet LiveResults.Client. Välj OLA.
* Gå igenom guiden för att göra inställningar för att ansluta till servern, välja tävling och välja etapp
* När du kommit igenom hela guiden klickar du på knappen start. Nu startar uppladdning av data till onlineservern.

Online-resultaten återfinns på http://liveresultat.orientering.se/
