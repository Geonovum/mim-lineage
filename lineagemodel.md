# Lineagemodel

## Inleiding

### Wat is lineage in deze context?
In figuur 1 uit de *Handreiking data lineage* worden de verschillende aspecten van lineage getoond. 
De hier beschreven lineage geeft invulling aan de relaties tussen gegevens, gegevensmodellen en grondslagen. 
De gegevensmodellen uit figuur 1 worden in dit document geïdentificeerd als modelelementen of begrippen.

![Gegevens in context](media/Gegevens_in_context.jpg "Gegevens in context")

In de context van deze toepassing betekent lineage het leggen van betekenisvolle verbindingen tussen modelelementen en begrippen uit de vier beschouwingsniveaus die MIM onderkent.

### Waarom lineage?
De waarde van lineage, zoals beschreven in de *Handreiking data lineage*, ligt op het gebied van:  
* Vertrouwen en transparantie  
* Voldoen aan wet- en regelgeving  
* Impact- en foutanalyse  
* Verbetering van gegevenskwaliteit  
* Kennis, overzicht, inzicht en sturing  

In de optimale situatie is van ieder (bron)gegeven in een technisch datamodel bekend hoe het zich verhoudt tot de modelelementen en begrippen op de hogere beschouwingsniveaus. 
Hiermee kunnen de genoemde waarden daadwerkelijk worden gerealiseerd.

Lineage wordt aanbevolen, maar is niet verplicht. 
Modellen op alle niveaus hebben ieder een eigen toepassingsgebied en daarmee bestaansrecht. 
In de praktijk zullen organisaties voor een specifiek model niet altijd alle beschouwingsniveaus hebben ingevuld of zullen invullen. 
In dergelijke situaties zijn niet alle hier beschreven vormen van lineage mogelijk.

### Lineage in en tussen verschillende MIM-beschouwingsniveaus
We onderscheiden verticale en horizontale lineage.

* **Verticale lineage** ontstaat door het leggen van relaties tussen modelelementen van verschillende niveaus, of tussen een modelelement en een begrip uit een begrippenkader.  
* **Horizontale lineage** ontstaat door het leggen van relaties tussen modelelementen op hetzelfde niveau, maar afkomstig uit verschillende modellen.  

