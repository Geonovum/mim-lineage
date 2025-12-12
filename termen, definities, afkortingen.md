# Termen, definities en afkortingen

Semantische herleidbaarheid bestaat uit een aantal concepten, samengevat in dit diagram. 

<img width="1117" height="701" alt="20251212 diagram sem herleid (conceptueel)" src="https://github.com/user-attachments/assets/6fa935b6-053f-4142-98b6-84ad9282d6ba" />

Dit diagram geeft herleidbaarheid weer tussen verschillende beschouwingsniveaus op generieke wijze. Het kan zijn dat er per beschouwingsniveau andere termen worden gekozen. 


## Termen, definities

_Algemene_

| Term                   | Definitie                                                                        | Toelichting                         |
| ---------------------- | -------------------------------------------------------------------------------- | ----------------------------------- |
| semantische herleidbaarheid	| Semantische herleidbaarheid is het vermogen om definities van modelelementen uit lagere beschouwingsniveaus expliciet en traceerbaar te verbinden met de semantische betekenis die met begrippen is vastgelegd in het semantische beschouwingsniveau (MIM laag 1 of erboven). | Semantische herleidbaarheid is in opzet 'verticaal', dat wil zeggen dat we deze vormgeven door het aanbrengen van semantische verwijzingen tussen modelelementen uit modellen op de verschillende beschouwingsniveaus, van technische modellen naar logische modellen naar conceptuele modellen naar semantische modellen (die zelf weer gebasseerd kunnen zijn op bovenliggende kennisbronnen). | 	
| verticale semantische verwijzing |	Een directe semantische verwijzing is een semantische verwijzing naar een modelelement uit een hogerliggend beschouwingsniveau.	| Wanneer de beschouwingsniveaus boven elkaar worden afgebeeld, lopen directe semantische verwijzingen verticaal naar boven. | 
| horizontale semantische verwijzing | Een indirecte semantische verwijzing is een semantische verwijzing naar een ander gelijkgetypeerd modelelement binnen hetzelfde beschouwingsniveau. | We spreken over indirecte verwijzing omdat voor betekenis semantisch wordt verwezen naar de semantische herleiding van een ander, gelijk getypeerd modelelement binnen hetzelfde beschouwingsniveaus. Feitelijk wordt ermee aangegeven dat de betekenis van het modelelement wordt gerepliceerd van de ander. Deze verwijzing is niet 'verticaal' (tussen beschouwingsniveaus), maar 'horizontaal'. De indirecte semantische verwijzing is vooral onderkend om aan te geven dat een gegevenstype in een gegevensmodel van een gegevensuitwisseling qua betekenis exact overeenkomt met een gegevenstype in een administratie. Vaak loopt dat gelijk op met een logistieke herleidbaarheid (waar komt het gegeven vandaan komt, maar niet per se). | 


_Mate van verwijsbaarheid_

De mate van verwijsbaarheid geeft aan in hoeverre de semantische herleidbaarheid goed is gespecificeerd. Dit is alleen relevant voor modelelementen waarvoor semantiek nodig is, oftewel modelelementen die semantisch relevant zijn. 

| Term                   | Definitie                                                                        | Toelichting                         |
| ---------------------- | -------------------------------------------------------------------------------- | ----------------------------------- |
| volledige semantische herleiding | Een duiding van de mate van verwijsbaarheid waarbij alle benodigde semantische verwijzingen zijn aangebracht, de aangebrachte semantische verwijzingen zijn compleet en exact. | Compleet betekent dat alle benodigde verwijzingen gelegd kunnen worden, exact betekent dat elk van deze exact gebruikt kan worden, dwz de betekenis waarnaar verwezen wordt is dekkend en juist en daardoor exact bruikbaar (de verwoording kan net anders zijn, mara dit heeft geen invloed op de betekenis). | 
| deels ontbrekende semantische herleiding | Een duiding van de mate van verwijsbaarheid waarbij niet alle benodigde semantische verwijzingen zijn aangebracht.	| Het gaat hier dus om de onvolledigheid van de semantische verwijzingen, waarbij er wel minimaal één semantische verwijzing is aangebracht. Reden kan zijn dat modellen waarnaar verwezen zou moeten worden niet of niet volledig beschikbaar zijn. | 
| ontbrekende semantische herleiding | Een duiding van de mate van verwijsbaarheid waarbij geen enkele semantische verwijzing is aangebracht.	| Een reden kan zijn dat modellen waarnaar verwezen zou moeten worden niet of niet volledig beschikbaar zijn. |
| verklaring van verschil | De verwoording van het semantische verschil tussen de betekenis vanuit de semantische herleiding en de gegevensdefinitie. | Dit is alleen relevant wanneer de semantische verwijzingen niet volledig zijn. De verklaring geeft aan wat het verschil is, om hiermee gebruikers van gegevens inzicht te bieden. De oorzaak ligt in het feit dat bovenliggende semantiek niet voldoende matched met de gegevensdefintie. Doorgaans zal het zo zijn dat het wenselijk is om dit verschil een keer op te gaan lossen, maar dit is niet altijd het geval. | 
| semantisch niet relevant | Een duiding dat een modelelement semantisch niet relevant is, er hoeft geen semantische herleiding te worden aangebracht. | Een voorbeeld van een niet semantisch relevant modelelement zou bijvoorbeeld kunnen zijn: een hulpgegeven t.b.v. routering, een modelelement dat modelmatig nodig is maar geen semantiek heeft, een technisch hulpgegeven zoals een record id die e.e.a. koppelt in de implementatie maar niet uitgewisseld behoort te worden richting gebruikers. Voor dit soort modelelementen kan expliciet aangegeven worden dat deze semantisch niet relevant zijn. | 

