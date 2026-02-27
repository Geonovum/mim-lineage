# Semantische herleidbaarheid

In dit hoofdstuk maakt u kennis met het onderwerp. 

## Introductie 

Semantische herleidbaarheid gaat over het aanbrengen van verticale lineage met betrekking tot definities van modelelementen, waarbij deze herleiding uiteindelijk uitkomt bij de kennis die beschreven is in kennisbronnen (of kennis in de hoofden van materiedeskundigen). 

Je kan semantische herleidbaarheid ook zien als het aanbrengen van afkomstrelaties, of is gebaseerd op relaties, tussen modelelementen van modellen uit de verschillende beschouwingsniveaus, zoals o.a. MIM deze onderkent. Denk hierbij aan: 
- een begrippenmodel van een begrippenkader, ook wel een semantisch begrippen model genoemd, waarnaar verwezen wordt vanuit: 
- een conceptuele informatiemodel van een bepaald informatiedomein, waarnaar verwezen wordt vanuit: 
- een logisch gegevensmodel van een administratie of een gegevensuitwisseling of een gegevensproduct, waarnaar verwezen wordt vanuit: 
- een fysieke datamodel of technisch schema

Het doel van semantische herleidbaarheid is hierbij om aan te geven hoe definities van modelelementen in informatie- en gegevensmodellen (MIM-2 en MIM-3) zich verhouden tot bovenliggende semantiek, in het bijzonder definities van begrippen uit begrippenkaders (MIM-1). 

Hierbij wordt in de kern vooral gekeken naar de tekstuele verwoording van de definities uit de verschillende modellen die voorhanden zijn. 

Uitgangspunt is dan ook dat elk modelelelement uit een (MIM) model een eigen definitie kent. Deze definitie staat op zichzelf en is zodanig opgesteld dat deze past bij het beschouwingsniveau dat uitgewerkt is in het betreffende model. 

Semantische herleidbaarheid is hierop een _aanvullende specificatie_, die de modelelementen en definities uit de verschillende modellen met elkaar verbindt. 

### Eenvoudig voorbeeld

Neem bij voorbeeld een attribute '**bsn**' in een logisch gegevensmodel met als definitie: de identificatie van een geregistreerd persoon. 

In dit voorbeeld is de bijbehorende semantische herleiding als volgt: 
- **bsn** is een _gegevenstype_ dat onderdeel uitmaakt van het _gegevensobjecttype GeregistreerdNP_ in een logisch gegevensmodel;
- voorgaande is gebaseerd op modelelementen die in een conceptueel informatiemodel zijn uitgewerkt, te weten een _objecttype Ingeschrevene_, met een _eigenschaptype burgerservicenummer_, waarbij de Ingeschrevene een _specialisatie is van  objecttype Natuurlijk persoon_ (niet elke natuurlijk persoon is een ingeschrevene);
- voorgaande is gebaseerd op begrippen zoals: _begrip natuurlijk persoon_, een _begrip ingeschrevene_, en een _begrip burgerservicenummer_;
- deze begrippen zelf kunnen weer gebaseerd zijn op gepubliceerde brondocumenten, zoals in dit voorbeeld _het Burgerlijk Wetboek_ en de _Wet algemene bepalingen burgerservicenummer_.

Opmerking: met dit voorbeeld wordt niet bedoeld dat er altijd sprake is of moet zijn van wet- en regelgeving. Er zijn vele domeinen waarbij dit niet of minder van belang is. 

![Het BSN voorbeeld in een diagram](media/BSN_voorbeeld.png "Het BSN voorbeeld in een diagram")

## Verticale lineage in en tussen de MIM-beschouwingsniveaus

De in het voorbeeld beschreven samenhang noemen we ook wel verticale lineage. Dit betreft afkomstrelaties tussen de definities van modelelementen in de verschillende modellen. 

Verticaal refereert hierbij naar de verbanden tussen de beschouwingsniveaus, zoals hier beschreven in MIM (MIM v1.2 paragraaf 1.6). 
Omdat dit aparte lagen zijn is het van belang om de relatie tussen de lagen te kunnen beschrijven op het niveau van de individuele informatie-elementen. Er onstaat hiermee een systematiek van 'voortbouwende en uitbreidende' specificatie waarbij de afkomstrelaties traceerbaar en bruikbaar zijn van begrips- tot dataniveau, of eigenlijk van dataniveau terug naar begripsniveau. 

