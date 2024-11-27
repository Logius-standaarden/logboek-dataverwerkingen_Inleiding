# FAQ

Dit hoofdstuk bevat veelgestelde vragen over de standaard en in dit hoofdstuk worden deze veelgestelde vragen beantwoord en toegelicht.

## Vragen

### Wat is het doel van de standaard Logboek Dataverwerking?
De overheid moet zich verantwoorden over haar handelen. Daar valt ook onder het verantwoorden van het gebruik van gegevens. Met het gebruik van de standaard Logboek Dataverwerking is een organisatie in staat de logging van de verwerking van gegevens gestandaardiseerd uit te voeren. Dit geldt zowel voor verwerkingen binnen de eigen organisatie als voor verwerkingen die tussen organisaties plaatsvinden.

### Wie kan de standaard Logboek Dataverwerking gebruiken?
Elke organisatie die gegevens verwerkt kan de standaard Logboek Dataverwerking inzetten bij  processen waar logging en monitoring vanuit de wetgeving wenselijk is.

### Is de standaard alleen bedoeld voor de verwerking van persoonsgegevens?
Nee, de standaard kan worden toegepast voor andere toepassingen zoals bijvoorbeeld de registratie van (geografische) objecten.

### Wordt in de standaard ook uitgelegd hoe loggings plaatsvinden ten aanzien van beveiligingsincidenten, technische systeemactiviteiten en toegangsbeheer?
Nee, deze materie is buiten scope van de standaard Logboek Dataverwerkingen.

### Wie is eigenaar en beheerder van de standaard Logboek Dataverwerking?
Het ministerie van Binnenlandse Zaken en Koninkrijksrelaties is verantwoordelijk voor de standaard en de doorontwikkeling ervan. Het beheer wordt door Logius uitgevoerd.

### Is mijn organisatie verplicht de standaard Logboek Dataverwerking te implementeren?
Er zijn momenteel geen verplichtingen voor gebruik van de standaard. Op termijn zal de standaard aangeboden worden aan het Forum Standaardisatie voor mogelijke opname op de Pas-toe-of-leg-uit-lijst. 

### Hoe werken het Register van verwerkingsactiviteiten en het Logboek Dataverwerkingen samen?
In het Register van verwerkingsactiviteiten (art 30 AVG) zijn de binnen de organisatie uit te voeren taken en processen waarin verwerkingen worden uitgevoerd benoemd. In de standaard wordt de relatie gelegd tussen de beschreven processen in het register en de daadwerkelijk uitgevoerde activiteit waarbij gegevens zijn verwerkt. Hiermee is inzicht in de taak en activiteit waarvoor de gegevens verwerkt zijn.

### Wat is de relatie van Audit Log met de standaard?
In de standaard wordt geen identificerende informatie opgeslagen over gebruiker van het systeem (bijv. de ambtenaar die het systeem gebruikt). We gaan ervan uit dat daar in de organisatie een Audit log voor is ingericht, aangezien dat verplicht is vanuit BIO. 
Vanuit Audit Log kan wel een relatie gelegd worden met een verwerking in de standaard door te verwijzen naar de Operation ID die de verwerking identificeert. 

