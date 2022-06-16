# **Inhoud**
- [Web applicatie](#web-applicatie)
- [Softwarekwaliteit](#softwarekwaliteit)
- [CI/CD](#cicd)
- [Professional](#professional)
# **Web applicatie**
Voor het bouwen van een full-stack applicatie zal ik gebruik gaan maken van een front-end in de taal VUE. Ik ga voor de back-end gebruik maken van C#, deze ga ik opslaan in een aparte repository.

## **Applicaties:**
- BetterNews-FrontEnd
- BetterNews-BackEnd

## **BetterNews-FrontEnd**
[Repository](https://github.com/457726/betternewsfrontend-s3)
### **Homepage**
Op de homepage krijg je een overzicht te zien van de meest trending nieuwsartikelen op dat moment, zodat mensen die niet opzoek zijn naar een specifiek onderwerp maar naar actualiteiten ook terecht kunnen op mijn website.
( afbeelding )
### **Specifieke pagina’s**
In mijn applicatie heb ik voor een aantal onderwerpen gekozen die ik zelf relevant vindt, wanneer je op een van deze onderwerpen klikt krijg je een overzicht te zien van de nieuwsartikelen gerelateerd aan dit onderwerp.

( afbeelding )
### **Zoeken**
Mijn applicatie biedt ook een mogelijkheid om op een specifiek onderwerp te zoeken, zodat een gebruiker die weet wat hij zoekt gericht nieuwsartikelen kan vinden over dit onderwerp. Je krijgt een overzicht te zien van verschillende nieuwswebsites.

![](https://i.imgur.com/EOQVsTV.jpg)
### **Accounts**
Ik maak gebruik van auth0 voor user-accounts, zo kan ik gebruikers bijhouden. Ook wil ik er voor zorgen dat gebruikers een beoordeling kunnen achterlaten op een artikel.

### **Beoordelingen**
Het is ook mogelijk om een beoordeling achter te laten voor een artikel. Hiervoor klik je op de knop "Beoordeel". Je komt dan op een pagina waar je netjes je mening achter kan laten en er voor kan kiezen om 1 tot 5 sterren te geven.

![image](https://user-images.githubusercontent.com/99723279/174195576-4fffa4a9-158f-4a1b-8266-b1f7cc1a2d85.png)

## **BetterNews-BackEnd**
[Repository](https://github.com/457726/VueBackEnd)

## **API**

Voor het ophalen van mijn nieuwsartikelen maak ik gebruik van een externe API van newsapi.org, dit is een erg toegankelijke API met veel mogelijkheden met betrekking tot het ophalen van verschillende artikelen.

Hieronder een voorbeeld hoe ik artikelen kan verstrekken op basis van zoek criteria:
![image](https://user-images.githubusercontent.com/99723279/174195903-0d5d8d65-e7bd-48df-abc1-e540bd1b26a9.png)

Naast de verschillende endpoints die ik opgezet heb voor het ophalen van de nieuwsartikelen bied ik een gebruiker ook de mogelijkheid om een artikel een bepaalde beoordeling te geven. Hiervoor maak ik gebruik van een zelfgemaakte API die op zijn beurt vervolgens communiceert met mijn database die ik gehost heb bij fontys. Het gaat hier om een MYSQL database, dit soort databases zijn toegankelijk en makkelijk in gebruik.

![image](https://user-images.githubusercontent.com/99723279/174196210-59eaa82b-718c-44d2-bbb2-e6209a894a2e.png)

Natuurlijk heeft de gebruikte tabel in mijn database ook nog zijn eigen structuur. Ik sla de titel van het artikel op in combinatie met de beoordeling en eventuele opmerkingen. Dit ziet er als volgt uit.

![image](https://user-images.githubusercontent.com/99723279/174196384-bd401e40-a64a-4978-b4e9-e8a57c2d7d38.png)


![](https://imgur.com/20A6xBF.jpg)
# **Softwarekwaliteit**
Om de softwarekwaliteit aan te tonen maak ik gebruik van SonarCloud, deze analyseert mijn code automatisch en goed gereviewed wordt. Iedere keer dat ik mijn code push naar git wordt deze geanalyseerd.

![](https://imgur.com/MLqODCY.jpg)
## **BetterNews-BackEnd**
[Repository](https://github.com/457726/VueBackEnd)
### **NewsAPI**
Om mijn artikelen op te halen maak ik gebruik van een newsapi, deze geeft resultaten van verschillende nieuws websites wereldwijd. In mijn applicatie verwerk ik deze data tot passende data en zorg ik voor verschillende mogelijkheden om deze informatie op te halen.

![](https://imgur.com/zZh9dOI.jpg)
# **CI/CD**
Voor CI/CD heb ik bij zowel de front- als backend in github actions verschillende .yaml bestaden. Aan de hand van deze bestanden wordt mijn code automatisch gepusht en gedeployed.

Op dit moment heb ik in mijn github verschillende .yaml bestanden die automatisch integreren.
# **Professional**
Voor het professioneel schrijven van mijn code wil ik gebruik gaan maken van een passende workflow. Hierdoor laat ik zien problemen serieus te nemen en deze op zo een passende manier mogelijk op te lossen. Dit werkt uiteindelijk in mijn voordeel omdat ik hierdoor het overzicht hou en hier op kan anticiperen.