Er zijn verschillende beschouwingsniveaus om kennis en gegevens te modelleren (en andere concerns, die hier niet benoemd zijn). Bij het specificeren van semantische herleidbaarheid wordt hierbij veelvuldig gebruik gemaakt van verwijzingen tussen modelelementen uit verschillende beschouwingsniveaus. De volgende verbanden worden hierbij als binnen scope gezien. 

![Semantische herleidbaarheid in een diagram](media/MIM-lineage_informatie-architectuur.png "In een diagram")

Merk op dat verbanden meestal verticaal worden aangebracht, maar soms ook horizontaal. 

* **Verticale lineage** ontstaat door het leggen van relaties tussen modelelementen van verschillende niveaus, of tussen een modelelement en een begrip uit een begrippenkader.  
* **Horizontale lineage** ontstaat door het leggen van relaties tussen modelelementen op hetzelfde niveau, maar afkomstig uit verschillende modellen.

Dit diagram in tekstvorm is weergegeven in de volgende tabel: 

| MIM niveau    | Lineage                                     | Uitwerking te vinden in | 
| ------------- | ------------------------------------------- | --------------------------- |
| 2 naar ...    | vanuit CIM naar kennisbronnen               | In scope van MIM, maar volgt de werkwijze zoals bij 'van 1 naar ...' |
| 2 naar 1      | vanuit CIM naar een begrippenkader          | In scope, in deze module van MIM. |
| 3 naar 2      | vanuit LGM naar een CIM                     | In scope, in deze module van MIM. |
| 3 naar 1      | vanuit LGM naar een begrippenkader          | In scope, in deze module van MIM. |
| 3 naar 3      | vanuit LGM naar een ander LGM               | In scope, in deze module van MIM, zie verderop bij semantische gelijkstelling |
| 3 naar ...    | vanuit LGM naar kennisbronnen               | In scope van MIM, maar volgt de werkwijze zoals bij 'van 1 naar ...' . |

Merk op dat er verticale en horizontale lineage wordt onderscheiden. Zo is van 3 naar 3 een voorbeeld van horizontale lineage, of beter gezegd verticale lineage waarvoor eerst een horizontale zijstap wordt gedaan. 

**Buiten scope**

Er is meer lineage tussen en binnen beschouwingsniveaus mogelijk, maar er is bewust gekozen om deze niet in MIM uit te werken. 

| MIM niveau    | Lineage | Uitwerking te vinden in | 
| -------------   | ------------------------------------------- | --------------------------- |
| 1 naar ...    | vanuit een begripppenkader naar kennisbronnen | Buiten scope van MIM. |
| 1 naar 1      | vanuit een begrippenkader naar een ander begrippenkader | Buiten scope van MIM. |
| 2 naar 2      | vanuit CIM naar een begrippenkader | In scope, dit is uitgewerkt bij het gewone metamodel, bij view en extern en niet hier. |
| 3 naar 4      | vanuit LGM naar een technisch datamodel |  Buiten scope van MIM. Zie ontwerpbeslissingen. |
| 4 naar ...    | vanuit een technisch datamodel naar een LGM, CIM of begrippenkader | Buiten scope van MIM. |

## Scope

Dit document beperkt zich qua scope tot de MIM modellen zelf en behandeld primair de volgende verticale lineage:  
- van een conceptuele informatiemodel naar de bijbehorende semantiek, zoals bijvoorbeeld een begrippenkader (dat bijvoorbeeld uitgewerkt is in de NL-SBB standaard)
- van een logisch gegevensmodel naar een conceptueel informatiemodel

> De focus van MIM is om semantische herleidbaarheid van elk modelelement volledig aan te kunnen brengen m.b.v. een CIM en een begrippenkader

Echter, er is niet altijd sprake van een ideale situatie. Het aanbrengen van semantische herleidbaarheid best dan ook complex worden. Denk aan de volgende niet ideale situaties: 
- dat definities niet altijd gebaseerd zijn op eigen kennis en definities. Het komt voor dat de bovenliggende semantiek wordt bepaald door andere organisaties;  
- dat definities niet geheel op elkaar aansluiten en het goed zou zijn om dit verschil zichtbaar te maken. 
- dat het niet mogelijk is om naar een modelelement in een model van een bovenliggende MIM laag te verwijzen, omdat bijvoorbeeld een conceptueel informatiemodel nog niet gemaakt is of er nog geen begrippenkader is opgesteld of gepubliceerd. Het kan dan nuttig of nodig zijn om rechtstreeks naar een begrip of kennisbron te verwijzen.