Voor redenatie hierachter, zie [besluit 4.4](https://logius-standaarden.github.io/logboek-dataverwerkingen_Inleiding/#geen-gegevens-over-gebruikers-in-logregels)

Daarnaast is het van belang om te beseffen dat het vastleggen van informatie over een gebruiker in de Audit Log, ook een dataverwerking is. Immers, de gegevens van de gebruiker (bijv. de ambtenaar die het systeem heeft gebruikt) worden daarbij opgeslagen (verwerkt). Dat is dus een eigen, aparte, dataverwerking die gelogd dient te worden in de Logboek Dataverwerkingen van de verwerker.

### Zijn er dingen die je moet aanpassen aan je Audit Log als je de standaard implementeert?
In de logging worden geen identificerende gegevens opgeslagen over gebruiker van het systeem (bijv. de ambtenaar die het systeem gebruikt). Om de link tussen een gebruiker en de standaard te maken, kan de Audit Log worden aangepast door te verwijzen naar de Operation ID die de dataverwerking identificeert die door de gebruiker is uitgevoerd. 

### Kan je de standaard implementeren als je een cloud (SaaS) applicatie gebruikt?
Ja dat kan. Het is wel van belang een duidelijk onderscheid te maken tussen verwerkingsverantwoordelijke en een verwerker van de gegevens. Dit bepaalt bijvoorbeeld de Register van verwerkingsactiviteiten waarnaar u dient te verwijzen bij implementatie van de standaard. 

Voor meer informatie over de rol van een verwerkingsverantwoordelijke en een verwerker kunt u de de website van [Autoriteit Persoonsgegevens](https://www.autoriteitpersoonsgegevens.nl/themas/basis-avg/avg-algemeen/verantwoordelijke-en-verwerker) raadplegen.

### Is de performance van de standaard getest? / Zal de standaard de performance van mijn applicaties beperken?
Ja, de performance is getest met een aantal demo-applicaties. De testen toonden aan dat er weinig tot geen performanceverlies was op geraakte applicaties.

### Moet ik mijn RvvA aanpassen als ik deze standaard implementeer?
Voor de implementatie van deze standaard is het noodzakelijk dat iedere verwerkingsactiviteit in uw RvvA uniek te identificeren is. Mocht dat nog niet het geval zijn, voeg dan een unieke identificator toe aan alle dataverwerkingen. 

Het is aanbevolen – maar niet verplicht – om de RvvA benaderbaar te maken met een API. Dat voorkomt dat de identificatoren van de verwerkingsactiviteiten “hardcoded” moeten  worden toegevoegd aan de logging en dat bij inzage, handmatig  gegevens uit de RvvA moeten worden toegevoegd in de logging.

Het is van belang dat, als de  RvvA wordt aangepast,de wijzigingen toevoegd worden als nieuwe verwerkingsactiviteiten met een eigen unieke identificator. Bestaande verwerkingsactiviteiten mogen niet wijzigen of verwijderd worden. Hierdoor blijven de oude verwijzingen uit de Logboek Dataverwerking intact. 

### Mijn organisatie heeft geen RvvA API. (Hoe) Kan ik dan nog steeds de standaard implementeren?
Ja, dat kan nog steeds. Het is niet verplicht een RvvA API te implementeren, de RvvA is uiteraard wel verplicht in het geval van persoonsgegevensverwerking. Voor de implementatie van de Logboek Dataverwerkingen is het van belang dat iedere verwerkingsactiviteit te identificeren is met een unieke identificator. 

Stel de RvvA is  uitgewerkt in een MS-Exceldocument en het systeem heeft daar geen API-toegang toe Daarnaast zijn de dataverwerkingenin de RvvA niet uniek te identificeren met een identificator. 

In dat geval zal er een kolom moeten worden toegevoegd aan het MS-Exceldocument waariedere dataverwerkingeen unieke identificator krijgt.  Deze identificatoren van de dataverwerkingen in uw RvvA zullen dan ‘hardcoded’ moeten worden toegevoegd in de logging. Bij inzage zullen de gegevens uit de RvvA, die horen bij een dataverwerking, handmatig moeten worden opgezocht.

### Hoe gedetailleerd moet mijn RvvA zijn om de standaard te implementeren? / Heeft de detailniveau van mijn RvvA invloed op de werking van de standaard?
De standaard gaat er alleen vanuit dat er een RvvA is. Hoe gedetailleerd de RvvA is, is een beslissing van de organisatie zelf. Uiteraard is het wel zo dat hoe gedetailleerder de RvvA is opgezet, hoe transparanter er kan worden gerapporteerd naar burger en (overige) overheid.

Wat gebeurt er als ik mijn RvvA wil wijzigen na de implementatie van de Logboek Dataverwerkingenstandaard?

Het is van belang dat als de RvvA aangepast moet worden,de wijzigingen toegevoegd worden als nieuwe verwerkingsactiviteit met een eigen unieke identificator. Bestaande verwerkingsactiviteiten mogen niet worden aangepast of verwijderd.

Hierdoor blijven de oude verwijzingen uit de Logboek Dataverwerking intact. 