# Lineagemodel

Dit hoofdstuk beschrijft een specificatie van semantische herleidbaarheid in een CIM of LGM, met behulp van diagrammen en specificaties. 

In het vorige hoofdstuk is een een abstract model uitgewerkt. Dit abstract model beschrijft concepten die voor meerdere modeltypen en modelelelementen van toepassing zijn. In dit hoofdstuk is dit verder uitgewerkt naar hoe dit er precies uitziet in een CIM of LGM, zoals een modelleur deze maakt. De uitwerking bestaat uit specifiek te beschrijven metagegevens, per type modelelement van een bepaald type model.

## Wijze van toepassing
Het toepassen van deze MIM-module verhoogd de begrijpelijkheid van een model en maakt consistentie met bovenliggende semantiek inzichtelijk. Dit kan er ook toe leiden dat gegevensdefinities verbeterd kunnen worden. Deze modele is echter niet verplicht in MIM, omdat er een bepaalde inspanning nodig is om deze toe te passen. Om aan te geven of en hoe deze module is toegepast in een model wordt het volgende beschreven: 
- ALS het model geen gebruik maakt van deze MIM module, dan hoeft dit niet expliciet te worden aangegeven.
   - Het is toegestaan om aan te geven: MIM-SH = Nee
- ALS het model wel gebruik maakt van deze MIM module, dan:
   - wordt dit aangegeven bij de metagegevens op model niveau: MIM-SH = Ja
   - worden de spelregels gevolgd die in deze module zijn aangegeven (deze volgen uit MIM-SH = Ja) 
   - is er de mogelijkheid om aan te geven welke _optionele spelregels_ er verder nog toegepast zijn in het model om de kwaliteit van de specificatie verder te verhogen. Deze lezer of gebruiker kan hier van op vertrouwen. 

## Modelelementen met lineage

Voor de volgende modelelementen is semantische herleidbaarheid uitgewerkt.

CIM modelelementen:
   - objecttype
   - attribuuttype (attribueerde eigenschap)
   - relatietype
   - relatie met eigenschappen

LGM modelelementen:
   - gegevensobjecttype
   - gegevenstype
   - TODO, eventueel: relatietype tussen twee gegevensobjecttypen

## Uitgangspunten en ontwerpbeslissingen

**Elk modelelement kent een eigen definitie**

In MIM is een definitie voor veel modelelementen een verplicht metagegeven.  In principe zijn definities op elk beschouwingsniveau ook zelfstandig voor specifiek dat beschouwingsniveau, ook al komen ze tekstueel overeen. Wanneer de definitie van een modelelement exact gelijk is aan die van een modelelement of begrip waarmee een lineage-relatie bestaat, kan dit als redundant worden ervaren. Het verdient echter de voorkeur om deze definities expliciet te specificeren, zodat het model ook zelfstandig goed te begrijpen blijft. In een eigen beheer omgeving zou de gegevensdefinitie leeg gelaten kunnen worden waarmee bedoeld wordt dat deze rechtstreeks van het gerelateerde begrip overgenomen kan worden, maar bij de publicatie van het model hoort er altijd een gegevensdefinitie te zijn die te lezen is door gebruikers.

**Elk gegevenstype heeft een gegevensdefinitie**

Elk gegevenstype verdiend een definitie. Ook als het gegeventype semantisch niet relevant is is het zinvol om te begrijpen wat ermee bedoeld wordt. Daarom is de definitie hiervan verplicht. 

**Lineage naar wet- en regelgeving en andere kennisbronnen mag rechtstreeks worden gelegd**

Een van de doelstellingen van lineage is dat van een gegeven kan worden vastgesteld welke wet- en regelgeving van toepassing is. Op die manier kan uiteindelijk ook worden nagegaan of aan de gestelde eisen wordt voldaan. 

Er zullen organisaties zijn die kiezen om deze lineage in een begrippenkader, zoals o.a. bedoeld in de NL-SBB standaard, op te nemen. Alsmede om vervolgens vanuit een CIM of LGM naar begrippen naar dit begrippenkader te verwijzen. Deze modellen zijn echter niet altijd gemaakt. Wet- en regelgeving en (openbaar) uitvoeringsbeleid is echter wel altijd gepubliceerd, we noemen dit kennisbronnen. Naar deze kennisbronnen kan daarom ook vanuit MIM modellen verwezen worden, via een kennisbron verwijzing. 

