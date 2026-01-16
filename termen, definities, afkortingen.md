# Termen, definities en afkortingen

Centraal bij semantische herleidbaarheid staat het **semantisch relevant modelelement**. Dit is een modelelement waarvoor het zinvol en nodig is om deze te verbinden met bovenliggende semantiek uit een CIM en/of begrippenkader. Anders gezegd, de gegevensdefinitie ervan wordt zo goed als mogelijk in verband gebracht met bovenliggende definities, door de **semantische herleiding** ervoor te beschrijven. 

Semantische herleiding kan verticaal en horizontaal aangebracht worden. 
- verticaal geeft aan dat er verwijzingen naar CIM modelelementen en/of begrippen uit een begrippenkader worden benoemd;
- horizontaal geeft aan dat de semantische herleiding al elders is beschreven, in een model van hetzelfde MIM-niveau, en het modelelement in het eigen model er qua betekenis mee gelijk gesteld wordt.  

Semantische herleiding bestaat uit een of meerdere **semantische verwijzingen**. De set van verwijzing kan _wel of niet compleet_ zijn om er de gegevensdefinitie mee af te dekken. Aanvullend kan de bovenliggende definitie waarnaar verwezen wordt, hierbij elke verwijzing op zichzelf beschouwend, _wel of niet exact_ in overeenstemming zijn met de tekstuele verwoording van de gegevensdefinitie. 

Semantische herleidbaarheid in een diagram. 

<img width="1117" height="701" alt="20251212 diagram sem herleid (conceptueel)" src="https://github.com/user-attachments/assets/6fa935b6-053f-4142-98b6-84ad9282d6ba" />

Dit diagram geeft herleidbaarheid weer tussen verschillende beschouwingsniveaus op generieke wijze. Het kan zijn dat er per beschouwingsniveau (LGM --> CIM en/of CIM --> begrippenkader en/of LGM --> begrippenkader) andere termen worden gekozen. 

Hieronder worden de begrippen beschreven die nodig zijn om semantische herleidbaarheid te begrijpen.

## Termen, definities

_Algemene_

| Term                   | Definitie                                                                        | Toelichting                         |
| ---------------------- | -------------------------------------------------------------------------------- | ----------------------------------- |
| semantische herleidbaarheid	| Semantische herleidbaarheid is het vermogen om definities van modelelementen uit lagere beschouwingsniveaus expliciet en traceerbaar te verbinden met de  betekenis die met begrippen is vastgelegd in het semantische beschouwingsniveau. | Semantische herleidbaarheid is in opzet 'verticaal', dat wil zeggen dat we deze vormgeven door het aanbrengen van semantische verwijzingen tussen modelelementen uit modellen op de verschillende beschouwingsniveaus, van technische modellen naar logische modellen naar conceptuele modellen naar semantische modellen (die zelf weer gebasseerd kunnen zijn op bovenliggende kennisbronnen). | 	
| verticale semantische verwijzing |	Een directe semantische verwijzing is een semantische verwijzing naar een modelelement uit een hogerliggend beschouwingsniveau.	| Wanneer de beschouwingsniveaus boven elkaar worden afgebeeld, lopen directe semantische verwijzingen verticaal naar boven. | 
| horizontale semantische verwijzing | Een indirecte semantische verwijzing is een semantische gelijkstelling, door middel van een verwijzing naar een ander gelijkgetypeerd modelelement in een ander logisch gegevensmodel. | We spreken over indirecte verwijzing omdat voor de semantische herleiding wordt verwezen naar de semantische herleiding elders. Deze verwijzing is niet 'verticaal' (tussen beschouwingsniveaus), maar 'horizontaal', binnen hetzelfde beschouwingsniveau. De indirecte semantische verwijzing is vooral onderkend om aan te geven dat een gegevenstype in een gegevensmodel van een gegevensuitwisseling qua betekenis exact overeenkomt met een gegevenstype in een administratie van waaruit gegevens zijn gebruikt voor een informatieproduct of zijn overgenomen naar een kopie. Vaak loopt deze herleidbaarheid gelijk op met een logistieke herleidbaarheid (datalineage, waar komt het gegeven vandaan komt). | 


_Mate van verwijsbaarheid_

De mate van verwijsbaarheid geeft aan in hoeverre de semantische herleidbaarheid klopt met de bovenliggende definities, zoals via verticale of horizontale semantische herleiding gespecificeerd. Dit is alleen relevant voor modelelementen waarvoor semantiek nodig is, oftewel modelelementen die semantisch relevant zijn. 

