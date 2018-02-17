# Uploading from OLA
This guide explains how to upload live results when using Swedish system OLA for event administration.

Live results are commonly used at major events where elite classes have several radio controls. 
But it may also be interesting to publish the final times for smaller events, without having any radio controls.

## Förberedelser
I OLA går det att använda MYSQL eller Intern Databas (H2) för lagring av tävlingen. Även om LiveResultat-klienten klarar att publicera liveresultat från båda databaserna är det **starkt rekommenderat** att använda MYSQL för tävlingar med liveresultat p.g.a. problem med access till H2-databaserna, speciellt via nätverk.

Om du använder intern databas i OLA. Se specifikt avsnitt om det i slutet av denna artikel.

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

## Anvädning av Intern Databas i OLA
Denna guide beskriver de extra steg som behöver göras ifall man använder Intern Databas i OLA och vill publicera liveresultat.

  *Steg 1 behöver enbart göras ifall liveresultat skall köras från en annan dator än servern)* 
* Dela OLAs databasmapp på nätverket (OBS! Datorn som kör liveresultat **måste ha skrivrättigheter till den utdelade mappen!**)
- Windows XP: C:\Documents and Settings\All Users\OLA5\db 
- Windows 10/7/Vista: C:\Users\Default\OLA5\db 
* Starta liveresultat-klienten och välj OLA5 Internal db som typ
* Peka ut den databas som du vill presentera liveresultat ifrån
* Välj tävling 
* Välj etapp

När man använder OLAs interna databas är det **mycket viktigt** att en annan OLA-klient är ansluten till denna databas INNAN du startar liveresultat-klienten mot den.

När fler än en anslutning sker mot databasen kommer den första anslutningen agera proxy för alla andra anslutningar varför all trafik mot databasen då kommer gå genom denna dator. 
