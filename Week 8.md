# week 8
{
Deze week hebben we gelukkig te horen gekregen dat we tot eind week 9 de tijd krijgen oom het project af te ronden.
Helaas moet ik wel mededelen dat één van onze groepsleden vorige week vrijdag, ons heeft geinformeerd dat ze gaat stoppen met de opleiding.
Het is haar eigen keuze dus in principe is er niets mis mee, wel is het nu rot dat we de meest belangerijke functionaliteiten met één persoon minder moeten maken. 
Deze week deel ik op in sub delen van dagen, vooral omdat we deze week veel hebben moeten inhalen van vorige week, dus hebben we al het werk verdeeld over verschillende dagen.

## dinsdag
Gisteren zijn we helaas vergeten iemand aan te wijzen om bij het wekelijkse gesprek te zijn met alle andere projectleiders, omdat we meer bezig waren met ons project dan met alle andere vakken.
We hadden om 11:00 op teams afgesproken te bellen, zodat we meteen kunnen beginnen.
We zijn meteen begonnen met het de koppeling van de characters en de vectorfield, daarbij hebben een stuk geschreven voor de logica van de verschillende states waarin je kunt komen tijdens het volgen van de vectorfield.
Ik heb daarbij bedacht om enums te gebruiken vooral, omdat dit mijzelf heel veel heeft geholpen bij het vorige project om de code beter te begrijpen en omdat het makkelijk te gebruiken is in dit project. 
De enum klasse heet FlowfieldStateInto en bestaat uit de volgende paar enums:

'public enum FlowfieldStateInfo {
    BUSY_SEAT(1), BUSY_TOILET(2), BUSY_KANTINE_SEAT(3), BUSY_KANTINE(4), IN_LOKAAL(5);'

Daarbij is er ook nog een getter voor het geval dat we de enums moeten kunnen ophalen. 
We hebben de enum klasse nog niet echt gebruikt voor iets dit zou later moeten komen voor bij het schrijven van de verschillende cases, zodat onze characters de juiste beslissingen nemen.

Voor de rest was het ons gelukt om vandaag nog de characters over het vectorfield te laten lopen, dus hiermee kunnen we de volgende keer beginnen met het schrijven van de logica.

## donderdag
Vandaag zijn we begonnen met het schrijven van de logica, daarbij hebben we een extra klasse toegvoegd die FlowfieldLogic heet in deze klasse gaan we alle beslissingen nemen op basis van waar de character naar toe moet. In deze klasse wordt vooral de route uitgerekend met de state van de character.
In de person klasse wordt de state veranderd en wordt de nieuwe state toegekend, dit doen we door verschillende if statements onder elkaar te zetten om zo de juiste state mee te geven.

We hebben in de map een extra collisionlaag toegevoegd, voor elke lokaal, omdat we niet wouden dat als de leerlingen zich bevinden in één lokaal en één stoel ging opzoeken zijn een vectorfield maken op basis van de hele map min de collisionMap.
De extra collisionLaag is om de lokale heen zodat de characters die de state IN_LOKAAL hebben bereikt een vectorfield volgen op basis van de map min de lokaalCollisionLaag. Het zoeken gaat hierdoor stukken sneller.

De attributen van de FlowfieldLogic klasse:
- int[][] collisionMap (We halen de collisionMap op uit vectorfield, zodat we die hier in deze klasse kunnen gebruiken)
- int[][] lokaalCollisionMap (Hier slaan we de waardes op die de collisionlaag van de lokalen heeft)
- Point2D.double[][] tileTargets (Hierin slaan we de berekende targets op)
- Map<String, Vectorfield> vectorFields (In de generate methode zetten we van tevoren alle targets die ze kunnen gerbuiken)

Hiermee hebben we een opzet om de koppeling tussen de agenda module en simulatie te behalen.
}