Horizontale lineage tussen begrippen uit verschillende begrippenkaders betreft de zogenoemde harmonisatierelaties uit de NL-SBB en wordt [aldaar](https://docs.geostandaarden.nl/nl-sbb/nl-sbb/#harmonisatiesrelaties) beschreven.

### Lineage en wet- en regelgeving
Een van de doelstellingen van lineage is dat van een gegeven kan worden vastgesteld welke wet- en regelgeving van toepassing is. 
Op die manier kan uiteindelijk ook worden nagegaan of aan de gestelde eisen wordt voldaan.

### Lineage en definities

#### Geannoteerde definities
De meeste modelelementen hebben verplicht een definitie: een beschrijving van de betekenis van dat modelelement. 
In zo’n beschrijving kunnen een of meerdere gebruikte termen expliciet gekoppeld zijn aan een begrip. 
Dit wordt een *geannoteerde definitie* genoemd.  

Bij een geannoteerde definitie kunnen zowel de afzonderlijke termen uit de definitie als het modelelement in zijn geheel een lineage-relatie hebben met een begrip.  

Zowel conceptuele informatiemodellen als logische gegevensmodellen kunnen geannoteerde definities bevatten.

#### Het hoofdonderwerp van een definitie
*(Nog uit te werken in dit document.)*
Zie: onderwerp van gesprek. 

#### Redundantie van definities
In MIM is een definitie voor veel modelelementen een verplicht metagegeven. 
Wanneer de definitie van een modelelement exact gelijk is aan die van een modelelement of begrip waarmee een lineage-relatie bestaat, kan dit als redundant worden ervaren.  

Het verdient echter de voorkeur om deze definities toch te herhalen, zodat het model ook zelfstandig goed te begrijpen blijft.

### Aanpak: per koppelvlak tussen niveaus een model maken
*(Nog uit te werken in dit document.)*

## Semantische herleidbaarheid 

Een begrippenkader met begrippen en een conceptueel informatiemodel (CIM) kunnen gebruikt worden om te komen tot een welgevormde definitie van een gegevenstype die goed leesbaar en ook nog steed heel helder is voor gebruikers. Hierbij wordt zowel gekeken naar definities en naar semantische herleibaarheid, beide horen bij elkaar. De laatste is een aanvulling op de eerste. Het doel is telkens om betekenis van elementen op ieder beschouwingsniveau uit te drukken met een welgevormde verwoording van die betekenis met een definitie en om hierna semantische verwijzingen aan te geven waarop de tekst van deze definitie is gebaseerd. 

Dit wordt uitgewerkt aan de hand van een voorbeeld. 

### Voorbeeld ### 

In dit voorbeeld is een begrippenkader uitgewerkt naar een CIM en beide weer zijn gebruikt bij het maken van gegevensobjecttype en een gegevenstype in een LGM. 

**Begrippen in een begrippenkader:**

- Werknemer: Een werknemer is een natuurlijk persoon die werkt voor een organisatie. 
- Woonplaats: Een woonplaats is een afgebakend grondgebied met een eigen begrenzing dat gelegen is binnen het grondgebied van een gemeente, dat onder andere bestemd is voor bewoning door mensen.
- Geboorteplaats: Een geboorteplaats is de plaats waar een natuurlijk persoon is geboren, in Nederland is dit altijd een woonplaats. 

**Modelelementen in een CIM:** 

- een objecttype _Natuurlijk persoon_
   - een relatietype '_is geboren in_'
      - Deze relatie ligt tussen objecttype Natuurlijk Persoon en een objecttype Woonplaats.
      - De rol die een plaats speelt in deze relatie is dat deze de _geboorteplaats_ is van de natuurlijk persoon.
   - een relatietype '_werkt bij_'
      - Deze relatie ligt tussen objecttype Natuurlijk Persoon en een objecttype Organisatie.
      - De rol die een natuurlijk persoon speelt in deze relatie is dat deze de _werknemer_ is van de organisatie
- een objecttype _Woonplaats_
   - een eigenschaptype 'naam', met definitie: De officiele naam van een Woonlaats.
   - een eigenschaptype 'code', met definitie: De code is de officiele identificatie van een Woonplaats

**Modelelementen in een LGM:**

Het model beschrijft een aantal gegevens die bijgehouden worden over werknemers die werken bij de eigen organisatie, in een registratie die enkele van deze gegevens uitwisselt met gebruikers: 

- een gegevensobjecttype _Geregistreerde werknemer_
   - een aantal gegevenstypen betreffende de naam en een werknemersnummer (maar deze worden niet nader uitgewerkt in het voorbeeld) 
   - een attribuuttype 'geboorteplaatscode' --> deze wordt uitgewerkt in onderstaand voorbeeld

Merk op dat het gegeven in geboorteplaatscode gaat over het gegevenstype: code van woonplaats. Het gegevenstype had dus ook woonplaats of code kunnen heten, maar dat is onvoldoende helder als het gaat om de geboorteplaats van de werknemer. Om soortgelijke redenen is ook niet de term geboorteplaats gebruikt maar geboorteplaatscode, om aan te geven dat het gegevenstype over de code gaat en niet over de naam van de woonplaats. Dit zorgt ervoor dat het logische gegevensmodel niet verwarrend is. Echter, er is geen begrip met de voorkeursterm geboorteplaatscode. 
  
Vraag: wat is nou een goede definitie van het gegevenstype geboorteplaatscode? 

Een antwoord kan zijn om deze uit de in het CIM gedefinieerde code te halen: de officiele identificatie van een Woonplaats. We raken dan echter relevante context kwijt, te weten dat het om de geboorteplaats gaat. 

Een ander antwoord zou daarom kunnen zijn om de definitie van het begrip geboorteplaats te gebruiken: een woonplaats waar een natuurlijk persoon is geboren. Maar het gegeven zelf gaat over de code ervan, dus dat klopt ook niet echt. 

Laten we daarom eerst kijken naar de semantische herleidbaarheid, gebruik makende van de bijbehorende concepten uit het vorige hoofdstuk.

**Semantische herleidbaarheid van het gegevenstype geboorteplaatscode:**

- onderwerp van gesprek: Natuurlijk persoon uit het CIM
   - niet zomaar een Natuurlijk persoon, maar een natuurlijk persoon die een werknemer is bij onze organisatie
- eigenschaptype: 'code' van Woonplaats uit het CIM 
   - lexicaal pad: de geboorteplaats van een natuurlijk persoon, in CIM termen: de rol die de woonplaats speelt in de relatie met een natuurlijk persoon (en dit is wat anders dan waar de persoon woont)

Merk op dat alleen de code van de woonplaats niet duidelijk maakt dat het om de geboorteplaats van een natuurlijk persoon gaat, het onderwerp van gesprek van dit gegevenstype is de natuurlijk persoon (niet de woonplaats). Het lexicale pad verbind het eigenschaptype code van woonplaats met het onderwerp van gesprek. 

Wanneer we de semantische herleidbaarheid beschouwen als onderdeel van een formele specificatie, en de oorspronklijke definities van de betrokken begrippen hierin subtitueren dan zou de formele definitie zijn: 
'De code is de officiele identificatie van een Woonplaats.' die de 'Een geboorteplaats is een plaats waar een natuurlijk persoon is geboren, in Nederland is dit altijd een woonplaats.' van een 'Natuurlijk persoon' die 'Een werknemer is een natuurlijk persoon die werkt voor een organisatie.' is bij onze 'Organisatie. Merk op dat Natuurlijk persoon' en 'Organisatie' ook nog uitgeschreven kunnen worden. 

Dit is heel exact, maar niet goed leesbaar. Merk ook op dat er extra woorden nodig zijn zoals 'die de' en 'van een' en 'is bij'. Semantische herleidbaarheid letterlijk uitschrijven levert meestal geen goed leesbare definities op voor de doelgroep van een model. Het is dan ook niet gebruikelijk om een definitie van een gegevenstype in een gegevensmodel op deze manier uit te schrijven. Het moet daarom altijd mogelijk zijn eigen verwoordingen toe te kennen. 

**Definitie van het gegevenstype geboorteplaatscode:**

Semantische herleidbaarheid is erg nuttig om te komen tot een goede definitie. Hiervan gebruik makende komen we tot teksten zoals: 
- De geboorteplaatscode is de code van de woonplaats die de geboorteplaats is van de natuurlijk persoon die werknemer is bij onze organisatie. 
- De geboorteplaatscode is de code van de woonplaats waarin een werknemer van onze organisatie is geboren.

Beide zijn heel helder. De eerste volgt zo veel als mogelijk de semantische herleidbaarheid. De tweede is ook heel helder en is nog prettiger leesbaar voor mensen. Deze beide verwoordingen zijn daarom goed. 

Althans, dit is zo wanneer _semantische herleidbaarheid_ ook is aangebracht **in aanvulling op** de _definitie van het gegevenstype_. Met de gespecificeerde semantische verwijzingen zijn dan _alle_ bijbehorende begrippen terug vinden en kan het bijbehorende CIM bestudeerd worden om te duiden of het om hieribj een eigenschaptype of relatietype of objecttype of iets anders gaat. Zo vinden we terug: 
- de begrippen: werknemer, woonplaats en geboorteplaats uit het begrippenkader
- extra begrippen die relevant zijn zoals natuurlijk persoon en organisatie
- aanvullend geeft het CIM aan dat er sprake is van een code van een woonplaats en dat de geboorteplaats een rol is die ingevuld wordt door een woonplaats. 

Wat er met het gegevenstype 'geboorteplaatscode' bedoeld wordt is dan volledig helder. Merk ook op dat hoe meer er gewerkt wordt met specialistische begrippen, of hoe meer "platgeslagen" een logisch gegevensmodel is opgezet, hoe belangrijker een goede definitie met bijbehorende semantische herleidbaarheid wordt. 

Tot dusver het voorbeeld. Onderstaande werkt nader uit hoe semantische herleidbaarheid precies gespecificeerd wordt. Merk op dat dit per modeltype verschillend is zijn omdat semantische verwijzingen in een CIM naar begrippen verwijzen en in LGM naar CIM modelelementen en van daaruit naar begrippen. Het doel is hierbij echter telkens hetzelfde. 

### Lineage vanuit conceptueel informatiemodel naar een begrippenkader

In deze paragraaf wordt aangegeven hoe een begrippenkader met begrippen gebruikt kan worden om semantische herleidbaarheid aan te brengen in een CIM. 
 
De definitie van een modelelement in een CIM heeft een zeer sterke relatie met de definitie van een begrip uit een begrippenkader. Een begrippenkader en een conceptueel informatiemodel beschrijven immers beiden een model van dezelfde werkelijkheid. De ene beschrijft begrippen waarmee we uitdrukking geven aan het beschrijven van die werkelijkeheid, de andere geeft de conceptualisatie aan van dezelfde werkelijkheid, door middel van objecttypen, eigenschaptypen, relatietypen enzovoorts. Het is daarom in principe zo dat de terminologie in een CIM overeenkomt met de voorkeurstermen van de gerelateerde begrippen, daar waar mogelijk, mede ook om geen onnodige (spraak) verschillen te krijgen. Dit is niet altijd mogelijk, maar dit is wel een streven. De spelregels in onderstaande tabel geven dit aan. 

#### Modelelementen uit een CIM waarvoor semantische verwijzingen mogelijk zijn 

Dit zijn in principe alle modelelementen die een definitie kunnen hebben en ten minste alle modelelementen die een definitie hebben (altijd behoren te hebben). 

| Modelelement | semantische verwijzing naar | kardinaliteit | spelregels, bij 1 modelelement van dit type hoort                     | 
| ------------ | --------------------------- | ------------- | --------------------------------------------------------------------- | 
| objecttype   | begrip                      | 0..*          | precies 1 begrip                               |  
| eigenschaptype | begrip                    | 0..*          | precies 1 begrip. Als dit begrip algemeen van aard is, dan geeft het objecttype de context aan waarbinnen het begrip geinterpreteerd moet worden. | 
| eigenschaptype, classifierend | begrip     | zie enumeratie | elke enumeratie kent precies 1 begrip. | 
| relatietype, associatief | begrip          | 0..*          | 1..* begrippen. 
| relatietype. compositie  | begrip          | 0..*          | 0 begrip, de betekenis is in principe: onderdeel van |  
| relatierol | begrip |                      | 0..1          | als de rol qua naam afwijkt van het objecttype waar de rol bij hoort, dan 1..1, anders: zie objecttype | 
| ...        | begrip |                      | 0..*          | overige modelelementen met een defintie | 

_Interpretatie van de semantische verwijzing_

De relatie tussen een conceptueel modelelement en een begrip moet strikt worden opgevat. Het gaat immers om een formele modellering van (informatie over) de werkelijkheid. De semantische verwijzing tussen een conceptueel modelelement en een begrip geeft altijd aan dat de definities overeenkomen, oftewel 1 op 1 op elkaar gebaseerd zijn en in ieder geval grotendeels overeenkomen. De verwoording is mogelijk anders, maar de betekenis is hetzelfde. Het kan zijn dat er meerdere begrippen zijn gebruikt, de betekenis is dan nog steeds geheel overeenkomend, er is enkel sprake van een combinatie. 

Het is mogelijk dat MIM in een latere versie ook niet exact overeenkomende semantische verwijzingen toestaat. De semantische verwijzingen zullen dan een aanduiding of classificatie krijgen. Dit is op het moment nog niet uitgewerkt.

#### Lineage op model niveau 

In een CIM kunnen modelelementen voorkomen die semantische verwijzingen hebben naar begrippen uit verschillende begrippenkaders. Hierover kan extra informatie worden toegevoegd in het model. 

| Metagegeven | semantische verwijzing naar | kardinaliteit | 
| ------------ | --------------------------- | ------------- |
| modelidentificatie begrippenkader model | begrippenkader     | 0..*          | 
| naam begrippenkader  | begrippenkader model    | 0..*          | 
| versie begrippenkader  | begrippenkader modelversie     | 0..*          | 

_Optionele spelregels_ 

Deze kunnen worden opgegeven bij een CIM. 

1. Het informatiedomein van een CIM volgt strikt 1 begrippenkader, of 1 set van sterk sterk bij elkaar behorende begrippenkaders die een bepaalde onderverdeling kennen. De partij die verantwoordelijkheid is voor beide, is dezelfde partij, en deze bewaakt ook dat beide naadloos op elkaar aansluiten. 
2. Verwijzingen naar kennisbronnen die niet als begrippenkader zijn uitgewerkt, zijn toegestaan. In dit geval is het metagegeven 'kennisbron' bij een modelelement met een definitie gevuld. 

### Metamodel

### Lineage vanuit logisch gegevensmodel naar een conceptueel informatiemodel 

Gegevens gaan over eigenschappen van een object. Door semantische herleidbaarheid aan te brengen wordt aangegeven hoe (en in hoeverre) de gegevenswerkelijkheid en de gemodelleerde werkelijkheid in het begrippenkader en het conceptuele inforatiemodel met elkaar overeenkomen. 

Een gegevensmodel gaat over gegevens die er zijn, een informatiemodel gaat over informatie die we over de werkelijkheid nodig hebben. De definitie van een gegevensobject of een gegevenstype is daarom sterk gebaseerd de conceptualisatie van de informatie die beschreven is in het CIM. Het CIM definieert immers het objecttype, of het eigenschaptype, waarover het gegevenstype gaat. Dit is in een begrippenkader nog open en nog niet formeel vastgesteld. Daarom heeft het de sterke voorkeur om bij het aanbrengen van semantische herleidbaarheid in een logische gegevensmodel verwijzingen aan te brengen naar een modelelment in een CIM, en alleen te verwijzen naar een begrip als er geen CIM is. 

Semantische herleidbaarheid in een logisch gegevensmodel beschrijft op welke modelelementen uit een CIM een gegevenstype is gebaseerd. In het verlengde hiervan geldt dat de definitie van het gegevenstype weer op de begrippen is gebaseerd die daarin zijn aangegeven. 

#### Modelelementen uit een LGM waarvoor semantische verwijzingen mogelijk zijn 

In MIM 1.2 kunnen logische modelelementen gekoppeld aan een modelelement uit een conceptueel informatiemodel, met behulp van het metagegeven `mim:begrip`. 
De definitie daarvan luidt:  

In MIM 1.2 kunnen logische modelelementen gekoppeld aan een begrip met behulp van het metagegeven `mim:begrip`. 
De definitie daarvan luidt:  

| Modelelement | semantische verwijzing naar | kardinaliteit | spelregels, bij 1 modelelement van dit type hoort                     | 
| ------------ | --------------------------- | ------------- | --------------------------------------------------------------------- | 
| gegevensobjecttype   | objecttype of relatietype | 1..1 | precies 1, te weten het objecttype of het relatietype die onderwerp van gesprek is van het gegevensobjecttype                          |  
| gegevensobjecttype   | begrip              | 0..* | precies 1, te weten het begrip waar het primair om gaat (en waarvoor een objecttype in een CIM zou moeten zijn, indien er een CIM is         |  
| gegevenstype         | eigenschaptype                    | 0..* | ten minste 1, mits er een CIM is met daarin een passend eigenschaptype | 
| gegevenstype         | begrip                            | 0..* | ten minste 1, indien er geen CIM is maar wel een begrippenkader is met daarin een passend begrip | 

Merk op: 
- Een relatietype in een logisch gegevensmodel is een verwijzing naar de identificatie van het gegevensobject waarnaar verwezen wordt. Hiervoor is geen semantische verwijzing vereist naar een CIM of begrippenkader. Wel kan een definitie gegeven worden voor dit relatietype in het LGM.

_Interpretatie van de semantische verwijzing_

> “Verwijzing naar een conceptueel modelelement, vanuit een modelelement op het logische niveau, waarmee wordt aangegeven op welk begrip, of begrippen, het informatiemodelelement is gebaseerd. De verwijzing heeft de vorm van een term of een URI.”

> “Verwijzing naar een begrip, vanuit een modelelement op het logische niveau, waarmee wordt aangegeven op welk begrip, of begrippen, het informatiemodelelement is gebaseerd. De verwijzing heeft de vorm van een term of een URI.”

De formulering *is gebaseerd op* wijst op een meer vrije en mogelijk meervoudige interpretatie van de relatie tussen een logisch modelelement en een begrip.

_Indirecte semantische verwijzing_

Een gegevenstype kan 1 op 1 overgenomen zijn uit een ander logisch gegevensmodel. Het is mogelijk om daarnaar te verwijzen, en voor de semantische herleidbaarheid te stellen: zie aldaar. 

| Modelelement | indirecte semantische verwijzing naar | kardinaliteit | spelregels, bij 1 modelelement van dit type hoort                     | 
| ------------ | --------------------------- | ------------- | --------------------------------------------------------------------- | 
| gegevensobjecttype   | gegevensobjecttype uit ander LGM | 0..1 | als aangebracht, dan altijd tijd precies 1                        |  
| gegevenstype         | gegevenstype uit ander LGMe      | 0..1 | als aangebracht, dan altijd tijd precies 1                        | 


#### Lineage op model niveau 

_Optionele spelregels_ 

Deze kunnen worden opgegeven bij een model. 
1. De modeldidentificaties van de begrippenkaders of conceptuele informatiemodellen, en de namen ervan, waarnaar verwezen wordt vanuit dit CIM zijn de volgende.
2. De administratie of de gegevensuitwisseling waar dit model een uitdrukking van is heet als volgt:

### Lineage vanuit logisch gegevensmodel naar een begrip uit een begrippen model 

TODO. 

## Lineage vanuit fysiek datamodel
Dit onderdeel is buiten scope van MIM. Dit wordt momenteel in detail beschreven in de *Handreiking data lineage*.
