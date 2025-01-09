# algoritmes
Deze repository beschrijft de taxonomie en het informatiemodel voor een metamodel voor het algoritmeregister. 
Deze beschrijving is gebaseerd op [versie 1.0 van de publicatiestandaard]([https://algoritmes.pleio.nl/attachment/entity/3f3de86f-6cc1-4229-92ba-658a7770291b](https://aienalgoritmes.pleio.nl/attachment/entity/a47f2708-48bd-4a10-8893-ab24ac8c7207). Binnen Nederland wordt de discussie over deze standaard gecoördineerd via <https://algoritmes.pleio.nl/>.

De taxonomie is opgezet conform de [Nederlandse Standaard voor het Beschrijven van Begrippen (NL-SBB)](https://docs.geostandaarden.nl/nl-sbb/nl-sbb/).
* De taxonomie wordt beheerd in de map [taxonomie](https://github.com/bp4mc2/algoritmes/blob/main/taxonomy/taxonomy.ttl)
* De taxonomie wordt vooralsnog voor mensen leesbaar gepubliceerd in de [Kadaster begrippencatalogus](https://catalogus.kadaster.nl/ar/nl/)
 
 Het informatiemodel is opgezet comform het [Metamodel voor Informatie Modellering (MIM)](https://docs.geostandaarden.nl/mim/mim/).
 * Het informatiemodel is beschikbaar in het Enterprise Architect eap formaat in de map [eap](https://github.com/bp4mc2/algoritmes/blob/main/eap/imar_v1.56.EAP) en in xmi formaat in de map [xmi](https://github.com/bp4mc2/algoritmes/blob/main/xmi/model.xmi).
* Het informatiemodel is voor mensen leesbaar gepubliceerd op https://regels.overheid.nl/.... 
* In het informatiemodel zijn de beschikbare EU en W3C standaarden voor het beschrijven van metadata gehanteerd:
  * [het Asset Description Metadata Schema (ADMS)](https://interoperable-europe.ec.europa.eu/collection/semic-support-centre/solution/asset-description-metadata-schema-adms) voor het beschrijven van algoritmische toepassingen en het algoritmeregister zelf
  * [het Data Catalog Vocabulary (DCAT)](https://www.w3.org/TR/vocab-dcat-3/), specifiek het [Nederlandse profiel](https://docs.geostandaarden.nl/dcat/dcat-ap-nl30/) hierop voor het beschrijven van de gebruikte datasets voor trainingsdata, testdata, respectievelijk brondata voor de algoritmische toepassing
  * [de W3C Organization Ontology](https://www.w3.org/TR/vocab-org/) voor het beschrijven van de organisatie die verantwoordelijk voor de algoritmische toepassing en voor de leverancier van een algoritmische toepsassing.
  * [de veelgebruikte FOAF specificatie](http://xmlns.com/foaf/spec/) voor het beschrijven van documentatie en afbeeldingen (visualisaties van algoritmische toepassingen)
  * [de W3C Vcard Ontoloty[(https://www.w3.org/TR/vcard-rdf/) voor het beschrijven van de contactgegevens voor een algoritmische toepassing.
* In het informatiemodel wordt onderscheid gemaakt tussen algoritmische toepassingen en algoritmes (met een vaak publiek toegankelijke codebase). Hiermee wordt het delen van kennis over algoritmes en hergebruik mogelijk.
* Daarnaast kennen algortmische toepassingen risico's die worden bepaald op basis van assesments zoals een IAMA. Ook hier geldt dat het onderscheid tussen de toepassing, de risico's van deze toepassing en de assesments waaruit deze risico's worden afgeleid de samenhang tussen deze zaken expliciet inzichtelijk maakt.
