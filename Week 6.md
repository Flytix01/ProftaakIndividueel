# week 6
{
Om 08:30 begon de wekelijkse project opstartbijeenkomst, daarna zochten we een lokaal op LD.
Vandaag was het plan om door te gaan met de character movement en collision. We moesten ook een start maken aan het pathfinding voor de characters.
Ik en Jan waren verantwoordelijk voor het maken van het algoritme. We hadden op internet gezocht naar manieren voor het schrijven van A* pathfinding.

## Tutor gesprek
Tijdens het tutor gesprek hadden we een planning gemaakt voor vandaag, en hadden we vragen gesteld over pathfinding.
Onze tutor raadde ons aan A* pathfinding niet te gebruiken, vooral omdat wij met grootte groepen characters bezig zijn. Om op elke character A* pathfinding toe te passen was te ineffiecent. 
Hij steldde voor om Flowfield pathfinding te gebruiken, dit kostte minder CPU-tijd en was makkelijker te gebruiken in grootte groepen en net zo goed als A* pathfinding.

## De rest van de dag
Na het tutor gesprek zijn ik en jan begonnen aan het zoeken van informatie over FlowField pathfinding. We vonden wat informatie op het internet over wanneer je flowfield pathfinding moest gebruiken en hoe je het kan toepassen. 

Hier een paar links van websites die we hebben bezocht:

<https://www.redblobgames.com/pathfinding/tower-defense/>
<https://gamedevelopment.tutsplus.com/tutorials/understanding-goal-based-vector-field-pathfinding--gamedev-9007>
<https://gamedev.stackexchange.com/questions/174801/efficiently-pathfinding-many-flocking-enemies-around-obstacles/174805>

We zijn gestart met het maken van een klasse genaamd VectorField. Hierin maken we een vector field aan voor het doel punt dat we hebben aangegeven, dit doen we met behulp van een 2d array. Helaas konden we dit niet zo goed testen als we wouden, omdat de character movement nog niet compleet was.

Attributen van het vectorfield klasse bestaan uit:
- boolean[][] map (hierin slaan we op waar we wel of niet mogen lopen)
- double[][] distanceMap (hierin in slaan we de afstanden tot het punt op)
- int[][] collisionMap (hierin slaan we de waardes van de collisionlaag op voor de map)

Code voor het maken van één vectorfield:
'public void recalc() {
        for (int y = 0; y < 100; y++){
            for (int x = 0; x < 100; x++){
                if (colissionMap[y][x] != 0){
                    map[x][y] = true;
                }
                else map[x][y] = false;
            }
        }
        
        map[targetX][targetY] = false;
        for (int x = 0; x < 100; x++) {
            for (int y = 0; y < 100; y++) {
                distanceMap[x][y] = Integer.MAX_VALUE;
            }
        }

        Queue<Point> points = new LinkedList<>();
        points.offer(new Point(targetX, targetY));
        distanceMap[targetX][targetY] = 0;
        while (!points.isEmpty()) {
            Point p = points.poll();

            for (int x = -1; x <= 1; x++) {
                for (int y = -1; y <= 1; y++) {
                    // Check new point is inside field
                    if (p.x + x < 0 || p.x + x >= 100 || p.y + y < 0 || p.y + y >= 100 || Math.abs(x) == Math.abs(y)) {
                        continue;
                    }
                    double d = distanceMap[p.x][p.y] + Math.sqrt(x * x + y * y);
                    if (d < distanceMap[p.x + x][p.y + y] && !map[p.x + x][p.y + y]) {
                        distanceMap[p.x + x][p.y + y] = d;
                        points.offer(new Point(p.x + x, p.y + y));
                    }
                }
            }

        }
    }'

We konden nog niet testen met de characters, maar wel konden we de waardes uit tekenen over de map heen, hiermee kunnen we dan zien waar de characters kunnen lopen en hoe ze naar het doel toe lopen. Gelukkig werkte de klasse na wat trial and error. 
Uiteindelijk was het de andere twéé gelukt om de character over de school map heen te laten lopen. Helaas was het wel later dan gedacht waardoor we de characters niet over de school map kunnen laten lopen door middel van het vectorfield dit zouden we dus volgende week moeten doen.

Onze evaluator was vandaag helaas ziek, dus hebben we weer geen reflectie gesprek gehouden. De vooruitgang ging in ieder geval wat beter dus kunnen we nu volgende week beginnen aan het pathfinden voor de characters. We hadden wat documentatie taken over gelaten aan onze evaluator, want hij gaf zelf al aan dat hij wel wat werk zou kunnen doen vanuit thuis. 
Vandaag waren we om 17.30 naar huis gegaan.
}