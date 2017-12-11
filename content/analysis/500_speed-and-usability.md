Hastighetsanalys
=================================
##Inledning
I denna analys har jag studerat hur lång tid det tar för en sida att laddas,
hur stor den är samt hur många resurser som laddas. Jag har valt att ha med
en sida med mycket bilder (stocksnap i detta fallet), en sida med mycket trafik
(sf.se) samt en sida som jag gjort själv. Jag har valt just dessa för att se hur
skillnaden kan se ut beroende på målgrupp och syftet med sidan. Sidan som jag
själv har gjort tog jag med för att visa hur det kan se ut när man skapar en sida
utan förståelse för bild optimering.

Jag har använt mig av Google PageSpeed för att få fram en poängsättning samt
för att få förslag på olika förbättrningar som kan göras. Jag har även använt mig
av Google Chrome och dess Devtool för att mäta hastigheten samt storlek på sidan som
laddas. Uppkopplingen har bestått av fiberlina på 100/100MBit, med anslutning via
wifi. Varje webbplats har blivit testad med tre stycken olika sidor. För varje sida
har tre stycken mätningar gjort gällande hastighet. Tiden som presenteras för respektive
sida är ett medeltal för samtliga tre mätningar.

Rådata för mätningar finner ni [här](https://docs.google.com/spreadsheets/d/1hFiDyq7O2Jn4t01aRCe4kbZNbQQVdP_JtEIW0DvwVv4/edit#gid=0).



SF.se
---------------------------------
[FIGURE src="image/SF_home.png" class="center"]

###Mätningar:
| Sida                                          |PageSpeed Desktop Betyg |PageSpeed Mobile Betyg  | Medel laddtid | Storlek | Resurser
| :-------------                               |:-------------:         | :-----:                | :-----:       | :-----: | :-----:
| [https://www.sf.se/](https://www.sf.se/)      | 78/100                 | 60/100                 | 7,6s          | 1MB       |   109
| [https://www.sf.se/moten/](https://www.sf.se/moten/)      | 50/100               |   41/100     | 1,9s          | 0,697MB       |   31
| [https://www.sf.se/nyheter/](https://www.sf.se/nyheter/)  | 80/100               |   60/100     | 3,6s          | 0,734MB       |   138

###Förbättringar:
Det finns JavaScript kod som blockerar rendering av innehållet ovanför mitten innan
följande innehåll ha blivit renderat. Denna kod bör tas bort för att öka hastigheten
av renderingen. Det finns en del bilder som kan optimeras för att spara så mycket
som upp till 16% i storlek.

TECHLINE-ltd.com
---------------------------------
[FIGURE src="image/techline_home.png" class="center"]

###Mätningar:
| Sida                                          |PageSpeed Desktop Betyg |PageSpeed Mobile Betyg  | Medel laddtid | Storlek | Resurser
| :-------------                               |:-------------:         | :-----:                | :-----:       | :-----: | :-----:
| [http://techline-ltd.com/](http://techline-ltd.com/)      | 48/100                 | 36/100                 | 3,2s          | 2MB       |   38
| [http://techline-ltd.com/techlift500/](http://techline-ltd.com/techlift500/)      | 41/100               |   11/100     | 16,7s          | 5,1MB       |   55
| [http://techline-ltd.com/contact/](http://techline-ltd.com/contact/)  | 64/100               |   48/100     | 4,5s          | 2,4MB       |   113

###Förbättringar:
Bilderna behöver kraftigt komprimeras. En reduktion i storlek på upp till 88% är möjlig
med rätt metoder. Varken JS, HTML eller CSS är minifierad - något som skulle minska
storleken för dessa filer. Svarstiden från servern är något långsam.

Stocksnap.io
---------------------------------
[FIGURE src="image/stocksnap_home.png" class="center"]

###Mätningar:
| Sida                                          |PageSpeed Desktop Betyg |PageSpeed Mobile Betyg  | Medel laddtid | Storlek | Resurser
| :-------------                               |:-------------:         | :-----:                | :-----:       | :-----: | :-----:
| [https://stocksnap.io/](https://stocksnap.io/)      | 7/100                 | 4/100                 | 9,4s          | 64MB       |   529
| [https://stocksnap.io/view-photos/sort/trending/desc](https://stocksnap.io/view-photos/sort/trending/desc)      | 13/100               |   9/100     | 3,22s          | 5,5MB       |   77
| [https://stocksnap.io/popular](https://stocksnap.io/popular)  | 54/100               |   39/100     | 2,3s          | 3MB       |   181

###Förbättringar:
Det finns JavaScript kod som blockerar rendering av innehållet ovanför mitten innan
följande innehåll ha blivit renderat. Denna kod bör tas bort för att öka hastigheten
av renderingen. Bilderna kan optimeras för att laddas snabbare.

##Sammanfattining
Samtliga sidor fick relativt dåligt resultatn men bäst betyg av PageSpeed fick SF.se
Varför Stocksnap fick såpass dåligt betyg tror jag har att göra med att Stocksnap
har en oändlig scroll funktion. En viss mängd laddas på en gång, scrollar du sedan
ner laddas mer information in. Jag är osäker på hur PageSpeed hanterar detta.

Det fanns mycket gemensamt i form av förbättringar för sidorna. Samtliga sidor
kunde komprimera sina bilder bättre och samtliga har kod som blockerar rendering
av innehållet ovanför mitten. Absolut sämst gällande bildoptimering var TECHLINE,
sidan som jag själv gjort. När jag skapade sidan hade jag ingen respekt för att
minska ner storleken på bilderna, något som märks tydligt på resultatet. Sidan
är förhållandevis stor i relation till mängden material.

Jag anser att en hemsida idag inte bör ha längre ladd tid än 5 sekunder. Allt mer
än så upplevs som långsamt. Denna tid bör räknas till den punkt man kan börja använda
sidan och inte nödvändigtvis när att innehåll är laddat. Dom flesta sidor som jag
testat håller sig inom tidsramen, dom som inte klarar sig laddar på ett vis att
det ändå inte känns långsamt. Med undantag för Techline. Den är märkbart långsam,
för långsam och kommer troligtvis skrämma bort en del besökare.

Analysen är gjord av mig, Christopher Augustsson, ensam.

###Rangordning:
1. SF.se
2. stocksnap
3. Techline
