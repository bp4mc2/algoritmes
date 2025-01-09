# Inleiding
Het model dat in dit document wordt beschreven is een uitwerking van de [versie 1 van de publicatiestandaard](https://aienalgoritmes.pleio.nl/wiki/view/2bcdf820-ce62-4249-95f7-d1a13fb6e1c9/handleiding-publicatiestandaard) voor het algoritmeregister. De definities van de gebruikte concepten zijn overgenomen uit de eveneens op basis van deze publicatiestandaard gemaakte [taxonomie voor het algoritmeregister](https://catalogus.kadaster.nl/ar/nl/).

Deze beschrijving is daarmee een bouwsteen in een werkwijze die de volgende stappen hanteert:
1) definiëren van het domein in een taxonomie met begrippen op [niveau 1](https://docs.geostandaarden.nl/mim/mim/#beschouwingsniveau-1-model-van-begrippen) van het Metamodel voor informatiemodellering (MIM)
2) uitwerken van deze taxonomie in een conceptueel informatiemodel op [MIM niveau 2](https://docs.geostandaarden.nl/mim/mim/#beschouwingsniveau-2-conceptueel-informatiemodel). Een conceptueel informatiemodel  definieert het ‘wat’: welke 'onderwerpen van gesprek' ('concepten', 'dingen’) worden onderscheiden in de beschouwde werkelijkheid, wat betekenen zij, hoe verhouden ze zich tot elkaar en welke informatie is daarvan relevant.
3) vertalen van dit model dat een representatie van informatie over de werkelijkheid is naar een logisch informatiemodel op [MIM niveau 3](https://docs.geostandaarden.nl/mim/mim/#beschouwingsniveau-3-logisch-informatie-of-gegevensmodel) voor een de digitale registratie en in de aanleverspecificatie van gegevens.
4) genereren van een technische aanleverspecificatie in bijvoorbeeld Json formaat en databasespecificatie in sql formaat.

In een dergelijke modelgedreven werkwijze zijn alle representaties met elkaar in lijn en liefst met elkaar verbonden. Dat betekent dat in api's waarin daadwerkelijk data wordt gepubliceerd en/of uitgewisseld de link naar volledige context wordt opgenomen, via het logische en conceptuele model en de onderleiggende begrippen met hun definitie en uitleg.

Het voorliggende informatiemodel is een concpetueel informatiemodel. 