Met dit soort situaties wordt daarom ook rekening gehouden in deze specificatie. Deze zijn meegenomen in deze uitwerking (in scope) waardoor het ook mogelijkheid is om te beschrijven dat we te maken hebben met een niet ideale situatie. 

> De specificatie ondersteund ideale en minder ideale situaties die je kan aantreffen in het vakgebied van informatie- en gegevensmodellering.

## Goede definities in samenhang

Een begrippenkader met begrippen en een conceptueel informatiemodel (CIM) kunnen gebruikt worden om te komen tot een welgevormde definitie van een gegevenstype die goed leesbaar en ook nog steed heel helder is voor gebruikers. Modelleren start doorgaans met opstellen van definities, van boven naar onder, maar in het uiteindelijk gebruik gaat de herleiding de andere kant op, van onder naar boven.

Hierbij wordt gekeken naar de definities en naar de bijbehorende semantische herleidbaarheid, beide horen bij elkaar. De laatste is een aanvulling op de eerste. Het doel is telkens om betekenis van elementen op ieder beschouwingsniveau uit te drukken met een welgevormde verwoording van die betekenis met een eigen definitie, waarbij semantische verwijzingen worden aangebracht naar voorliggende of bovenliggende definities, om aan te geven waarop de tekst van de eigen definitie is gebaseerd. Hierbij kan ook aangegeven worden of de aangebrachte herleidbaarheid wel of niet exact is, en wel of niet compleet is.  

Dit wordt uitgewerkt aan de hand van een uitgebreid voorbeeld. 

### Uitgebreid voorbeeld

In dit voorbeeld is een begrippenkader uitgewerkt naar een CIM en beide weer zijn gebruikt bij het maken van gegevensobjecttype en een gegevenstype in een LGM. 

*Begrippen in een begrippenkader:*

- Werknemer: Een werknemer is een natuurlijk persoon die werkt voor een organisatie. 
- Woonplaats: Een woonplaats is een afgebakend grondgebied met een eigen begrenzing dat gelegen is binnen het grondgebied van een gemeente, dat onder andere bestemd is voor bewoning door mensen.
- Geboorteplaats: Een geboorteplaats is de plaats waar een natuurlijk persoon is geboren, in Nederland is dit altijd een woonplaats. 

*Modelelementen in een CIM:* 

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

*Modelelementen in een LGM:*

Het model beschrijft een aantal gegevens die bijgehouden worden over werknemers die werken bij de eigen organisatie, in een registratie die enkele van deze gegevens uitwisselt met gebruikers: 

- een gegevensobjecttype _Geregistreerde werknemer_
   - een aantal gegevenstypen betreffende de naam en een werknemersnummer (maar deze worden niet nader uitgewerkt in het voorbeeld) 
   - een attribuuttype 'geboorteplaatscode' --> deze wordt uitgewerkt in onderstaand voorbeeld

Merk op dat het gegeven in geboorteplaatscode gaat over het gegevenstype: code van woonplaats. Het gegevenstype had dus ook woonplaats of code kunnen heten, maar dat is onvoldoende helder als het gaat om de geboorteplaats van de werknemer. Om soortgelijke redenen is ook niet de term geboorteplaats gebruikt maar geboorteplaatscode, om aan te geven dat het gegevenstype over de code gaat en niet over de naam van de woonplaats. Dit zorgt ervoor dat het logische gegevensmodel niet verwarrend is. Echter, er is geen begrip met de voorkeursterm geboorteplaatscode. 
  
Vraag: wat is nou een goede definitie van het gegevenstype geboorteplaatscode? 

Een antwoord kan zijn om deze uit de in het CIM gedefinieerde code te halen: de officiele identificatie van een Woonplaats. We raken dan echter relevante context kwijt, te weten dat het om de geboorteplaats gaat. 

Een ander antwoord zou daarom kunnen zijn om de definitie van het begrip geboorteplaats te gebruiken: een woonplaats waar een natuurlijk persoon is geboren. Maar het gegeven zelf gaat over de code ervan, dus dat klopt ook niet echt. 

Laten we daarom eerst kijken naar de semantische herleidbaarheid, gebruik makende van de bijbehorende concepten uit het vorige hoofdstuk.

*Semantische herleidbaarheid van het gegevenstype geboorteplaatscode:*

