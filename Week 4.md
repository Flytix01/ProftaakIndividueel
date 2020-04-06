# week 4
{
Om 08:30 begon de wekelijkse project opstartbijeenkomst, daarna zochten we een lokaal op LD.
Vandaag moesten we de json file kunnen uitlezen, en een begin te maken voor onze simulatie module. De agenda module heeft ons al een behoorlijk lange tijd gekost.
We waren bezig met het maken van de klasse structuur voor het uitlezen van de json file om die te kunnen tekenen.

Hierbij werd als tip gegeven dat we dat in een aparte applicatie doen, vooral omdat het testen dan stukken makkelijker gaat.
We kregen ook al te horen dat we weer verder konden gaan met het PVA we hadden een goede basis geschreven, maar nu moesten wat standaard onderwerpen uit het projectmanagement boek van P&OC naar voren brengen in het PVA.

## Senior gesprek
Vandaag hadden we het senior gesprek, daarin hadden we wat vragen over het uitlezen van de json file gesteld. We konden ook de map laten zien en vragen of dit voldoende was voor de simulatie. Hierbij gaf onze senior het advies om de hallen wat breder te maken, Pathfinding kan tricky zijn.
Hij was bang dat als de hallen niet breed genoeg waren de leerlingen misschien door de muur heen gaan clippen, of dat er zo grote onstoppingen zijn vanwege de collision dat ze nooit op tijd de les zouden halen.
Op zijn verzoek hebben we dus de halen wat breder gemaakt. 

De nieuwe map ziet er als volgt uit:

![SchoolmapVersie2](\ProftaakIndividueel\SchoolmapVersie2.png)

Ook hebben we in de nieuwe map de collisionlaag en de infolaag aangepast, de infolaag bestaat nu niet alleen uit de lokalen, kantine en de toiletten. Hij bevat nu ook alle plaatsen van de stoelen in de lokalen, kantine en lerarenkamer, de deuren van de toiletten, de ingang van de school en alle lokalen. 

De nieuwe info laag ziet er als volgt uit:

![InfolaagVersie2](\ProftaakIndividueel\InfolaagVersie2.png)

## De rest van de dag

Het uitlezen van de json lukte niet in het begin we waren de hele tijd bezig met uitlezen, waardoor we de tijd niet in de gaten hielden. 
Voordat we het wisten was het al 16.00 het PVA was flink vooruit gegaan alleen waren we geen stap verder gekomen met het uitlezen van de json file.
Helaas moesten 2 van onze groepsleden weg, omdat ze naar hun afspraken moesten gaan. Hierdoor bleven ik en 2 andere groepsleden achter,
om 17.00 besloten we toch nog naar een leraar te gaan voor hulp, gelukkig was johan nog op school. 
Hij hielp ons vooruit door uit te leggen hoe het uitlezen van de map in elkaar zit. Daarbij hielp hij ons met het schrijven van de code voor het uitlezen van de map waardoor we weer vooruit konden.

De code voor het uitlezen van de map:

'JsonReader reader = null;
        reader = Json.createReader(getClass().getResourceAsStream(fileName));
        JsonObject root = reader.readObject();

        int amountTileSet = root.getJsonArray("tilesets").size();

        for (int i = 0; i < amountTileSet; i++) {
            JsonObject tileset = root.getJsonArray("tilesets").getJsonObject(i);
            String imageFile = tileset.getString("image");
            int firstGID = tileset.getInt("firstgid");
            int imageWidth = tileset.getInt("imagewidth");
            int imageHeight = tileset.getInt("imageheight");
            int tileWidth = tileset.getInt("tilewidth");
            int tileHeight = tileset.getInt("tileheight");
            int tileCount = tileset.getInt("tilecount");
            while (tiles.size() <= firstGID + tileCount) {
                tiles.add(null);
            }
            try {
                rawImage = ImageIO.read(getClass().getResourceAsStream("/" + imageFile));
            } catch (IOException e) {
                e.printStackTrace();
            }
            for (int y = 0; y < imageHeight; y += tileHeight) {
                for (int x = 0; x < imageWidth; x += tileWidth) {
                    BufferedImage subimage = rawImage.getSubimage(x, y, tileWidth, tileHeight);
                    tiles.set(firstGID, subimage);

                    firstGID++;
                }
            }
        }'

Vandaag hielden we een reflectie gesprek met ons drieën, daarbij kwamen we tot de conclusie dat we vandaag simpel weg te lang hebben gewacht met het stellen van vragen over het uitlezen, zowel naar onze senior als naar andere leraren toe. We gaan dus bij toekomstige problemen eerder om hulp vragen. We waren vandaag om 18:00 naar huis gegaan.
}