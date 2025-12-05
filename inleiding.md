# Inleiding
Het metamodel voor informatiemodellering (MIM) biedt een gemeenschappelijk vertrekpunt voor het maken van informatie- en gegevensmodellen. Het bevat afspraken en conventies voor het creëren van modellen en modelelementen, met daarbij standaard metagegevens. Het leidt tot meer uniforme beschrijvingen van modellen en zorgt daardoor voor meer begrijpelijkheid en andere vormen van kwaliteit.

Dit document beschrijft een specifiek onderdeel van het MIM namelijk de semantische herleidbaarheid. Het doel van semantische herleidbaarheid is om aan te geven hoe definities van modelelementen in deze modellen zich verhouden tot bovenliggende semantiek. Hierbij wordt in de kern vooral gekeken naar de tekstuele verwoording van de definitie die gebruikt wordt voor een modelelement in een MIM model. Deze definitie van het modelelement staat voor elk modelelement op zichzelf. Hiermee wordt bedoeld dat deze strikt genomen zelf geen onderdeel van semantischer herleidbaarheid is. De semantische herleidbaarheid is een aanvulling erop, en bestaat uit verwijzingen naar bovenliggende definities.

Bijvoorbeeld: 
- een gegevenstype bsn, wat een gegevenstype is dat onderdeel uitmaakt van het gegevensobjecttype GeregistreerdNP in een logisch gegevensmodel;
- voorgaande is gebaseerd op modelelementen die in een conceptueel informatiemodel zijn uitgewerkt, te weten een objecttype Ingeschrevene, met een eigenschaptype burgerservicenummer, waarbij de Ingeschrevene een specialisatie is van een objecttype Natuurlijk persoon (die niet altijd een ingeschrevene is);
- voorgaande is gebaseerd op begrippen zoals natuurlijk persoon, een ingeschrevene, en een burgerservicenummer;
- deze begrippen zelf kunnen weer gebaseerd zijn op gepubliceerde kennisbronnen, zoals bijvoorbeeld wet- en regelgeving zoals het Burgerlijk Wetboek en de Wet algemene bepalingen burgerservicenummer.

Voorgaande samenhang noemen we ook wel verticale lineage of afkomstrelaties tussen de modelelementen in de verschillende abstractielagen. In de modellering van een domein onderscheidt MIM verschillende abstractielagen van begrip naar conceptueel naar logisch naar fysieke implementatie. Omdat dit aparte lagen zijn is het van belang om de relatie tussen de lagen te kunnen beschrijven op het niveau van de individuele informatie-elementen. Er onstaat hiermee een systematiek van 'voortbouwende en uitbreidende' specificatie waarbij de afkomstrelaties traceerbaar en bruikbaar zijn van begrips- tot dataniveau, of eigenlijk van dataniveau terug naar begripsniveau. 

Of semantische herleidbaarheid van belang is voor een model of een organisatie, dat is een afweging voor elke organisatie zelf. Daarom is dit onderwerp als een aparte module opgenomen in de standaard. Het is niet verplicht om dit te doen, maar als er gekozen wordt om het wel te beschrijven doe het dan zoals in dit document is gespecificeerd. 

Dit document beperkt zich hierbij qua scope tot de MIM modellen zelf: 
- van een conceptuele informatiemodel naar de bijbehorende semantiek, zoals bijvoorbeeld een NL-SBB begrippenkader
- van een logisch gegevensmodel naar een conceptueel informatiemodel

Tot slot is het van belang om op te merken dat het aanbrengen van semantische herleidbaarheid best complex kan zijn. Denk aan: 
- definities zijn niet altijd gebaseerd zijn op eigen kennis en definities. Het komt voor dat de bovenliggende semantiek wordt bepaald door andere organisaties;  
- dat het niet mogelijk is om naar een modelelement in een model van een bovenliggende MIM laag te verwijzen, omdat dat model nog niet gemaakt is;
- dat definities niet geheel op elkaar aansluiten en het goed zou zijn om dit verschil zichbaar te maken en te verklaren. 

Met dit soort situaties wordt rekening gehouden. 