Samen met het begrippenkader worden met dit model MIM niveau 1 en 2 ingevuld. Een logisch model ontbreekt voor de huidige publicatiestandaard. De huidige publicatiestandaard kant alleen een technisch model in  de vorm van een [json schema](https://github.com/MinBZK/Algoritmeregister/blob/main/schema.json]. Dit is niet veel meer dan een platte lijst met te registreren gegevens. Slechts enkele gegevens, zoals de risicoklasse, worden vastgelegd op basis van een keuzelijst. De meeste gegevens zijn beschrijvende teksten. 

# Van verantwoording naar governance
De kern van het model is gebaseerd op de Nederlandse algoritmestandaard. Deze standaard is in eerste instantie ontwikkeld als een rechttoe rechtaan lijst met een aantal gegevens die relevant zijn om algoritmes in een algoritmeregister te beschrijven. Dat is een belangrijke stap binnen de overheid om de toepassing van algoritmes en de implicaties en risico’s voor de samenleving inzichtelijk te maken. 

Voor governance op algoritmische toepassingen is een meer genuanceerde benadering nodig. Daarbij is het relevant om onderscheid te maken tussen een algoritmische toepassing, de algoritmes zelf en gebruikte methoden en technieken. De algoritmische toepassing heeft al dan niet maatschappelijke impact. Binnen 1 toepassing kunnen meerdere algoritmes worden ingezet. En om hergebruik van in algoritmes gebruikte methoden en technieken mogelijk te maken is ook het expliciet onderscheiden hiervan relevant.

Daarnaast maakt het model gebruik van bestaande semantische standaarden zoals dcat (Data Catalog Vocabulary) voor het beschrijven van datasets en adms (Asset Description Metadata Schema) voor het beschrijven van semantic assets. Door een algoritmeregister te beschrijven als asset repository en een algoritmische toepassing te beschrijven als ‘semantic asset’ worden algoritmeregisters en de daarin beschreven algoritmische toepassingen als zodanig vindbaar op het web. Ook kan daarmee een verbinding worden gemaakt met https://data.overheid.nl. Data.overheid wordt gevuld op basis van beschrijvingen van datasets op basis van dcat.

Een mogelijke vervolgstap is om een eerste versie van een logisch informatiemodel op MIM niveau 3 te maken dat enerzijds gereversed engineerd wordt op basis van de huidige standaard en tegelijkertijd de verbinding legt met het conceptuele model en daarmee ook met het begrippenmodel. Daarnaa kan de publicatiestandaard stap voor stap worden verfijnd in de zin van doorontwikkeld van een tekstuele beschrijving waarmee verantwoording wordt afgelegd over algoritmische toepassingen naar een plek waar naast deze verantwoording kennis over (soorten) algoritmes en bijbehorende (soorten) risico's, leveranciers, beschikbare datasets et cetera wordt gedeeld. Daarmee faciliteert de standaard een transparante, maar ook een excelente overheid.

# Modeldocumentatie
In het informatiemodel voor algoritmes is opgebouwd uit verschillende bouwstenen (packages). 

# Algoritme
Het domein Algoritme bevat de kern van het model. Het bijbehorende diagram is de versimpelde versie, gebaseerd op de standaard versie 1.0.0 van het algoritme register.
Centraal in dit domein staan de objecttypen Algoritme register en Algoritmische toepassing. De algoritmische toepassing is een semantische asset die een aantal kenmerken hergebruikt uit adms en daarmee indirect ook enkele kenmerken uit dcat (adms is een profiel op dcat). Het Algoritme register is een asset repository en hergebruikt eveneens een aantal kenmerken uit adms en dcat. Deze algemene, door de W3C (World Wide Web Consortium) aanbevolen standaard kenmerken zijn direct interpreteerbaar voor bijvoorbeeld zoekmachines en worden ook gebruikt in data.overheid.
1 algoritmische toepassing kan meerdere algoritmes gebruiken, bijvoorbeeld een combinatie van regelgebaseerde en zelflerende algoritmes. Met zo’n combinatie kan de betrouwbaarheid van de uitkomst worden verhoogd of kunnen zelflerende algoritmes via de toegepaste regels uitleggen hoe ze tot een resultaat zijn gekomen. Ook is denkbaar dat bijvoorbeeld voor de herkenning van bepaalde feiten en namen in teksten verschillende algoritmes worden ingezet. Deze algoritmes zijn niet geheel onafhankelijk: als iets een feit is, is het geen naam en andersom. 
1 algoritme kan vervolgens weer meerdere methoden of modellen gebruiken. In het voorbeeld van de herkenning van entiteiten in teksten kan eerst een methode worden gebruikt om teksten op te splitsen in woorden en vervolgens een beproefd open source algoritme om Nederlands te herkennen en tot slot een specifiek algoritme voor het herkennen van namen in Nederlandse teksten. Methoden en technieken zijn in de regel ergens beschreven en kunnen op basis van hun documentatie worden hergebruikt. 
Voor het beschrijven van documentatie wordt een algemeen patroon gebruikt. In zijn meest eenvoudige vorm is er een eenvoudige beschrijving, maar idealiter is er een webpagina met meer informatie. Documentatie kan betrekking hebben op een contactformulier met een beschrijving ‘er kan contact worden opgenomen via een contactformulier’, waarbij een url naar de webpagina met dit formulier gebruikelijk is. Maar het is ook mogelijk dat aan de beschrijving wordt toegevoegd ‘… dat kan worden opgevraagd bij de klantenservice’ of dat alleen de url naar een webpagina met een beschrijving van de procedure voldoende wordt gevonden.
Op dezelfde wijze kan ook een eventuele publiekspagina van een algoritmische toepassing, de beschrijving van het algoritmeregister zelf of de code base van een algoritme in bijvoorbeeld GitHub worden beschreven. Dit geldt ook voor een methode of model en voor een assessment. Deze zijn gemodelleerd als subtype van documentatie.
Een algoritmische toepassing heeft een (wettelijke) grondslag die beschrijft waarom een organisatie dit soort dingen mag of juist moet doen. Zo’n bron kan beschreven met een zin als ‘dit algoritme wordt ingezet na goedkeuring van ...’ of met een citeertitel en url die zijn ontleend aan wetten.nl.
In de meeste algoritmeregisters wordt voor iedere algoritmische toepassing een afbeelding opgenomen. Deze is gemodelleerd als een afbeelding conform het foaf vocabulaire. Foaf (friend of a friend) is een veel gebruikt vocabulaire dat is gemaakt om webpagina’s machine leesbaar te maken.
Zowel afbeeldingen, documentatie als grondslag zijn gemodelleerd als foaf documenten.
Algoritmische toepassingen kennen risico’s. Risico’s komen altijd naar boven uit een assessment. Op dit moment worden 2 typen assessment aanbevolen, namelijk een IAMA (Impact Assessment Mensenrechten en Algoritmes) en een DPIA (Data Protection Impact Assessment). 
Tot slot is zowel de bevoegde organisatie van belang die mag besluiten over de algoritmische toepassing als de organisatie die de algoritmische toepassing levert. Voor de beschrijving van een organisatie wordt de org (organisation) ontologie van de W3C hergebruikt. Dit maakt het mogelijk aan te sluiten op het register van overheidsorganisaties.

# Views op W3C vocabulaires
Adms, dcat, foaf, org zijn beschreven door de W3C. In het voorliggende informatiemodel hebben we deze vocabulaires uitgedrukt in UML met een overzicht van de in het kader van algoritmes relevante kenmerken. De namen voor deze kenmerken zijn vertaald naar Nederlandse termen in de context van algoritmes. Dit is puur voor de leesbaarheid gedaan. Het is niet de bedoeling dat door eventuele andere associaties bij deze Nederlandse termen de betekenis van de oorspronkelijke kenmerken verandert. Voor alle kenmerken is een link naar het oorspronkelijke Engelstalige begrip en de definitie daarvan opgenomen.

# Datatypes
De datatypes bevatten in de eerste plaats referentielijsten naar bestaande waardelijsten voor:
*	Publicatiecategorie (http://begrippen.kadaster.nl/ar/id/concept/Publicationcategory)
*	Organisatie (https://standaarden.overheid.nl/tooi)
*	Status (http://begrippen.kadaster.nl/ar/id/concept/Status)
*	Taal (https://en.wikipedia.org/wiki/ISO_639-3) 
*	ToepassingsCategorie (https://standaarden.overheid.nl/owms/4.0/doc/waardelijsten/thema-indeling-voor-officiele-publicaties)

Daarnaast bevatten datatypes de binnen het domein van algoritmes nog te definiëren waardelijsten:
*	MitigerendeMaatregel (bewaken, berusten, …)
*	TypeAssessment (IAMA, DPIA, …)
*	TypeMethodeOfModel (…)

Hieronder is een overzicht van alle packages in de huidige versie van het model. 

