# Semantische herleidbaarheid

Uitgangspunt is dat elk modelelement een eigen definitie kent en daarmee op zichzelf staat en dat semantische herleidbaarheid hier een aanvullende specificatie op is. In deze specificatie zelf kan aangegeven worden of herleidbaarheid wel of niet exact is, en wel of niet compleet (de mate van herleidbaarheid). 

Voorbeeld van een definitie in een logisch gegevensmodel, van een attribuuttype 'bsn': 
- de identificatie van een geregistreerd persoon

Voorbeeld van de bijbehorende semantische herleidbaarheid: 
- bsn is een gegevenstype dat onderdeel uitmaakt van het gegevensobjecttype GeregistreerdNP in een logisch gegevensmodel;
- voorgaande is gebaseerd op modelelementen die in een conceptueel informatiemodel zijn uitgewerkt, te weten een objecttype Ingeschrevene, met een eigenschaptype burgerservicenummer, waarbij de Ingeschrevene een specialisatie is van een objecttype Natuurlijk persoon (niet elke natuurlijk persoon is een ingeschrevene);
- voorgaande is gebaseerd op begrippen zoals natuurlijk persoon, een ingeschrevene, en een burgerservicenummer;

Deze begrippen zelf kunnen weer gebaseerd zijn op gepubliceerde kennisbronnen, zoals in dit voorbeeld het Burgerlijk Wetboek en de Wet algemene bepalingen burgerservicenummer. Merk op dat met dit voorbeeld niet bedoeld wordt dat er altijd sprake is of moet zijn van wet- en regelgeving. Er zijn vele domeinen waarbij dit niet of minder van belang is. 

![Het BSN voorbeeld in een diagram](media/BSN_voorbeeld.png "Het BSN voorbeeld in een diagram")

Voorgaande samenhang noemen we ook wel verticale lineage of afkomstrelaties tussen de modelelementen in de verschillende abstractielagen. In de modellering van een domein onderscheidt MIM verschillende abstractielagen van begrip naar conceptueel naar logisch naar fysieke implementatie. Omdat dit aparte lagen zijn is het van belang om de relatie tussen de lagen te kunnen beschrijven op het niveau van de individuele informatie-elementen. Er onstaat hiermee een systematiek van 'voortbouwende en uitbreidende' specificatie waarbij de afkomstrelaties traceerbaar en bruikbaar zijn van begrips- tot dataniveau, of eigenlijk van dataniveau terug naar begripsniveau. 

Of semantische herleidbaarheid van belang is voor een model of een organisatie, is een afweging voor elke organisatie zelf. Daarom is dit onderwerp als een aparte module opgenomen in de standaard. Het is niet verplicht om dit te doen, maar als er gekozen wordt om het wel te beschrijven doe het dan zoals in dit document is gespecificeerd. 

Dit document beperkt zich hierbij qua scope tot de MIM modellen zelf: 
- van een conceptuele informatiemodel naar de bijbehorende semantiek, zoals bijvoorbeeld een begrippenkader (dat bijvoorbeeld uitgewerkt is in de NL-SBB standaard)
- van een logisch gegevensmodel naar een conceptueel informatiemodel

Tot slot is het van belang om op te merken dat het aanbrengen van semantische herleidbaarheid best complex kan zijn. Denk aan: 
- dat definities niet altijd gebaseerd zijn op eigen kennis en definities. Het komt voor dat de bovenliggende semantiek wordt bepaald door andere organisaties;  
- dat het niet mogelijk is om naar een modelelement in een model van een bovenliggende MIM laag te verwijzen, omdat bijvoorbeeld een conceptueel informatiemodel nog niet gemaakt is, en het dus nuttig en nodig kan zijn om rechtstreeks naar een begrip te verwijzen;
- dat definities niet geheel op elkaar aansluiten en het goed zou zijn om dit verschil zichtbaar te maken. 

Met dit soort situaties wordt rekening gehouden. 
