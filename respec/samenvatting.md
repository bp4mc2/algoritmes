Deze specificatie beschrijft het informatiemodel voor het algoritmeregister comform het [Metamodel voor Informatie Modellering (MIM)](https://docs.geostandaarden.nl/mim/mim/).

De status is *'concept, ter inspiratie'*. De huidige publicatiestandaard is een eenvoudige lijst met te publiceren aspecten van algoritmische toepassingen. Dit informatiemodel is bedoeld ter inspiratie om de publicatiestandaard door te ontwikkelen tot een volwaardige metadatastandaard.

In dit informatiemodel worden de bouwstenen van beschrijvingen van algoritmische toepassingen als aparte informatieobjecten onderscheiden. Daarnaast wordt aangesloten bij bestaande semantische standaarden vanuit de EU en de W3C.
* In het informatiemodel zijn de beschikbare EU en W3C standaarden voor het beschrijven van metadata gehanteerd:
  * [het Asset Description Metadata Schema (ADMS)](https://interoperable-europe.ec.europa.eu/collection/semic-support-centre/solution/asset-description-metadata-schema-adms) voor het beschrijven van algoritmische toepassingen en het algoritmeregister zelf
  * [het Data Catalog Vocabulary (DCAT)](https://www.w3.org/TR/vocab-dcat-3/), specifiek het [Nederlandse profiel](https://docs.geostandaarden.nl/dcat/dcat-ap-nl30/) hierop voor het beschrijven van de gebruikte datasets voor trainingsdata, testdata, respectievelijk brondata voor de algoritmische toepassing
  * [de W3C Organization Ontology](https://www.w3.org/TR/vocab-org/) voor het beschrijven van de organisatie die verantwoordelijk voor de algoritmische toepassing en voor de leverancier van een algoritmische toepsassing.
  * [de veelgebruikte FOAF specificatie](http://xmlns.com/foaf/spec/) voor het beschrijven van documentatie en afbeeldingen (visualisaties van algoritmische toepassingen)
  * [de W3C Vcard Ontoloty[(https://www.w3.org/TR/vcard-rdf/) voor het beschrijven van de contactgegevens voor een algoritmische toepassing.
* In het informatiemodel wordt onderscheid gemaakt tussen algoritmische toepassingen en algoritmes (met een vaak publiek toegankelijke codebase). Hiermee wordt het delen van kennis over algoritmes en hergebruik mogelijk.
* Daarnaast kennen algortmische toepassingen risico's die worden bepaald op basis van assesments zoals een IAMA. Ook hier geldt dat het onderscheid tussen de toepassing, de risico's van deze toepassing en de assesments waaruit deze risico's worden afgeleid de samenhang tussen deze zaken expliciet inzichtelijk maakt.
