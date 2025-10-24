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

#### Redundantie van definities
In MIM is een definitie voor veel modelelementen een verplicht metagegeven. 
Wanneer de definitie van een modelelement exact gelijk is aan die van een modelelement of begrip waarmee een lineage-relatie bestaat, kan dit als redundant worden ervaren.  

Het verdient echter de voorkeur om deze definities toch te herhalen, zodat het model ook zelfstandig goed te begrijpen blijft.

### Aanpak: per koppelvlak tussen niveaus een model maken
*(Nog uit te werken in dit document.)*


## Lineage vanuit conceptueel informatiemodel naar een begrippenkader
De relatie tussen een conceptueel modelelement en een begrip moet strikt worden opgevat. 
Het gaat immers om een formele modellering van (informatie over) de werkelijkheid.

Een relatie tussen een conceptueel modelelement en een begrip drukt uit dat de definities overeenkomen, of in ieder geval grotendeels overeenkomen.

### Model


## Lineage vanuit logisch gegevensmodel
In MIM 1.2 worden logische modelelementen gekoppeld aan een begrip met behulp van het metagegeven `mim:begrip`. 
De definitie daarvan luidt:  

> “Verwijzing naar een begrip, vanuit een modelelement, waarmee wordt aangegeven op welk begrip, of begrippen, het informatiemodelelement is gebaseerd. De verwijzing heeft de vorm van een term of een URI.”  

De formulering *is gebaseerd op* wijst op een meer vrije en mogelijk meervoudige interpretatie van de relatie tussen een logisch modelelement en een begrip.

### Model


## Lineage vanuit fysiek datamodel
Dit onderdeel wordt momenteel in detail beschreven in de *Handreiking data lineage*.

### Model
