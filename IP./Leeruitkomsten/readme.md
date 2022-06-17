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
![image](https://user-images.githubusercontent.com/99723279/174196730-53e25e0b-9099-426e-b039-dc22e9dcaeb4.png)
### **Specifieke pagina’s**
In mijn applicatie heb ik voor een aantal onderwerpen gekozen die ik zelf relevant vindt, wanneer je op een van deze onderwerpen klikt krijg je een overzicht te zien van de nieuwsartikelen gerelateerd aan dit onderwerp.

![image](https://user-images.githubusercontent.com/99723279/174196688-165c1c50-114b-4aea-bd69-e3ec9e6806d0.png)

### **Zoeken**
Mijn applicatie biedt ook een mogelijkheid om op een specifiek onderwerp te zoeken, zodat een gebruiker die weet wat hij zoekt gericht nieuwsartikelen kan vinden over dit onderwerp. Je krijgt een overzicht te zien van verschillende nieuwswebsites.

![](https://i.imgur.com/EOQVsTV.jpg)
### **Accounts**
Ik maak gebruik van auth0 voor user-accounts, zo kan ik gebruikers bijhouden. Ook wil ik er voor zorgen dat gebruikers een beoordeling kunnen achterlaten op een artikel.

![](https://imgur.com/20A6xBF.jpg)

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




# **Softwarekwaliteit**
Softwarekwaliteit is geen eenvoudig begrip en kan van verschillende kanten bekeken worden. Zo kan je het zien als letterlijke kwaliteit van kode, maar op basis waarvan wordt deze kwaliteit dan bepaald? En wat voor eisen ga je hier aan stellen? Echter kan codekwaliteit ook als iets heel anders gezien, en dat is namelijk begrijpt de eindgebruiker de structuur van mijn applicatie? Is de opbouw logisch?

Eigenlijk zijn dit allemaal onderdelen die samen de kwaliteit van de software maken. Ik wil hier mee zeggen dat softwarekwaliteit niet alleen het letterlijk op orde hebben van je code etc. is maar dat het ook een stukje structuur binnen je programma is en geen onnodige moeilijkheid of iets dergelijks.

Ik heb voor het aantonen van mijn softwarekwaliteit verschillende dingen gedaan. Voor het testen van de softwarekwaliteit van mijn back-end heb ik er voor gekozen om gebruik te gaan maken van unit-tests. Dit in combinatie met een mockdal, dit is een techniek die je toepast als je de database niet wil raken. Nu weet ik zelf toevallig dat bij het gebruik van een ORM, bijv. Entity Framework je een in memory database kan draaien. Dit is als het ware een kopie van je database die alleen eventjes draait wanneer jij tests uit aan het voeren bent. Dit is erg handig en gebruiksvriendelijk. Maar omdat ik in dit geval geen gebruik heb gemaakt van Entity Framework heb ik zelf een mockdal aangemaakt met sortgelijke functies als mijn echte dal. Het verschil is dat ik in mijn mockdal een lijst met objecten heb die funtioneert als database.

Ik heb verschillende unit-tests uitgevoerd, bijvoorbeeld het achterlaten van een review met bijbehorende titel, bericht en cijfer. Daarnaast heb ik ook nog enkele tests geschreven om te kijken of het toegevoegde object ook wel daadwerkelijk de juiste informatie mee krijgt en niet bijv. gewoon maar leeg is. 

![image](https://user-images.githubusercontent.com/99723279/174198121-e48afd3c-c8aa-4f6f-98bf-99f600279b46.png)
![image](https://user-images.githubusercontent.com/99723279/174257726-09ca1912-8294-4c8c-b9f5-eee426469bc5.png)

Bijvoorbeeld het ophalen van alle beoordelingen van een bepaald artikel. Dit is belangrijk voor het laten zien van alle opmerkingen bij een artikel. Ik heb dit getest door meerdere reviews toe te voegen van verschillende artikelen. Vervolgens vraag ik alle revieuws van een bepaald artikel op en kijk ik of ik daadwerkelijk dit aantal reviews opgeslagen heb.

![image](https://user-images.githubusercontent.com/99723279/174198305-e0f85cc0-a2ce-493e-96d6-6381ae68776b.png)

# **CI/CD**
Voor CI/CD heb ik bij zowel de front- als backend in github actions verschillende .yaml bestaden. Aan de hand van deze bestanden wordt mijn code automatisch gepusht en gedeployed.

Ik heb gebruik gemaakt van SonarCloud. Die analyseert je code en komt automatisch met beveiligings-issues etc. Het is makkelijk in gebruik en er wordt bij iedere push op master een automatische scan uitgevoerd.

Dit was de kwaliteit in het begin:
![](https://imgur.com/MLqODCY.jpg)

Dit is de kwaliteit nu:
![image](https://user-images.githubusercontent.com/99723279/174198796-7afb0d64-a38a-4244-83ff-bb616750c7ee.png)

## **CD**

De CD regel ik doormiddel van Azure, zowel mijn front- als backend staan beide gedployed op azure. En worden bij iedere release ook weer opnieuw gedeployed zodat continue uptime gegarandeerd is.

<a href="https://ashy-ground-072245e03.1.azurestaticapps.net/">Front-end</a>\
<a href="https://newsbackendapiservice-s3.azurewebsites.net/">Back-end</a>

Microsoft Azure Platform (voorheen: Windows Azure Platform) is een cloudcomputingplatform van Microsoft waarmee een aantal internetdiensten aangeboden kan worden via het internet of binnen de omgeving van het eigen bedrijf. Microsoft wil hiermee de concurrentie aangaan met andere cloudsystemen die software as a service (SaaS) aanbieden, zoals Google Compute Engine van Google en EC2 van Amazon. Deze software hoeft niet geïnstalleerd te worden op de computer van de gebruiker, alles gebeurt via het web; aan de server-kant.

Hier beneden zie je de workflow die ik gebruik voor mijn back-end. Op deze manier wordt er iedere keer een nieuwe versie gedeployed naar azure.

``` yaml
name: Build and deploy .NET Core app to Windows WebApp NewsBackEndAPIService-S3
on:
  push:
    branches:
    - main
env:
  AZURE_WEBAPP_NAME: NewsBackEndAPIService-S3
  AZURE_WEBAPP_PACKAGE_PATH: NewsBackEnd/publish
  AZURE_WEBAPP_PUBLISH_PROFILE: ${{ secrets.NewsBackEndAPIService_S3_b384 }}
  CONFIGURATION: Release
  DOTNET_CORE_VERSION: 5.0.x
  WORKING_DIRECTORY: NewsBackEnd
jobs:
  build-and-deploy:
    runs-on: windows-latest
    steps:
    - uses: actions/checkout@v2
    - name: Setup .NET Core
      uses: actions/setup-dotnet@v1
      with:
        dotnet-version: ${{ env.DOTNET_CORE_VERSION }}
    - name: Restore
      run: dotnet restore "${{ env.WORKING_DIRECTORY }}"
    - name: Build
      run: dotnet build "${{ env.WORKING_DIRECTORY }}" --configuration ${{ env.CONFIGURATION }} --no-restore
    - name: Test
      run: dotnet test "${{ env.WORKING_DIRECTORY }}" --no-build
    - name: Publish
      run: dotnet publish "${{ env.WORKING_DIRECTORY }}" --configuration ${{ env.CONFIGURATION }} --no-build --output "${{ env.AZURE_WEBAPP_PACKAGE_PATH }}"
    - name: Deploy to Azure WebApp
      uses: azure/webapps-deploy@v2
      with:
        app-name: ${{ env.AZURE_WEBAPP_NAME }}
        package: ${{ env.AZURE_WEBAPP_PACKAGE_PATH }}
        publish-profile: ${{ env.AZURE_WEBAPP_PUBLISH_PROFILE }}
    - name: Publish Artifacts
      uses: actions/upload-artifact@v1.0.0
      with:
        name: webapp
        path: ${{ env.AZURE_WEBAPP_PACKAGE_PATH }}
```

# **Professional**

## **Git Workflow**

Ik wilde gebruik gaan maken van een simpele git workflow. Dit omdat ik nog niet eerder bewust met een workflow gewerkt had en daarnaast de enigste ontwikkelaar zou zijn binnen dit project. Ik heb gekozen voor de git workflow "Feature branches"

"De workflow van de feature branch gaat ervan uit dat alle ontwikkelaars in het team dezelfde kennis en positie hebben. In grotere teams is er echter altijd een vorm van hiërarchie in het bedrijf.

In dit geval kun je merge-verzoeken en push-permissies gebruiken waarmee je het pushen tot geselecteerde branches in de repository kunt beperken en de volledige controle over de code kunt behouden.

Voordat een branch wordt samengevoegd met Master, moet deze worden geverifieerd en gecontroleerd op fouten. Junior-ontwikkelaars kunnen een samenvoegverzoek maken en dit toewijzen aan een van de Senioren, zodat ze de code kunnen bekijken en opmerkingen kunnen achterlaten. Als alles in orde is, wordt het verzoek geaccepteerd en wordt de branch samengevoegd."

Bron: <a href="https://buddy.works/blog/5-types-of-git-workflows">Git Workflows</a>

![image](https://user-images.githubusercontent.com/99723279/174199816-9823674f-a622-4ac8-9179-0970bf9fcf64.png)

In de praktijk heb ik deze workflow ook toegpast en dit beviel me erg goed. Echter zou ik in een groter team voor een andere workflow kiezen.

## **Feedback**

Het feedback vragen verliep bij mij in het begin van het schooljaar nog niet zoals ik gewild had. Ik was te veel bezig met onderzoeken, en bleef hier zo in hangen dat ik er niet aan dacht om ook de voortgang te laten zien of in ieder geval te laten weten dat ik bezig was met onderzoek en nog niet zo zeer functioneel. Een volgende keer wil ik dan ook structureel de docent gaan spreken en er voor zorgen dat deze op de hoogte blijft van zowel mijn praktische voortgang als bijv. mijn onderzoeksvoortgang zodat de vakdocent een goede visie op mijn voortgang heeft.