Merk op: het kan voorkomen dat een modelelement wel semantisch relevant is, maar dat er nog geen herleidbaarheid voor is aangebracht. Gebruik dan: ontbrekende semantische herleiding. 

_Specifiek voor logische gegevensmodellen_



| Term                   | Definitie                                                                        | Toelichting                         |
| ---------------------- | -------------------------------------------------------------------------------- | ----------------------------------- |
| onderwerp	van gesprek | Een onderwerp van gesprek is de aanduiding van het objecttype of het relatietype waarvoor een gegevensobjecttype is ingericht. | Het modelelement uit het hogerliggende beschouwingsniveau van een LGM noemen we het onderwerp van gesprek. Daar gaan de gegevens over die getypeerd zijn in het LGM bij dit gegevensobjecttype. Bijvoorbeeld: een gegevensobjecttype geregistreerdNP heeft als onderwerp van gesprek het objecttype Ingeschrevene. De gegevens in het gegevensobject gaan over een object of exemplaar van dit objecttype. De achtergrond van onderwerp van gesprek is dat voor elk gegeven het helder moet zijn om welke eigenschap het gaat en van welk object, zie definitie van 'gegeven' en van 'gegevenstype'. |  
| lexicaal pad		| Een lexicaal pad is voor de structuur om in een logisch gegevens model, vanuit een gegeven startpunt, een specifiek modelelement uit een conceptueel informatiemodel aan te wijzen door de route tussen startpunt en eindpunt te specificeren. | Meestal hoort er bij 1 gegevensobjecttype ook 1 objecttype, of hoort er bij 1 gegevenstype ook 1 eigenschaptype of relatietype uit een CIM, maar het komt voor dat het pad hiernaartoe via meerdere relatietypen bij een ander objecttype uitkomt. Deze ingeschrevene kan wonen in een (woon)plaats en dit gegeven kan opgenomen zijn in hetzelfde gegevensobjecttype. 
| gegevensdefinitie	| Een gegevensdefinitie is de verwoording van de semantische herleiding van een gegevenstype. | Voor de betekenis van een gegevenstype leggen we semantische herleidbaarheid aan. Dan hebben we nog geen welgevormde verwoording van die betekenis die bruikbaar is voor lezers van het gegevensmodel, zeker niet in situaties waarin de semantische herleidbaarheid is gevormd met een samenstel van semantische verwijzingen en/of waar lexicale paden nodig zijn. Daarom wordt aanvullend een gegevensdefinitie opgenomen. Deze mag natuurlijk niet in tegenspraak zijn met de betekenis. | 

Nader uit te werken: keuzes maken bij lexicaal pad: 
1. Lexicaal pad: mensleesbaar vs machineleesbaar 
- mensleesbaar bv. string, met een notatiewijze en een delimeter en een volgorde. Dit zijn impliciet verwijzingen naar modelelementen. 
- machineleesbaar, bv. een opsomming van (bepaalde_ modelelementen
2. inclusief begin en eindpunt, of alleen de tussenpunten?
3. met of zonder generalisaties en specialisaties?
4. alleen als er ook een CIM is of ook als er alleen begrippen zijn? Is het pad altijd uitgedrukt in CIM modelelementen?


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
