# week 9
{
Dit is de laatste reflectie week van mij portfolio, ook deze week heb ik sub kopjes met de dagen van deze week waarop we hebben gewerkt aan het project. We hebben afgesproken om de dagen waarop we werken deze week om 10:00 te beginnen.

## maandag
Vandaag zijn we door gegaan met het project het moet inmiddels aan het eind van deze week af zijn.
Ik en jan zijn weer door gegaan met het schrijven voor alle mogelijkheden van de characters.
De andere 2 groepsleden zijn begonnen aan de koppeling, daarbij gingen ze als eerst een klok maken waarop de tijd kan worden bijgebouden.
Deze kan dan worden gebruikt wanneer er in de agenda module een rooster wordt gemaakt.

Ik en jan zijn overgestapt op het gebruiken van een switch case voor alle states, vooral omdat we in onze oude logica gedeelte anders te veel dubbele code zit. De code ziet er dan als volgt uit:

' public void update(ArrayList<Person> people) {
        switch (state) {
            case NAAR_LOKAAL: {
                if (classroom != 0) {
                    Point2D studentTarget = logic.pathfind("lokaal" + classroom, position);
                    target = new Point2D.Double(studentTarget.getX() * 2, studentTarget.getY() * 2);
                    if (target.getY() == 0 && target.getX() == 0) {
                        this.state = FlowfieldStateInfo.IN_LOKAAL;
                    }
                }
                break;
            }'

Dit is alleen één case van de update methode deze wordt bij elke verandering opnieuw doorlopen, om te kijken waar de characters zich heen moeten bevinden. Inmiddels hebben we de enum klasse wat uitgebreidt met nieuwe states die we kunnen gebruiken voor de logica,
deze nieuwe states zijn:

'IDLE(6), NAAR_LOKAAL(7), NAAR_BREAKROOM(8), IN_BREAKROOM(9);'

Hiermee hebben we de volgende cases uitgewerkt:

- Lokaal -> Stoel
- Lokaal -> Breakroom (is tot nu toe alleen de kantine nog niet de lerarenkamer voor de leraren)
- Ingang -> Lokaal

Helaas is het ons niet gelukt om alle cases vandaag af te maken, ook moeten we nog wat extra cases uitwerken waaraan we nog niet zijn begonnen.

Extra cases waar nog code over moet worden nagedacht:
- Leraren -> Huis (Hoe laat? Komen ze naar school ook al hebben ze geen les?)
- Student -> Huis (Hoe laat? Laten we ze de hele dag op school zitten of moeten ze naar huis als ze geen lessen meer hebben?)
- Student -> Toilet (Random leerling moet elke les naar de wc? Leerlingen die in de kantine zitten kunnen naar de wc?)

Hier moeten we nog over nadenken.

## donderdag
Vandaag gaan we verder met het afwerken van alle cases, ook gaan de andere 2 groepsleden weer verder met het koppelen van de agenda en simulatie.
Eerst hebben we alle oude cases getest om te kijken of we niets over het hoofd hebben gezien.
Toen we alles waren nagelopen zijn we uiteindelijk weer verder gegaan met het uitwerken van alle cases waar we maandag niet aan kwamen.

De rest van de groep is weer verder gegaan met het koppelen van de agenda en de simulatie, bij het schrijven van de logica code hadden ik en jan wat dingen aangepast in de agenda module, zodat we onze code konden laten werken.
Helaas was dit niet zo slim van ons geweest. We hebben de import en export functie kapot gemaakt waardoor deze het niet meer deden.
De andere 2 moesten dus helaas onze fouten oplossen. Wat zorgde voor dubbel werk en dat kunnen we op dit moment niet echt gebruiken.

Voor de rest zag de dag er bijna net zo uit als maandag we werkten wat cases uit en bedachten weer wat nieuwe. 
De volgende cases die aan bod komen zijn:
- Leraren -> Huis (Leraren blijven standaard op school tot 16.30. Als de leraar geen les heeft hoeft hij of zij niet naar school te komen.)
- Student -> Huis (Als hun laatste les voorbij is gaan de leerlingen naar huis. Tijdens tussenuren zitten ze in de kantine)
- Student -> Toilet (Elke keer dat de leerlingen naar de kantine gaan gaat er minimaal 1 leerling naar de wc)

Hier hadden we al over nagedacht en regels voor opgesteld om het zo "school vriendelijk" mogelijk te maken.
De agenda module en simulatie zijn nu klaar om gekoppeld te worden en alle fouten zijn opgelost.

## Vrijdag
Vandaag koppelen we de agenda en simulatie, runnen wat tests en werken de laatste cases uit.
Het koppelen ging stukken makkelijker dan we hadden gedacht, we zijn blij met het feit dat onze code geen extra foutmeldingen geeft.

We hebben gisteren wat regels opgesteld voor de overige cases, die gaan ik en jan vandaag uitwerken. De rest van de groep is de simulatie en agenda aan het testen. Ook proberen ze fouten op te sporen, die ik en jan misschien hebben gemist.

De case:

- Student -> Toilet

Zijn we vandaag helaas niet aangekomen deze moeten ik en jan morgen nog doen, met wat hulp van de rest.
Ook moeten er nog voor zorgen dat de leerlingen en leraren goed de ingang inlopen.


## zaterdag
Ik en jan hebben vandaag alleen nog gewerkt, de andere 2 moesten helaas werken. We hebben de laatste case uitgewerkt:
- Student -> Toilet (Blijkbaar gaan de leraren nooit naar het toilet XD, helaas kunnen we dat vanwege de tijd niet doen)

Ook hebben we ervoor gezorgd dat de studenten en leraren goed door de ingang heen lopen. 
(eerst clipte sommige studenten nog door de muur heen!)
We hebben de laatste test uitgevoerd gekeken of alles het deed en waren hierna eindelijk klaar met het project.
Zelf zijn we niet zo blij met het proces, vooral omdat we tegen veel dingen zijn aangelopen door het project heen. Wel zijn we erg blij dat we met zijn allen nog het project hebben kunnen afmaken en het ziet er nog goed uit ook nog.

## Afsluiting
Dan sluit ik hierbij het laatste Hoofdstuk van dit portfolio! :)
}