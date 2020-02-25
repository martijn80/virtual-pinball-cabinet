## Zelf een Virtual Pinball Cabinet bouwen

In februari 2020 heb ik besloten een eigen virtual pinball mini cabinet te gaan bouwen. Mini, of eigenlijk table top (voor op tafel), omdat de maten van een echte flipperkast veel te groot zijn voor mijn woning. Bovendien vind ik die kasten te log en lelijk. De echte maten en met name de verhoudingen worden wel door veel pinball software als uitgangspunt genomen, dus hou hier rekening mee. 

Ik had nog twee ongebruikte 19" en 23,8" monitors die ik mooi als backbox en playfield kon gebruiken. De 19" is 5:4 dus bijna vierkant, perfect voor de backbox. Het playfield heeft normaal een 18,7:9 verhouding, de 23,8" monitor heeft helaas een 16:9 verhouding, 21:9 had mooier geweest, maar die heb ik niet liggen en kosten (door de bijzondere verhouding) nog steeds best wat duiten. 

Er zijn genoeg tekeningen online te vinden van het traditionele ontwerp van een pinball cabinet, maar zoals gezegd vind ik dit geen mooi ontwerp. Dus ben ik gaan schetsen en klooien in Fusion360 (een CAD tekenprogramma) om te kijken welk ontwerp ik gaaf vind. Het doel is om een beetje een retro arcade achtige uitstraling te krijgen. Dus t-molding, ronde hoeken gecombineerd met hoekige lijnen. Verder is een eis dat het playfield niet op de tafel rust maar verhoogt (met pootjes oid), ivm koeling en speakers in de onderplaat die lucht en bewegings ruimte moeten hebben. De hoek van het playfield moet ik nog mee spelen, maar ik verwacht iets van 10-15 graden. Tot slot wil ik graag een Kinect bovenop de kast zetten zodat mbv Better Arcade Mode (BAM) in Future Pinball een soort 3D weergave mogelijk is, waardoor het playfield heel realistisch eruit ziet en je echt om objecten in het speelveld heen kunt kijken (door de headtracking van de Kinect).

Het mooie aan Fusion360 is dat (als het goed is) je met je ontwerp naar een houtzagerij kan gaan en dat zij op basis van die tekeningen je planken kunnen "uitprinten", CNC-en heet dit. Daarnaast ontdek je door het klooien in 3D al vroeg knelpunten in je ontwerp, voordat je het laten produceren en je dan dus met een probleem zit. Dat scheelt dus heel wat frustratie, tijd en geld. Het aanpassen van je ontwerp is met een paar muisklikken gefixt en zo kan je een paar versies ontwerpen waar je er eentje uitpikt om echt te gaan maken. Voor het schetsen in Fusion was het handig dat ik alle maten van de onderdelen bij de hand had, vandaar de tabel met afmetingen.

### Windows instellen

Paralel aan het tekenen van het cabinet in Fusion360 ben ik aan de slag gegaan met installeren en configureren van de Pinball software. Zo kon ik al snel zien of ik alles aan de praat zou krijgen en kon ik alvast een beetje pinballen. De software die ik gebruik draait uitsluitend op Windows. 

Installeren van Future Pinball
todo 

Tafels downloaden

Instellen van de juiste kijkhoek 
F6 

Installeren van Steam en Pinball FX3

Dit is het makkelijkst, maar kost ook geld. 

Direct een Pinball FX3 tafel starten

- Maak een shortcut met als doel "C:\Program Files (x86)\Steam\Steam.exe" -applaunch 442120 -class -table_"Citadel"
- De opties -silent en -tenfoot werkte bij niet
- Windows toets + r 
- Type shell:startup
- Zet de shortcut in de map neer die door het vorige commande werd geopend

Andere toepassingen die opstarten uitzetten

- Windows toets + r 
- Type taskkmgr
- Ga naar de tab Opstarten
- Selecteer de app die wilt uitzetten door rechtermuis Uitschakelen te kiezen

Windows Gaming Bar / Balk uitzetten

Dit stoort namelijk tijdens het spelen met een soort game bar in je scherm en dat wil je niet
Zoek op Gamebalk en schakel dit uit

Windows onzichtbaar maken