| Term                   | Definitie                                                                        | Toelichting                         |
| ---------------------- | -------------------------------------------------------------------------------- | ----------------------------------- |
| complete semantische herleiding | Een duiding van dat alle relevante semantische verwijzingen zijn aangebracht. | Er ontbreekt er geen (ook niet vanwege het ontbreken van een CIM of een begrippenkader). Wanneer de herleiding niet compleet is dan is er altijd sprake van ten minste 1 ontbrekende verwijzing, die er wel zou moeten zijn om de gehele gegevensdefinitie af te dekken. Als de gehele gegevensdefinitie afgedekt wordt dan ontbreken er geen verwijzingen en is de herleiding dus compleet. |
| exacte semantische verwijzing | Een duiding dat de gegevensdefinitie en de betekenis waarnaar via alleen deze verwijzing naar verwezen wordt exact met elkaar in overeenstemming zijn. | De  verwoording kan net anders zijn, maar dit heeft geen invloed op de betekenis. De strekking is hetzelfde. Wanneer er meerdere verwijzingen nodig zijn, dan betreft het exact overeenstemmen alleen deze betreffende verwijzing en het gedeelte van de gegevensdefinitie die hierbij hoort. |
| compleet en exact  | De semantische herleiding is compleet en alle semantische verwijzingen zijn exact. | De gegevensdefinitie kan volledig verklaard worden via de betekenis die te vinden is via de semantische verwijzingen en is daarmee in overeenstemming. De verwoording is mogelijk net anders, maar de betekenis is hetzelfde (semantisch equivalent). |
| verklaring van verschil | De beschrijving van het semantische verschil tussen de betekenis van de modelelementen waarnaar verwezen wordt vanuit de semantische herleiding en de gegevensdefinitie. | Deze zijn niet semantische equivalent met elkaar, er is sprake van een wezenlijk verschil. De verklaring geeft aan wat het verschil is, om hiermee gebruikers van gegevens inzicht te bieden. De oorzaak ligt in het feit dat bovenliggende semantiek niet voldoende matched met de gegevensdefinitie (het gegevensmodel klopt niet goed met het CIM en/of begrippenkader). Doorgaans zal het zo zijn dat het wenselijk is om dit verschil een keer op te gaan lossen, zeker wanneer het verschil per ongeluk is ontstaan. Als semantische herleiding compleet en exact is, dan is het nooit nodig om een verklaring van verschil te beschrijven.  | 
| uitleg verschil in verwoording | De beschrijving van het verschil in verwoording van de betekenis van de modelelementen waarnaar verwezen wordt vanuit de semantische herleiding en de gegevensdefinitie, terwijl de betekenis wel hetzelfde is. | Er is geen sprake van een semantisch verschil. De betekenis is semantisch equivalent, maar er is wel gebruik gemaakt van andere woorden. Het is niet nodig om punten en komma's en verbindingswoorden uit te leggen. De uitleg is nuttig voor de lezers van de gegevensdefinitie, die wel een verschil in woorden zien, en gerustgesteld willen worden dat er slechts sprake is van een andere verwoording. | 
| semantisch niet relevant | Een duiding dat een modelelement semantisch niet relevant is, er hoeft geen semantische herleiding te worden aangebracht. | Voor dit soort modelelementen kan expliciet aangegeven worden dat deze semantisch niet relevant zijn, oftewel niet in een CIM of begrippenkader horen. Semantisch niet relevante modelelementen hebben uiteraard wel een gegevensdefinitie, bij alle getypeerde gegevens hoort immers een gegevensdefinitie. Een voorbeeld van een niet semantisch relevant modelelement zou bijvoorbeeld kunnen zijn: een hulpgegeven t.b.v. routering, een modelelement dat modelmatig nodig is maar geen semantiek heeft, een technisch hulpgegeven zoals een record id die e.e.a. koppelt in de implementatie maar niet uitgewisseld behoort te worden richting gebruikers. Merk op: het kan voorkomen dat een modelelement wel semantisch relevant is, maar dat er nog geen herleidbaarheid voor is aangebracht. Gebruik dan: ontbrekende semantische herleiding. | 

_Specifiek voor logische gegevensmodellen_


