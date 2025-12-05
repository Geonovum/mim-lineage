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


## Lineage vanuit conceptueel informatiemodel naar een begrippenkader

De definitie van een modelelement in een CIM heeft daarom een zeer sterke relatie met de definitie van een begrip uit een begrippenkader. Een begrippenkader en een conceptueel informatiemodel beschrijven immers beiden een model van dezelfde werkelijkheid. De ene beschrijft begrippen waarmee we uitdrukking geven aan het beschrijven van die werkelijkeheid, de andere geeft de conceptualisatie aan van dezelfde werkelijkheid, door middel van objecttypen, eigenschaptypen, relatietypen enzovoorts. Het is daarom in principe zo dat de terminologie in een CIM overeenkomt met de voorkeurstermen van de gerelateerde begrippen, daar waar mogelijk, mede ook om geen onnodige (spraak) verschillen te krijgen. Dit is niet altijd mogelijk, maar dit is wel een streven. De spelregels in onderstaande tabel geven dit aan. 

### Modelelementen uit een CIM waarvoor semantische verwijzingen mogelijk zijn 

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

### Lineage op model niveau 

_Optionele spelregels_ 

Deze kunnen worden opgegeven bij een model. 

1. Het informatiedomein van een CIM volgt strikt 1 begrippenkader, of 1 set van sterk sterk bij elkaar behorende begrippenkaders die een bepaalde onderverdeling kennen. De partij die verantwoordelijkheid is voor beide, is dezelfde partij, en deze bewaakt ook dat beide naadloos op elkaar aansluiten.
2. De modeldidentificaties van de begrippenkaders, en de namen ervan, waarnaar verwezen wordt vanuit dit CIM zijn de volgende
3. Verwijzingen naar kennisbronnen die niet als begrippenkader zijn uitgewerkt, zijn toegestaan. In dit geval is het metagegeven 'kennisbron' bij een modelelement met een definitie gevuld. 
   

### Model


## Lineage vanuit logisch gegevensmodel naar een conceptueel informatiemodel 

Gegevens gaan over eigenschappen van een object. Door semantische herleidbaarheid aan te brengen wordt aangegeven hoe (en in hoeverre) de gegevenswerkelijkheid en de gemodelleerde werkelijkheid in het begrippenkader en het conceptuele inforatiemodel met elkaar overeenkomen. 

Een gegevensmodel gaat over gegevens die er zijn, een informatiemodel gaat over informatie die we over de werkelijkheid nodig hebben. De definitie van een gegevensobject of een gegevenstype is daarom sterk gebaseerd de conceptualisatie van de informatie die beschreven is in het CIM. Het CIM definieert immers het objecttype, of het eigenschaptype, waarover het gegevenstype gaat. Dit is in een begrippenkader nog open en nog niet formeel vastgesteld. Daarom heeft het de sterke voorkeur om bij het aanbrengen van semantische herleidbaarheid in een logische gegevensmodel verwijzingen aan te brengen naar een modelelment in een CIM, en alleen te verwijzen naar een begrip als er geen CIM is. 

Semantische herleidbaarheid in een logisch gegevensmodel beschrijft op welke modelelementen uit een CIM een gegevenstype is gebaseerd. In het verlengde hiervan geldt dat de definitie van het gegevenstype weer op de begrippen is gebaseerd die daarin zijn aangegeven. 

### Modelelementen uit een LGM waarvoor semantische verwijzingen mogelijk zijn 

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


### Lineage op model niveau 

_Optionele spelregels_ 

Deze kunnen worden opgegeven bij een model. 
1. De modeldidentificaties van de begrippenkaders of conceptuele informatiemodellen, en de namen ervan, waarnaar verwezen wordt vanuit dit CIM zijn de volgende.
2. De administratie of de gegevensuitwisseling waar dit model een uitdrukking van is heet als volgt:

### Lineage vanuit logisch gegevensmodel naar een begrip uit een begrippen model 


## Lineage vanuit fysiek datamodel
Dit onderdeel is buiten scope van MIM. Dit wordt momenteel in detail beschreven in de *Handreiking data lineage*.

### Model