Omdat de NL-SBB ook kennisbron verwijzingen kent maakt MIM deze manier van verwijzen ook beschikbaar vanuit MIM. Er zijn ook kennisbronnen die zelf specificeren hoe er naar hen verwezen kan of moet worden. Uitgangspunt is dat dit soort aspecten meegenomen worden bij de NL-SBB en MIM hetzelfde mechanisme ook mogelijk maakt. 

**Semantische relaties tussen begrippen worden niet uitgewerkt in MIM**

Dit wordt momenteel in detail beschreven in o.a. de *NL-SBB standaard*. Horizontale lineage tussen begrippen uit verschillende begrippenkaders betreft de zogenoemde harmonisatierelaties uit de NL-SBB en wordt [aldaar](https://docs.geostandaarden.nl/nl-sbb/nl-sbb/#harmonisatiesrelaties) beschreven. 

**Lineage van technische implementatiemodellen naar LGM worden niet uitgewerkt in MIM**

Een logisch gegevensmodel kan worden uitgewerkt in verschillende technische schema's, naar gelang welke gebruikers welke serialisatie willen ontvangen of welke applicaties of databases worden ontwikkelt. Hetzelfde logische model kan in vele technische verschijningsvormen zijn uitgewerkt, waarmee het ook eenvoudig wordt om deze eenduiding naar elkaar te vertalen. Lineage is in principe altijd van 'onder' naar 'boven' dus de lineage van technisch naar logisch hoort bij de technische uitwerking. 

Dit wordt momenteel in detail beschreven in de *Handreiking data lineage*.

Deze lineage betreft vaak een mapping en/of een vertaalspeficiatie tussen technisch en logisch. Deze *kan* vanwege pragmatische overwegingen eventueel opgenomen worden *bij* een LGM, maar zit strikt genomen **niet** *in* het LGM. Wellicht dat deze mapping generiek kan worden gespecificeerd zonder afhankelijkheden met de diverse implementatie technieken en als zodanig een plek in MIM kan krijgen, maar dit is nu niet zo.

## Lineage vanuit CIM naar begrippenkader

In deze paragraaf wordt aangegeven hoe een begrippenkader met begrippen gebruikt kan worden om semantische herleidbaarheid aan te brengen in een CIM. 
 
De definitie van een modelelement in een CIM heeft een zeer sterke relatie met de definitie van een begrip uit een begrippenkader. Een begrippenkader en een conceptueel informatiemodel beschrijven immers beiden een model van dezelfde werkelijkheid. De ene beschrijft begrippen waarmee we uitdrukking geven aan het beschrijven van die werkelijkeheid, de andere geeft de conceptualisatie aan van dezelfde werkelijkheid, door middel van objecttypen, eigenschaptypen, relatietypen enzovoorts. Het is daarom in principe zo dat de terminologie in een CIM overeenkomt met de voorkeurstermen van de gerelateerde begrippen, daar waar mogelijk, mede ook om geen onnodige (spraak) verschillen te krijgen. Dit is niet altijd mogelijk, maar dit is wel een streven. De spelregels in onderstaande tabel geven dit aan. 

**Lineage op model niveau**

In een CIM kunnen modelelementen voorkomen die semantische verwijzingen hebben naar begrippen uit verschillende begrippenkaders. Hierover kan extra informatie worden toegevoegd in het model, zodat helder is welke dit zijn. 

Per model waarnaar wordt verwezen kan worden aangegeven. 

| Metagegeven  | semantische verwijzing naar | kardinaliteit  | voorbeeld | 
| ------------ | --------------------------- | ------------- | -------------- | 
| model type          | model                       | 1..1  | begrippenkader | 
| model identificatie | begrippenkader model        | 1..1  | ...                  | 
| model naam          | begrippenkader model        | 1..1  | Natuurlijke personen | 
| model versie        | begrippenkader modelversie  | 1..1  |  1.0.0 | 

_Optionele spelregels_ 

1. Model verwijzingen worden opgenomen bij dit CIM.
2. Het informatiedomein van een CIM volgt strikt 1 begrippenkader, of 1 set van sterk sterk bij elkaar behorende begrippenkaders die een bepaalde onderverdeling kennen. De partij die verantwoordelijkheid is voor beide, is dezelfde partij, en deze bewaakt ook dat beide naadloos op elkaar aansluiten. 
3. Verwijzingen naar kennisbronnen die niet als begrippenkader zijn uitgewerkt, zijn toegestaan. In dit geval is het metagegeven 'kennisbron' bij een modelelement met een definitie gevuld. 

_TODO: 3 is hier nog niet uitgewerkt._

**Modelelementen uit een CIM waarvoor semantische verwijzingen mogelijk zijn** 

Dit zijn in principe alle modelelementen die een definitie kunnen hebben en ten minste alle modelelementen die een definitie hebben (altijd behoren te hebben). 

| Modelelement | semantische verwijzing naar | kardinaliteit | spelregels, bij 1 modelelement van dit type hoort: ...                | 
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

**Metamodel**
*(Nog uit te werken in dit document.)*
TODO: visueel diagram. 

## Lineage vanuit LGM naar begrippenkader 
*(Nog uit te werken in dit document.)*

**Modelelementen uit LGM met semantische verwijzingen naar begrippenkader**

| Modelelement | semantische verwijzing naar | kardinaliteit | spelregels, bij 1 modelelement van dit type hoort: ...                | 
| ------------ | --------------------------- | ------------- | --------------------------------------------------------------------- | 
| gegevensobjecttype   | begrip              | 0..* | precies 1, te weten het begrip waar het primair om gaat (en waarvoor een objecttype in een CIM zou moeten zijn, indien er een CIM is         |  
| gegevenstype         | begrip                            | 0..* | ten minste 1, indien er geen CIM is maar wel een begrippenkader is met daarin een passend begrip | 

Merk op:
- Het is ook mogelijk om naar een CIM modelelement te verwijzen, zoals bedoeld in de volgende paragraaf (hier niet uitgewerkt)

_Interpretatie van de semantische verwijzing_

> “Verwijzing naar een begrip, vanuit een modelelement op het logische niveau, waarmee wordt aangegeven op welk begrip, of begrippen, het informatiemodelelement is gebaseerd. De verwijzing heeft de vorm van een term of een URI.”

De formulering *is gebaseerd op* wijst op een meer vrije en mogelijk meervoudige interpretatie van de relatie tussen een logisch modelelement en een begrip.

_TODO: hoe precies verwijzen naar een begrip. Dit is analoog aan MIM 1.2, wellicht nog met een extra uitbreiding of dit wel of niet exact is._


## Lineage vanuit LGM naar CIM

Gegevens gaan over eigenschappen van een object. Door semantische herleidbaarheid aan te brengen wordt aangegeven hoe (en in hoeverre) de gegevenswerkelijkheid en de gemodelleerde werkelijkheid in het begrippenkader en het conceptuele inforatiemodel met elkaar overeenkomen. 

Een gegevensmodel gaat over gegevens die er zijn, een informatiemodel gaat over informatie die we over de werkelijkheid nodig hebben. De definitie van een gegevensobject of een gegevenstype is daarom sterk gebaseerd de conceptualisatie van de informatie die beschreven is in het CIM. Het CIM definieert immers het objecttype, of het eigenschaptype, waarover het gegevenstype gaat. Dit is in een begrippenkader nog open en nog niet formeel vastgesteld. Daarom heeft het de sterke voorkeur om bij het aanbrengen van semantische herleidbaarheid in een logische gegevensmodel verwijzingen aan te brengen naar een modelelment in een CIM, en alleen te verwijzen naar een begrip als er geen CIM is. 

Semantische herleidbaarheid in een logisch gegevensmodel beschrijft op welke modelelementen uit een CIM een gegevenstype is gebaseerd. In het verlengde hiervan geldt dat de definitie van het gegevenstype weer op de begrippen is gebaseerd die daarin zijn aangegeven. 

**Lineage op model niveau**

In een LGM kunnen modelelementen voorkomen die semantische verwijzingen hebben naar CIM modelelementen uit verschillende CIM's. Hierover kan extra informatie worden toegevoegd in het model. 

Per model waarnaar wordt verwezen kan worden aangegeven: 

| Metagegeven  | semantische verwijzing naar  | kardinaliteit  | voorbeeld | 
| ------------ | ---------------------------  | ------------- | -------------- | 
| model type          | model                 | 1..1   | CIM, LGM, begrippenkader
| model identificatie | zie type, model       | 1..1   | ...                  | 
| model naam          | zie type, model       | 1..1   | Natuurlijke personen | 
| model versie        | zie type, modelversie | 1..1   |  1.0.0 | 
| model URI           | locatie van model     | 0..1   | http://mijnorganisatie/mijnmodel 

_Optionele spelregels_ 

Deze kunnen worden opgegeven bij een model en geven aan welke verwijzen op modelniveau opgenomen mogen worden in het model:  
1. Er mag worden verwezen naar een CIM 
2. Er mag (rechtstreeks) worden verwezen naar een begrippenkader 
3. Als er een CIM is, dan wordt er naar het CIM verwezen en niet rechtstreeks naar het begrippenkader
4. Er mag worden verwezen naar een LGM via indirecte semantische verwijzingen

**Modelelementen uit LGM met semantische verwijzingen naar CIM**

| Modelelement | semantische verwijzing naar | kardinaliteit | spelregels, bij 1 modelelement van dit type hoort: ...                | 
| ------------ | --------------------------- | ------------- | --------------------------------------------------------------------- | 
| gegevensobjecttype   | objecttype of relatietype | 1..1 | precies 1 objecttype of het relatietype, te weten degene die onderwerp van gesprek is van het gegevensobjecttype  |  
| gegevenstype         | eigenschaptype                    | 0..* | ten minste 1, mits er een CIM is met daarin een passend eigenschaptype | 

Merk op: 
- Het is ook mogelijk om naar een begrip te verwijzen, zoals bedoeld in de vorige paragraaf (hier niet uitgewerkt)
- Een relatietype in een logisch gegevensmodel is een verwijzing naar de identificatie van het gegevensobject waarnaar verwezen wordt. Hiervoor is geen semantische verwijzing vereist naar een CIM of begrippenkader. Wel kan een definitie gegeven worden voor dit relatietype in het LGM.

_Interpretatie van de semantische verwijzing_

> “Verwijzing naar een conceptueel modelelement, vanuit een modelelement op het logische niveau, waarmee wordt aangegeven op welk begrip, of begrippen, het informatiemodelelement is gebaseerd. De verwijzing heeft de vorm van een term of een URI.”

De formulering *is gebaseerd op* wijst op een meer vrije en mogelijk meervoudige interpretatie van de relatie tussen een logisch modelelement en een begrip.

### Specificatie voor gegevensobjecttype

| Metagegeven | Beschrijving      | 
| ------------ | ------------------------------------------------------ |
| onderwerp van gesprek | aanduiding welk objecttype uit een CIM het onderwerp van gesprek is van het gegevensobjecttype |

De volgende metagegevens worden gespecificeerd bij een semantische verwijzing naar een objecttype uit een CIM:

| Metagegeven  | beschrijving      | kardinaliteit | datatype | voorbeeld | 
| ------------ | ------------------------------------------------------ | -------------- | -------------- | -------------- | 
| modelelement identificatie | zie MIM algemeen | 0..1 | zie MIM algemeen | ... | 
| modelelement naam | zie MIM algemeen | 0..1 | zie MIM algemeen | ... | 
| model naam | zie MIM algemeen | 1..1 | zie MIM algemeen | ... | 

*In diagram vorm:*
**TODO: Frans, diagram SH Gegevensobjecttype verticaal naar CIM** 

Regels: 
- ofwel de modelelement identificatie ofwel de modelelement naam is opgenomen, of beide
- de model naam is opgenomen bij Lineage op model niveau

Bij het aangeven van de semantische herleidbaarheid van een gegevenstype naar de bijbehorende semantiek kan uit analyse blijken dat de gegevensdefinitie van een gegevenstype volledig afgedekt kan worden door modelelementen in een CIM en/of begrippenkader. Dit is de gewenste situatie. Het kan echter ook zo zijn dat het niet het wat anders is dan gewenst. De mate van aanwijsbaarheid is dan maar deels mogelijk of zelfs geheel niet mogelijk. 

### Specificatie voor gegevenstype

De manier waarop semantische herleidbaarheid is gespecificeerd wordt eerst aangegeven. 

| Metagegeven | beschrijving      | datatype | voorbeeld | 
| ------------ | ------------------------------------------------------ | -------------- | -------------- | 
| semantische herleidbaarheid | zie H4, semantische herleidbaarheid | enumeratie | zie enumeratiewaarden | 

De volgende enumeratiewaarden zijn mogelijk: 

| waarde | beschrijving      | datatype | voorbeeld | 
| ------------------ | ------------------------------------------------------ | -------------- | -------------- | 
| "niet relevant" | aanduiding dat een modelelement semantisch niet relevant is en de semantische herleiding niet uitgewerkt hoeft te worden | CharacterString | "niet relevant" | 
| "niet herleidbaar" | aanduiding dat voor een semantisch relevant modelelement de gehele semantische herleiding ontbreekt en dus niet herleidbaar is | CharacterString | "niet herleidbaar" |
| "herleidbaar"      | aanduiding dat voor een semantisch relevant modelelement de semantische herleiding is uitgewerkt, voor zover mogelijk | 
| "horizontale verwijzing" | aanduiding dat voor een semantisch relevant modelelement de semantische herleiding is uitgewerkt via een horizontale verwijzing | 

Regel: De aanduiding van de van verwijsbaarheid is een van deze waarden. 

Regel: Het is niet toegestaan om een andere aanduiding te kiezen die niet in MIM gedefinieerd is. Het is wel toegestaan om in een eigen toepassingsprofiel een 'nadere aanduiding' te specificeren, in aanvulling op de MIM aanduiding. 

**Horizontale semantische herleidbaarheid**

Een gegevenstype kan 1 op 1 overgenomen zijn uit een ander logisch gegevensmodel. Het is mogelijk om daarnaar te verwijzen, en voor de semantische herleidbaarheid te stellen: zie aldaar. 

| Modelelement | indirecte semantische verwijzing naar | kardinaliteit | spelregels, bij 1 modelelement van dit type hoort                     | 
| ------------ | --------------------------- | ------------- | --------------------------------------------------------------------- | 
| gegevensobjecttype   | gegevensobjecttype uit ander LGM | 0..1 | als aangebracht, dan altijd tijd precies 1                        |  
| gegevenstype         | gegevenstype uit ander LGMe      | 0..1 | als aangebracht, dan altijd tijd precies 1                        | 

**Metamodel in diagram vorm:**
**TODO: Frans, diagram SH Gegevenstype horizontaal naar gegevenstype in ander LGM** 


**Verticale semantische herleidbaarheid**

Een gegevenstype kan een gegevensdefinitie hebben die gebaseerd is op bovenliggende definities. 

Regel: indien de semantische herleidbaarheid 'herleidbaar' is dan worden de metagegevens 'semantische verwijzingen' en 'ontbrekende verwijzingen' ook gespecificeerd. 

Voor elk gegevenstype kunnen meerdere semantische verwijzingen worden opgenomen. 

| Metagegeven  | beschrijving      | kardinaliteit per gegevenstype | 
| ------------ | ------------------------------------------------------ | -------------- | 
| semantische verwijzing CIM | aanduiding van het modelelement in het CIM | 0..* |

De volgende metagegevens worden gespecificeerd bij elke _semantische verwijzing_ naar een CIM: 

| Metagegeven  | beschrijving      | kardinaliteit | datatype | 
| ------------ | ------------------------------------------------------ | -------------- | -------------- | 
| modelelement identificatie CIM | zie MIM algemeen | 0..1 | zie MIM algemeen 
| modelelement naam | zie MIM algemeen | 0..1 | zie MIM algemeen 
| model identificatie | zie MIM algemeen | 1..1 | zie MIM algemeen  
| is exact     | aanduiding dat de semantische verwijzing wel of niet exact is, zoals bedoeld bij _exacte semantische verwijzing_ | 1..1 | boolean | 1 (ja, is exact) |
| lexicaal pad | zie H4 | 0..1 | zie specificatie lexicaal pad verderop

**Metamodel in diagram vorm:**
**TODO: Frans, diagram SH Gegevenstype horizontaal naar gegevenstype in ander LGM** 

Regels: 
- ofwel de modelelement identificatie ofwel de modelelement naam is opgenomen, of beide
- de model naam is opgenomen bij Lineage op model niveau

Voor elk gegevenstype kan aangegeven worden of er verwijzingen ontbreken, oftewel dat deze niet compleet zijn. 

| Metagegeven  | beschrijving      | kardinaliteit | datatype | voorbeeld | 
| ------------ | ------------------------------------------------------ | -------------- | -------------- | -------------- | 
| onbrekende verwijzingen | aanduiding dat er in de semantische herleiding 1 of meerdere semantische verwijzingen ontbreken, zoals bedoeld bij _complete semantische herleiding _| 1..1 | boolean | 1 (ja, er ontbreken er) |

Indien er ontbrekende verwijzingen zijn of indien er verwijzingen zijn die niet exact zijn, dan kan er een verklaring van verschil worden opgenomen. De modelleur heeft hiertoe eerst de definities van de bovenliggende CIM modelelementen en/of begrippen bestudeerd.

### Verschillen met bovenliggende definities

Er wordt onderscheidt gemaakt tussen 2 soorten verschillen: 
- verklaring van verschil, semantisch niet equivalent met bovenliggende definities
- toelichting verwoordingsverschil, semantisch equivalent met bovenliggende definities

| Metagegeven  | beschrijving      | kardinaliteit | datatype  | voorbeeld | 
| ------------ | ----------------  | ------------- | --------- | -------------- | 
| verklaring van verschil | zie H4 | 0..1          | tekst     | omissie in CIM  |

Regel: de verklaring van verschil is in principe vrije tekst. Deze legt zo goed als mogelijk uit hoe de gegevensdefinitie verschilt van bestaande definities uit een CIM of begrippenkader. De verklaring is bedoeld voor de lezer van het model en niet voor de modelleur. Neem dus geen procesopmerkingen of oorzaken op, maar hou het bij het inhoudelijke verschil zelf. 

Het is hierbij toegestaan om gebruik te maken van gestandaardiseerde teksten. Hierbij kan gebruik gemaakt worden van de volgende: 

| Verklaring van verschil | Toelichting | 
| ----------------- | --------------------------- |
| omissie in CIM            | Er ontbreekt (vermoedelijk) een modelelement in het CIM. | 
| omissie in begrippenkader | Er ontbreekt (vermoedelijk) een begrip in het begrippenkader. |  
| niet relevant             | De betekenis is semantisch niet relevant op MIM niveau 1 of 2. Het gegeven is bijvoorbeeld geheel technisch van aard, of er is sprake van een modelmatige hulpconstructie. |  

_Optionele spelregels:_

1. Indien semantische herleiding bestaat uit 1 semantische verwijzing en deze exact is dan wordt de afspraak gehanteerd dat de definitie van het CIM modelelement 1 op 1 kan worden overgenomen naar de gegevensdefinitie van het gegevenstype of gegevensobjecttype.
2. De verklaring van verschil is verplicht indien de semantisch herleiding wel herleidbaar is maar ofwel niet compleet is ofwel niet exact is. Het is in dit geval van belang om het verschil goed te duiden aan gebruikers. 

--

Indien de verwoording van de gegevensdefinitie afwijkt van de verwoording van de bovenliggende definities, maar de betekenis ervan gelijk is (semantisch equivalent) dan kan dit ook worden aangegeven: 

| Metagegeven  | beschrijving      | kardinaliteit | datatype | voorbeeld |
| ------------ | -------------- | -------------- | -------------- | ------------------------------------------------------ | 
| toelichting verwoordingsverschil | zie H4 | 0..1 | tekst | Er is een oude term gebruikt die inmiddels is vervangen door een nieuwe term, maar de strekking en de betekenis ervan is hetzelfde.  |

### Lexicaal pad

TODO: keuzes maken, zie issue 4. 

| Modelelement | semantische verwijzing naar     | kardinaliteit | spelregels                     | 
| ------------ | ------------------------------- | ------------- | ----------------------------------------------- | 
| lexicaal pad | objecttypen en/of relatierollen | 0..*          |  het pad tussen het startpunt en het eindpunt     | 

Bij de geboorteplaatscode in het voorbeeld hoort de volgende specificatie voor het lexicale pad: 
- modelelement startpunt: objecttype Natuurlijk persoon 
- modelelement eindpunt: eigenschaptype code
- lexicaal pad: geboorteplaats (de rol), Woonplaats (het objecttype)

Het gehele lexicale pad voor het gegevenstype geboorteplaatscode is dan: Natuurlijk persoon, geboorteplaats, Woonplaats, code. 

Als een model geen rollen kent, dan wordt als rol de naam van het objecttype waar het relatietype naar verwijst gekozen. Het lexicale pad is dan: woonplaats, Woonplaats. Dit komt wellicht redundant over, maar dit zorgt ervoor dat er geen "gaten" in het pad ontstaan. 

Er is ook gekozen om niet de relatienaam te gebruiken, omdat de rol over het algemeen stabieler is, en korter. Het is dan wel nodig dat de rol gegarandeerd uniek is in het geval er meerdere relatietypen liggen tussen dezelfde objecttypen. Wanneer tussen het objecttype Natuurlijk persoon en Woonplaats dus twee relatietypen zijn gemodelleerd, zoals 'woont in' en 'is geboren in' dan is bij elk van deze relatietypen ook een rol nodig, zoals 'woonplaats' en 'geboorteplaats'. 

_Optionele spelregels:_

1. Het model hanteert een eigen notatiewijze voor het lexicale pad, te weten de volgende: ... 
2. Start- en eindpunt hoeven niet te worden opgegeven door de modelleur en kunnen terug gevonden worden bij de overige specificaties van semantische herleidbaarheid.
3. Het lexicale pad wordt gespecificeerd als pad met begin- en eindpunt. Strikt genomen horen het objecttype dat het onderwerp van gesprek is van het gegevensobjecttype (het beginpunt) en het eigenschaptype waarnaar verwezen wordt (het eindpunt) ook tot het pad (inclusief). Tegelijkertijd zijn deze al gespecificeerd als onderdeel van semantische herleiding via respectievelijk het onderwerp van gesprek en het de semantische verwijzing. Deze spelregel geeft aan dat deze expliciet (nogmaals) gespecificeerd moeten worden.  

Ad 3. 
| Metagegeven  | beschrijving      | kardinaliteit | spelregels | 
| ------------ | -------------- | -------------- | ------------------------------------------------------ | 
| lexicaal pad start  | CIM objecttype die het onderwerp van gesprek is van het gegevensobject waartoe het gegevenstype behoort | 0..1 | als aangebracht, dan altijd tijd precies 1                 |  
| lexicaal pad start eind   | eigenschaptype waar het gegevenstype over gaat                                                      | 0..1 | als aangebracht, dan altijd tijd precies 1 en gelijk aan                  | 

## Mogelijke openstaande punten en teksten om nog een plek te geven: 

**Geannoteerde definities**
De meeste modelelementen hebben verplicht een definitie: een beschrijving van de betekenis van dat modelelement. 
In zo’n beschrijving kunnen een of meerdere gebruikte termen expliciet gekoppeld zijn aan een begrip. 
Dit wordt een *geannoteerde definitie* genoemd.  

Bij een geannoteerde definitie kunnen zowel de afzonderlijke termen uit de definitie als het modelelement in zijn geheel een lineage-relatie hebben met een begrip.  

Zowel conceptuele informatiemodellen als logische gegevensmodellen kunnen geannoteerde definities bevatten.O: visueel diagram. 

