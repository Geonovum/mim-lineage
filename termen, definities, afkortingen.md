# Termen, definities en afkortingen

## Termen, definities

_Algemene_

| Term                   | Definitie                                                                        | Toelichting                         |
| ---------------------- | -------------------------------------------------------------------------------- | ----------------------------------- |
| semantische herleidbaarheid	| Semantische herleidbaarheid is het vermogen om definities van modelelementen uit lagere beschouwingsniveaus expliciet en traceerbaar te verbinden met de semantische betekenis die met begrippen is vastgelegd in het semantische beschouwingsniveau (MIM laag 1 of erboven). | Semantische herleidbaarheid is in opzet 'verticaal', dat wil zeggen dat we deze vormgeven door het aanbrengen van semantische verwijzingen tussen modelelementen uit modellen op de verschillende beschouwingsniveaus, van technische modellen naar logische modellen naar conceptuele modellen naar semantische modellen (die zelf weer gebasseerd kunnen zijn op bovenliggende kennisbronnen). | 	
| directe semantische verwijzing |	Een directe semantische verwijzing is een semantische verwijzing naar een modelelement uit een bovenliggend beschouwingsniveau.	| Wanneer de beschouwingsniveaus boven elkaar worden afgebeeld, lopen directe semantische verwijzingen verticaal naar boven. | 
| indirecte semantische verwijzing | Een indirecte semantische verwijzing is een semantische verwijzing naar een ander gelijkgetypeerd modelelement binnen hetzelfde beschouwingsniveau. | We spreken over indirecte verwijzing omdat voor betekenis semantisch wordt verwezen naar de semantische herleiding van een ander, gelijk getypeerd modelelement binnen hetzelfde beschouwingsniveaus. Feitelijk wordt ermee aangegeven dat de betekenis van het modelelement wordt gerepliceerd van de ander. Deze verwijzing is niet 'verticaal' (tussen beschouwingsniveaus), maar 'horizontaal'. De indirecte semantische verwijzing is vooral onderkend om aan te geven dat een gegevenstype in een gegevensmodel van een gegevensuitwisseling qua betekenis exact overeenkomt met een gegevenstype in een administratie. Vaak loopt dat gelijk op met een logistieke herleidbaarheid (waar komt het gegeven vandaan komt, maar niet per se). | 


_Mate van verwijsbaarheid_

| Term                   | Definitie                                                                        | Toelichting                         |
| ---------------------- | -------------------------------------------------------------------------------- | ----------------------------------- |
| volledige semantische verwijzingen | een duiding van de mate van verwijsbaarheid waarbij alle benodigde semantische verwijzingen zijn aangebracht. | | 
| deels ontbrekende semantische verwijzingen | een duiding van de mate van verwijsbaarheid waarbij niet alle benodigde semantische verwijzingen zijn aangebracht.	| Het gaat hier dus om de onvolledigheid van de semantische verwijzingen, waarbij er wel minimaal één semantische verwijzing is aangebracht. Reden kan zijn dat modellen waarnaar verwezen zou moeten worden niet of niet volledig beschikbaar zijn. | 
| ontbrekende semantische verwijzingen | een duiding van de mate van verwijsbaarheid waarbij geen enkele semantische verwijzing is aangebracht.	| Een reden kan zijn dat modellen waarnaar verwezen zou moeten worden niet of niet volledig beschikbaar zijn. |
| verklaring van verschil | De verwoording van het semantische verschil tussen de betekenis vanuit de semantische herleiding en de gegevensdefinitie. | Dit is alleen relevant wanneer de semantische verwijzingen niet volledig zijn. De verklaring geeft aan wat het verschil is, om hiermee gebruikers van gegevens inzicht te bieden. De oorzaak ligt in het feit dat bovenliggende semantiek niet voldoende matched met de gegevensdefintie. Doorgaans zal het zo zijn dat het wenselijk is om dit verschil een keer op te gaan lossen, maar dit is niet altijd het geval. | 


_Specifiek voor logische gegevensmodellen_

| Term                   | Definitie                                                                        | Toelichting                         |
| ---------------------- | -------------------------------------------------------------------------------- | ----------------------------------- |
| onderwerp	van gesprek | Een onderwerp van gesprek is de aanduiding van het objecttype of het relatietype waarvoor een gegevensobjecttype is ingericht. | Bijvoorbeeld: een gegevensobjecttype geregistreerdNP heeft als onderwerp van gesprek het objecttype Ingeschrevene. De gegevens in het gegevensobject gaan over een object of exemplaar van dit objecttype. De achtergrond van onderwerp van gesprek is dat voor elk gegeven het helder moet zijn om welke eigenschap het gaat en van welk object, zie definitie van 'gegeven' en van 'gegevenstype'. |  
| lexicaal pad		| Een lexicaal pad is voor de structuur om in een logisch gegevens model, vanuit een gegeven startpunt, een specifiek modelelement uit een conceptueel informatiemodel aan te wijzen door de route tussen startpunt en eindpunt te specificeren. | Meestal hoort er bij 1 gegevensobjecttype ook 1 objecttype, of hoort er bij 1 gegevenstype ook 1 eigenschaptype of relatietype uit een CIM, maar het komt voor dat het pad hiernaartoe via meerdere relatietypen bij een ander objecttype uitkomt. Deze ingeschrevene kan wonen in een (woon)plaats en dit gegeven kan opgenomen zijn in hetzelfde gegevensobjecttype. 
| gegevensdefinitie	| Een gegevensdefinitie is de verwoording van de semantische herleiding van een gegevenstype. | Voor de betekenis van een gegevenstype leggen we semantische herleidbaarheid aan. Dan hebben we nog geen welgevormde verwoording van die betekenis die bruikbaar is voor lezers van het gegevensmodel, zeker niet in situaties waarin de semantische herleidbaarheid is gevormd met een samenstel van semantische verwijzingen en/of waar lexicale paden nodig zijn. Daarom wordt aanvullend een gegevensdefinitie opgenomen. Deze mag natuurlijk niet in tegenspraak zijn met de betekenis. | 


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