- onderwerp van gesprek: Natuurlijk persoon uit het CIM
   - niet zomaar een Natuurlijk persoon, maar een natuurlijk persoon die een werknemer is bij onze organisatie
- eigenschaptype: 'code' van Woonplaats uit het CIM 
   - lexicaal pad: de geboorteplaats van een natuurlijk persoon, in CIM termen: de rol die de woonplaats speelt in de relatie met een natuurlijk persoon (en dit is wat anders dan waar de persoon woont)

Merk op dat alleen de code van de woonplaats niet duidelijk maakt dat het om de geboorteplaats van een natuurlijk persoon gaat, het onderwerp van gesprek van dit gegevenstype is de natuurlijk persoon (niet de woonplaats). Het lexicale pad verbind het eigenschaptype code van woonplaats met het onderwerp van gesprek. 

Wanneer we de semantische herleidbaarheid beschouwen als onderdeel van een formele specificatie, en de oorspronklijke definities van de betrokken begrippen hierin subtitueren dan zou de formele definitie zijn: 
'De code is de officiele identificatie van een Woonplaats.' die de 'Een geboorteplaats is een plaats waar een natuurlijk persoon is geboren, in Nederland is dit altijd een woonplaats.' van een 'Natuurlijk persoon' die 'Een werknemer is een natuurlijk persoon die werkt voor een organisatie.' is bij onze 'Organisatie. Merk op dat Natuurlijk persoon' en 'Organisatie' ook nog uitgeschreven kunnen worden. 

Dit is heel exact, maar niet goed leesbaar. Merk ook op dat er extra woorden nodig zijn zoals 'die de' en 'van een' en 'is bij'. Semantische herleidbaarheid letterlijk uitschrijven levert meestal geen goed leesbare definities op voor de doelgroep van een model. Het is dan ook niet gebruikelijk om een definitie van een gegevenstype in een gegevensmodel op deze manier uit te schrijven. Het moet daarom altijd mogelijk zijn eigen verwoordingen toe te kennen. 

*Definitie van het gegevenstype geboorteplaatscode:*

Semantische herleidbaarheid is erg nuttig om te komen tot een goede definitie. Hiervan gebruik makende komen we tot teksten zoals: 
- De geboorteplaatscode is de code van de woonplaats die de geboorteplaats is van de natuurlijk persoon die werknemer is bij onze organisatie. 
- De geboorteplaatscode is de code van de woonplaats waarin een werknemer van onze organisatie is geboren.

Beide zijn heel helder. De eerste volgt zo veel als mogelijk de semantische herleidbaarheid. De tweede is ook heel helder en is nog prettiger leesbaar voor mensen. Deze beide verwoordingen zijn daarom goed. 

Althans, dit is zo wanneer _semantische herleidbaarheid_ ook is aangebracht **in aanvulling op** de _definitie van het gegevenstype_. Met de gespecificeerde semantische verwijzingen zijn dan _alle_ bijbehorende begrippen terug vinden en kan het bijbehorende CIM bestudeerd worden om te duiden of het om hieribj een eigenschaptype of relatietype of objecttype of iets anders gaat. Zo vinden we terug: 
- de begrippen: werknemer, woonplaats en geboorteplaats uit het begrippenkader
- extra begrippen die relevant zijn zoals natuurlijk persoon en organisatie
- aanvullend geeft het CIM aan dat er sprake is van een code van een woonplaats en dat de geboorteplaats een rol is die ingevuld wordt door een woonplaats. 

Wat er met het gegevenstype 'geboorteplaatscode' bedoeld wordt is dan volledig helder. Merk ook op dat hoe meer er gewerkt wordt met specialistische begrippen, of hoe meer "platgeslagen" een logisch gegevensmodel is opgezet, hoe belangrijker een goede definitie met bijbehorende semantische herleidbaarheid wordt. 

![5.2.1_Voorbeeld.png](media/5.2.1_Voorbeeld.png "Voorbeeld.png")

> Van dit voorbeeld leren we dat definities met elkaar samenhangen en dat het aanbrengen van deze samenhang kan leiden tot betere en beter begrijpelijke definities. 

In de volgende hoofdstukken wordt nader uitgewerkt hoe semantische herleidbaarheid precies gespecificeerd wordt. Merk op dat dit per modeltype verschillend is zijn omdat semantische verwijzingen in een CIM naar begrippen verwijzen en in LGM naar CIM modelelementen en van daaruit naar begrippen. Het doel is hierbij echter telkens hetzelfde. 