Als de pinball machine opstart wil je geen sporen van Windows en omdat je geen muis hebt wil je de dat alleen wat je nodig hebt automatisch opstart. Ook al heb je inloggen met wachtwoord uitgezet, toch zal windows nog even een achtergrond en welcome tonen tijdens het inloggen. Het is mij niet gelukt helemaal weg te krijgen, maar met onderstaande instellingen wel zo onzichtbaar mogelijk.

- Windows toets + r 
- Type optionalfeatures
- Zoek naar Vergrendeling apparaat
- Vink Aangepaste aanmelding aan
- Vink Merkloos opstarten aan

Bovenstaande kan ook via cmd
- Zoek cmd
- Rechtermuis uitvoeren als admin 
- dism /Online /enable-feature /featureName:Client-DeviceLockdown
- dism /Online /enable-feature /featureName:Client-EmbeddedLogon

Dit heb ik ook gedaan maar weet niet meer of dat nodig is 
bcdedit.exe -set {globalsettings} bootuxdisabled on 

Tijdens inloggen geen gebruikers gegevens laten zien
- Windows toets + r 
- Type secpol.msc
- Ga naar lokaal beleid > interactieve login gebruikersnaam niet weergeven en zet dit op 1

Buroblad leeg maken
- Verwijder alle iconen (of verplaats ze naar een andere map
- Zet in de taakbalk alle iconen uit
- Verberg de taakbalk
- Kies een zwarte achtergrond kleur of een pinball afbeelding
- Kies als vergrendelingsscherm dezelfde afbeelding
- Vink aan dat je deze achtergrond afbeelding ook wilt weergeven op het aanmeldings scherm
- In het aanmeld scherm is die achtergrond afbeelding blurry. Dit zet je als volgt uit 
- Windows toets + r
- Type gepedit.msc
- Ga naar computer configuratie > beheer sjablonen > Aanmelden 
- Vink daar Duidelijke achtegrond aan
- En als dit niet onthouden was eerder: Altijd aangepaste achtergrond gebruiken


### Afmetingen

| Monitor | Verh | Resolutie | Hoogte  | Breedte | Bezel | Diepte |
|---|:---:|---:|---:|---:|---:|---:|
| Playfield | 18,7:9
| Backbox | 1:1
| Backglass posters | | 1920 x 1080
| Pinball FX3 DMD | 4:1 | 128 x 32 dots
| Dell U2415 24,1" | 16:10 | 1920 x 1200 | 35,06 cm  | 53,32 cm  | 5 mm | 4,57 cm |
| Dell U2417H 23,8" | 16:9 | 1920 x 1080 |  31,43 cm | 53,76 cm | 5 mm | 4,52 cm |
| Dell P190S 19" | 5:4 | 1280 x 1024 | 33,80 cm  | 41,00 cm | 18 mm| 5,90 cm |
| Kinect | | | 8,00 cm | 28,00 cm | 8,00 cm |
| Videokaart | | | 12,00 cm | 27,50 cm |
| Moederbord ATX | | | 30,50 cm | 24,40 cm
| Moederbord mini ATX | | | 24,00 cm | 24,40 cm
| Moederbord micro ATX | | | 17,00 cm | 17,00 cm
| Voeding | | | 14,00 cm | 16,00 cm | 9,00 cm

1. Let op de videokaart hoogte optellen bij die van het moederbord
2. Alle monitoren hebben een VESA 10mm beugelbevestiging, maak de plank echter 15cm hoog, zodat ze wat vlees hebben om op te steunen
3. De backglass poster is vaak 2/3 van de backbox, waardoor 1/3 overblijft voor speaker en dmd paneel.
4. De DMD op mijn 19" dell komt dus op : 8.44cm x 33.83cm of 1024 x 256 pixels
5. De hoek van het playfield moet gemeten vanaf een loodlijn vanaf 50 graden richting speler hoofd/blikveld. Vaak 5-6 graden tov horizontaal. Ik snap even niet hoe je dat kan verenigen.
6. De standaard afstand tot het glas in een traditionele pinball kast is onderop 2" en aan de achterkant 4.5" en glasdikte is 3/16" dat is circa 4,7mm

### Benodigde knoppen 

- 1 x grote ronde launch button
- 2 x 2 flipper buttons (naast de flipper, eentje voor nudge of magna safe)
- 2 x vierkante coin en start 
- Extra ball
- Exit
- On/Off


