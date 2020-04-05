# week 5
{
Om 08:30 begon de wekelijkse project opstartbijeenkomst, daarna zochten we een lokaal op LD.
Vandaag moesten we onze characters kunnen tekenen, laten lopen en collision moest tussen de characters moest worden toegevoegd.
We hadden nog geen plaatjes uit gekozen voor de characters zelf, dus hebben we daar eerst over nagedacht. 
Hierbij kwamen tot de volgende spritesheets, deze hebben we van deviantart gehaald (pokemon theme):

![CharacterSprites](\ProftaakIndividueel\CharacterSprites.png)

Het tekenen van de characters lukte wel alleen ging het lopen over de schoolmap heen wat moeilijker.
We hadden de voorbeeld applicatie gebruikt bij het maken van de logica, maar dat ging moeizaam we hadden alvast een basis op gesteld. De basis leek veel op die van het voorbeeld.
Alleen hadden we geen idee hoe onze characters over de map heen zouden lopen.

Vandaag gingen we ook verder met de simulatie module het was ons gelukt om de map te tekenen. Nu moesten nog alleen een camera maken, zodat we de map kunnen slepen in de simulatie. De camera zag er niet zo mooi uit, omdat tijdens het slepen de map soms weg viel. 

Hierbij nog één stukje code die we hebben gebruikt voor de camera:

'private void mouseScroll(ScrollEvent e) {
        scale *= (1 + e.getDeltaY() / 250.0f);
        drawSimulator(graphics2D);
    }

    private void mouseDragged(MouseEvent e) {
        if (e.getButton() == MouseButton.PRIMARY) {
            centerPoint = new Point2D.Double(
                    centerPoint.getX() - (lastMousePos.getX() - e.getX()) / scale,
                    centerPoint.getY() - (lastMousePos.getY() - e.getY()) / scale
            );
            lastMousePos = new Point2D.Double(e.getX(), e.getY());
            drawSimulator(graphics2D);
        }
    }'

Het is ons uiteindelijk niet gelukt de characters te laten lopen deze week. Wel hebben we het PVA afgerond en kunnen we deze dus vandaag inleveren. We zijn vandaag om 17.15 naar huis gegaan, en hebben helaas geen reflectie gesprek gehouden met zijn allen.
}