| Term                   | Definitie                                                                        | Toelichting                         |
| ---------------------- | -------------------------------------------------------------------------------- | ----------------------------------- |
| onderwerp	van gesprek | Een onderwerp van gesprek geeft het objecttype of het relatietype aan waarvoor een gegevensobjecttype is ingericht. | Bijvoorbeeld: een gegevensobjecttype geregistreerdNatuurlijkPersoon heeft als onderwerp van gesprek het objecttype Ingeschrevene. De gegevens in het gegevensobject gaan over een object of exemplaar van dit objecttype, ook als het gegeven bijvoorbeeld een naam is van een plaats, want het gaat dan om de woonplaats die de ingeschrevene hanteert als woonadres. Er staat daarom in de definitie bewust 'waarvoor', en niet 'waarmee'. Merk op dat als in het CIM staat dan een natuurlijk persoon maar 1 woonadres kan hebben, dan hoort het gegevensobject er ook maar 1 te hebben (op 1 moment in de tijd). De achtergrond van onderwerp van gesprek is dat voor elk gegeven het helder moet zijn om welke eigenschap het gaat en vanuit welk object dit beschouwd wordt, zie definitie van 'gegeven' en van 'gegevenstype'. Het is mogelijk om per gegevenstype een onderwerp van gesprek bij te houden, maar omdat dit in principe altijd hetzelfde is voor hetzelfde gegevensobject wordt dit metagegeven bij het gegevensobjecttype bijgehouden. Een eigenschaptype in een CIM heeft op zich ook een onderwerp van gesprek, maar dat is altijd het object dat getypeerd is d.m.v. het objecttype zelf. Daarom wordt dit verder niet uitgemodelleerd. |  
| lexicaal pad		| Een lexicaal pad is de specificatie van de route tussen een gegevenstype en het bijbehorende eigenschaptype in een conceptueel informatiemodel waarnaar de semantische verwijzing naar gelegd is. | Meestal hoort er bij 1 gegevensobjecttype ook 1 objecttype en hoort er bij 1 gegevenstype ook 1 eigenschaptype van dit objecttype. Er is dan niet echt sprake van een route of pad door het CIM, alleen maar van een verwijzing naar een eigenschaptype in het CIM. Het komt echter ook voor dat er wel pad door het CIM gelopen wordt, via een of meerdere relatietypen en objecttypen, vertrekkend vanuit het onderwerp van gesprek. Zie ook het voorbeeld aan het begin van dit hoofdstuk. Dan is de specificatie van het lexicale pad noodzakelijk om exact aan te geven hoe de semantische herleiding precies in elkaar zit. Elke semantische verwijzing heeft 0 of 1 lexicaal pad, nooit meerdere. Aangezien 1 gegevenstype wel meerdere semantische verwijzingen kan hebben (bv. een adresregel) kan bij 1 gegevenstype wel sprake zijn van meerdere lexicale paden.  
| gegevensdefinitie	| Een gegevensdefinitie is de beschrijving van de betekenis die hoort bij een gegevenstype. | Het betreft de officiele gegevensdefinitie die in de praktijk gehanteerd wordt door gebruikers, zoals beschreven in officiele koppelvlakdocumentatie of interfaces. Het betreft hier niet een alternatieve B1 taalniveau verwoording en ook invulinstructies horen niet in de gegevensdefintie te worden opgenomen. Indien voor een gegevenstype semantische herleidbaarheid is aangebracht kan de gegevensdefinitie aan de hand hiervan uitgewerkt worden. Let wel, wanneer alle definities uit bovenliggende modellen erbij worden gepakt dan ontstaat niet altijd direct een welgevormde verwoording van die betekenis die bruikbaar is voor lezers van het gegevensmodel en een dergelijke verwoording is wel nuttig en nodig. Het is deze verwoording die de gegevensdefinitie is. Nota bene: het is mogelijk dat semantische herleidbaarheid niet compleet en/of niet exact is en dat de gegevensdefinitie die in de praktijk gebruikt wordt afwijkt van de bovenliggende definities. Geef dit dan aan d.m.v. een verklaring van verschil (doe niet net alsof het wel klopt). | 

Overige:

In MIM 1.2 kunnen logische modelelementen gekoppeld aan een modelelement uit een conceptueel informatiemodel, met behulp van het metagegeven `mim:begrip`. 
De definitie daarvan luidt:  

In MIM 1.2 kunnen logische modelelementen gekoppeld aan een begrip met behulp van het metagegeven `mim:begrip`. 
De definitie daarvan luidt: 

--

<p class="note" title="">
Geef de term op deze manier aan in de tekst:  
We gebruiken een <a>fiets</a> om te fietsen.
</p>


## Afkortingen

|                   |                                                                                                                                            |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| MIM     | Metamodel Informatiemodellering        |
