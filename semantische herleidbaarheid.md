# Semantische herleidbaarheid

In dit hoofdstuk maakt u kennis met dit onderwerp. 

Uitgangspunt is dat elk modelelelement uit een MIM model een eigen definitie kent. Deze definitie staat op zichzelf en zodanig opgesteld dat deze past bij het beschouwingsniveau dat uitgewerkt is in het betreffende model. Semantische herleidbaarheid is hierop een aanvullende specificatie, die de modelelementen en definities uit de verschillende modellen met elkaar verbindt. 

Neem bij voorbeeld een attribute '**bsn**' in een logisch gegevensmodel met als definitie: de identificatie van een geregistreerd persoon. 

In dit voorbeeld is de bijbehorende semantische herleidbing: 
- **bsn** is een _gegevenstype_ dat onderdeel uitmaakt van het _gegevensobjecttype GeregistreerdNP_ in een logisch gegevensmodel;
- voorgaande is gebaseerd op modelelementen die in een conceptueel informatiemodel zijn uitgewerkt, te weten een _objecttype Ingeschrevene_, met een _eigenschaptype burgerservicenummer_, waarbij de Ingeschrevene een _specialisatie is van  objecttype Natuurlijk persoon_ (niet elke natuurlijk persoon is een ingeschrevene);
- voorgaande is gebaseerd op begrippen zoals: _begrip natuurlijk persoon_, een _begrip ingeschrevene_, en een _begrip burgerservicenummer_;
- deze begrippen zelf kunnen weer gebaseerd zijn op gepubliceerde brondocumenten, zoals in dit voorbeeld _het Burgerlijk Wetboek_ en de _Wet algemene bepalingen burgerservicenummer_.

Opmerking: met dit voorbeeld wordt niet bedoeld dat er altijd sprake is of moet zijn van wet- en regelgeving. Er zijn vele domeinen waarbij dit niet of minder van belang is. 

![Het BSN voorbeeld in een diagram](media/BSN_voorbeeld.png "Het BSN voorbeeld in een diagram")

Voorgaande samenhang noemen we ook wel verticale lineage of afkomstrelaties tussen de modelelementen in de verschillende beschouwingsniveaus. Hierbij kan ook aangegeven worden of herleidbaarheid wel of niet exact is, en wel of niet compleet is.  

In de modellering van een domein onderscheidt MIM verschillende beschouwingsniveaus. Bijvoorbeeld van begrip naar conceptueel naar logisch naar fysieke implementatie. Omdat dit aparte lagen zijn is het van belang om de relatie tussen de lagen te kunnen beschrijven op het niveau van de individuele informatie-elementen. Er onstaat hiermee een systematiek van 'voortbouwende en uitbreidende' specificatie waarbij de afkomstrelaties traceerbaar en bruikbaar zijn van begrips- tot dataniveau, of eigenlijk van dataniveau terug naar begripsniveau. 

Dit document beperkt zich hierbij qua scope tot de MIM modellen zelf: 
- van een conceptuele informatiemodel naar de bijbehorende semantiek, zoals bijvoorbeeld een begrippenkader (dat bijvoorbeeld uitgewerkt is in de NL-SBB standaard)
- van een logisch gegevensmodel naar een conceptueel informatiemodel

Tot slot is het van belang om op te merken dat het aanbrengen van semantische herleidbaarheid best complex kan zijn. Denk aan: 
- dat definities niet altijd gebaseerd zijn op eigen kennis en definities. Het komt voor dat de bovenliggende semantiek wordt bepaald door andere organisaties;  
- dat definities niet geheel op elkaar aansluiten en het goed zou zijn om dit verschil zichtbaar te maken. 
- dat het niet mogelijk is om naar een modelelement in een model van een bovenliggende MIM laag te verwijzen, omdat bijvoorbeeld een conceptueel informatiemodel nog niet gemaakt is of er nog geen begrippenkader is opgesteld of gepubliceerd. Het kan dan nuttig of nodig zijn om rechtstreeks naar een begrip of kennisbron te verwijzen.

Met dit soort situaties wordt rekening gehouden. Deze zijn meegenomen in deze uitwerking (in scope) waardoor het ook mogelijkheid is om te beschrijven dat we te maken hebben met een niet ideale situatie. 

Of semantische herleidbaarheid van belang is voor een model of een organisatie, is een afweging voor elke organisatie zelf. Daarom is dit onderwerp als een aparte module opgenomen in de standaard. Het is niet verplicht om dit te doen, maar als er gekozen wordt om het wel te beschrijven doe het dan zoals in dit document is gespecificeerd. 
