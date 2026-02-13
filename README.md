# Naturreservat-Sverige
Synka Wikidata och OSM 

Verkar som OSM kanske ligger efter WD och WD uppdateras vart 4:e år.... Öppna plattformar har sina svagheter

## SPARQL mot Wikidata
* [Wikidata med koppling OSM eller ej](https://query.wikidata.org/embed.html#%23title%3ANaturreservat%20i%20Sverige%20%E2%80%93%20har%20OSM%20rel%2C%20OSM%20way%2C%20saknar%0A%23defaultView%3AMap%7B%22layer%22%3A%22%3Fmarker%22%2C%20%22hide%22%3A%5B%22%3Fcoord%22%5D%7D%0ASELECT%20%3Fitem%20%3FitemLabel%20%3FitemDescription%20%3Fcoord%20%3Fmarker%20%3Fnrvid%20%3Fwww%20%3Fimage%20%3Fnrv%20%3FOSM%20%3FosmMap%20WHERE%20%7B%0A%20%20%3Fitem%20wdt%3AP31%20wd%3AQ179049%3B%20%20%20%23%20naturreservat%0A%20%20%20%20%20%20%20%20wdt%3AP17%20wd%3AQ34%3B%20%20%20%20%20%20%20%23%20Sverige%0A%20%20%20%20%20%20%20%20wdt%3AP625%20%3Fcoord.%20%20%20%20%20%20%23%20koordinat%20kr%C3%A4vs%20f%C3%B6r%20karta%0A%0A%20%20OPTIONAL%20%7B%20%3Fitem%20wdt%3AP402%20%3FOSMrelid.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Fitem%20wdt%3AP10689%20%3FOSMwayid.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Fitem%20wdt%3AP3613%20%3Fnrvid.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Fitem%20wdt%3AP856%20%3Fwww.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Fitem%20wdt%3AP18%20%3Fimage.%20%7D%0A%20%20MINUS%20%7B%20%3Fitem%20wdt%3AP576%20%3Fdissolved.%20%7D%0A%20%20%0A%0A%20%23%20trel%C3%A4ges-logik%0A%20%20BIND%28%0A%20%20%20%20IF%28BOUND%28%3FOSMrelid%29%2C%0A%20%20%20%20%20%20%20%22OSM%20relation%22%2C%0A%20%20%20%20%20%20%20IF%28BOUND%28%3FOSMwayid%29%2C%0A%20%20%20%20%20%20%20%20%20%20%22OSM%20way%22%2C%0A%20%20%20%20%20%20%20%20%20%20%22Saknar%20OSM%22%0A%20%20%20%20%20%20%20%29%0A%20%20%20%20%29%20AS%20%3Fmarker%0A%20%20%29%0A%20BIND%28URI%28CONCAT%28%22https%3A%2F%2Fwww.openstreetmap.org%2Frelation%2F%22%2C%3FOSMrelid%29%29%20AS%20%3FOSM%29%0A%20BIND%28URI%28CONCAT%28%22https%3A%2F%2Fwww.openstreetmap.org%2Fway%2F%22%2C%3FOSMwayid%29%29%20AS%20%3FOSM%29%0A%20BIND%28URI%28CONCAT%28%22https%3A%2F%2Fskyddadnatur.naturvardsverket.se%2Fsknat%2F%3Fnvrid%3D%22%2C%3Fnrvid%29%29%20AS%20%3Fnrv%29%0A%0A%20%20%23%20lat%2Flon%20fr%C3%A5n%20koordinat%0A%20%20BIND%28geof%3Alongitude%28%3Fcoord%29%20AS%20%3Flon%29%0A%20%20BIND%28geof%3Alatitude%28%3Fcoord%29%20AS%20%3Flat%29%0A%20%20%23%20OSM-l%C3%A4nk%20endast%20om%20b%C3%A5da%20saknas%0A%20%20BIND%28%0A%20%20%20%20IF%28%0A%20%20%20%20%20%20%21BOUND%28%3FOSMrelid%29%20%26%26%20%21BOUND%28%3FOSMwayid%29%2C%0A%20%20%20%20%20%20URI%28CONCAT%28%0A%20%20%20%20%20%20%20%20%22https%3A%2F%2Fwww.openstreetmap.org%2Findex.html%3Fmlat%3D%22%2C%0A%20%20%20%20%20%20%20%20STR%28%3Flat%29%2C%0A%20%20%20%20%20%20%20%20%22%26mlon%3D%22%2C%0A%20%20%20%20%20%20%20%20STR%28%3Flon%29%2C%0A%20%20%20%20%20%20%20%20%22%26zoom%3D11%22%0A%20%20%20%20%20%20%29%29%2C%0A%20%20%20%20%20%20%22%22%0A%20%20%20%20%29%20AS%20%3FosmMap%0A%20%20%29%0A%20%20%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%0A%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22sv%2Cen%22.%0A%20%20%7D%0A%7D%0A)

<img width="1041" height="853" alt="image" src="https://github.com/user-attachments/assets/ff3201d4-0bb5-42c2-b4b5-c200681e7320" />

## OSM Forum
* "[Naturreservat - Wikidata skall uppdateras dvs. ladda upp nya](https://community.openstreetmap.org/t/naturreservat-wikidata-skall-uppdateras-dvs-ladda-upp-nya/141400)"

<img width="1309" height="834" alt="image" src="https://github.com/user-attachments/assets/e9be33d3-358e-486d-8874-6b43bea638bf" />

## Länkröta Wikipedia - Sverige Naturreservat   > 11 000 länkar pekar på site som upphörde för flera år sedan
* [#67](https://github.com/salgo60/SCB-Wikidata/issues/67)
* [links_nvpub_v1_2026_02_09.html](https://salgo60.github.io/SCB-Wikidata/notebook/resultsNvpub/links_nvpub_v1_2026_02_09.html)

<img width="1527" height="774" alt="image" src="https://github.com/user-attachments/assets/0c65b48e-c0c5-4f39-b06a-c032a8535f4a" />

<img width="1510" height="718" alt="image" src="https://github.com/user-attachments/assets/9dd89c0b-5353-469f-b747-55393aa8b1c6" />

## Test modul [Extension:Kartographer](https://www.mediawiki.org/wiki/Help:Extension:Kartographer) Wikipedia Sthlm
<img width="1431" height="844" alt="image" src="https://github.com/user-attachments/assets/b1ebf774-a291-4979-ba15-2537471d92fe" />

'''
<mapframe text="text" latitude="59.3" longitude="18.5" zoom="8" width="900" height="900">

[{  "type": "ExternalData",
  "service": "geoshape",
  "query": "SELECT * WHERE { ?id wdt:P31 wd:Q179049;wdt:P131/wdt:P131 wd:Q104231 .}"
  } 
]
</mapframe>
''' 

**wdt:P17 Q34**

<img width="913" height="861" alt="image" src="https://github.com/user-attachments/assets/6c34805b-9111-465f-ad3b-6f437a55e370" />


* För Stockholm Archipelago Trail gjordes en karta som denna klickbara för att navigera mellan olika delar av Wikicommons / Wikipedia se exmpel [Template:StockholmArchipelagoTrailMapSparql](https://commons.wikimedia.org/wiki/Template:StockholmArchipelagoTrailMapSparql)

### Test Links
* [Sandbox](https://sv.wikipedia.org/wiki/Anv%C3%A4ndare:Salgo60/sandl%C3%A5da#/map/0)

<img width="859" height="664" alt="image" src="https://github.com/user-attachments/assets/b6714607-6343-44b2-a838-d05b9f38116d" />

#### Code added 
Its rader unstable but works 
* should be SPARQL in one line
* check usage of characters...
* ?title ?description is the text in the popup

'''
<mapframe text="Naturreservat i Stockholms län med popup och länk" latitude="59.3" longitude="18.5" zoom="8" width="900" height="900">
[{ "type":"ExternalData","service":"geoshape","query":"SELECT DISTINCT ?id (?idLabel AS ?title) ?description ('small' AS ?marker_size) ('#228b22' AS ?marker_color) ('park' AS ?marker_symbol) WHERE { ?id wdt:P31 wd:Q179049; wdt:P131/wdt:P131 wd:Q104231. OPTIONAL{?id wdt:P18 ?img} OPTIONAL{?id wdt:P373 ?commons} OPTIONAL{?sitelink schema:about ?id; schema:isPartOf <https://sv.wikipedia.org/>} BIND(IF(BOUND(?commons),CONCAT('[[c:Category:',?commons,']]\\n'),'') AS ?d1) BIND(IF(BOUND(?img),CONCAT(?d1,'[[File:',SUBSTR(STR(?img),52,400),'{{!}}200px]]\\n'),?d1) AS ?d2) BIND(IF(BOUND(?sitelink),CONCAT(?d2,'[[:sv:',REPLACE(STR(?sitelink),'^.*wiki/',''),']]'),?d2) AS ?description) SERVICE wikibase:label { bd:serviceParam wikibase:language 'sv,en'. } }"}]
</mapframe>
'''
##### SPARQL
'''
SELECT DISTINCT
  ?id
  (?idLabel AS ?title)
  ?description
  ('small' AS ?marker_size)
  ('#228b22' AS ?marker_color)
  ('park' AS ?marker_symbol)

WHERE {
  # Nature reserves in Stockholm County
  ?id wdt:P31 wd:Q179049;          # instance of nature reserve
      wdt:P131/wdt:P131 wd:Q104231. # located in Stockholm County

  # Optional data
  OPTIONAL { ?id wdt:P18 ?img }       # image
  OPTIONAL { ?id wdt:P373 ?commons }  # Commons category
  OPTIONAL {
    ?sitelink schema:about ?id;
              schema:isPartOf <https://sv.wikipedia.org/>
  }

  # Popup description builder
  BIND(
    IF(
      BOUND(?commons),
      CONCAT('[[c:Category:', ?commons, ']]\n'),
      ''
    ) AS ?d1
  )

  BIND(
    IF(
      BOUND(?img),
      CONCAT(
        ?d1,
        '[[File:',
        SUBSTR(STR(?img), 52, 400),
        '{{!}}200px]]\n'
      ),
      ?d1
    ) AS ?d2
  )

  BIND(
    IF(
      BOUND(?sitelink),
      CONCAT(
        ?d2,
        '[[:sv:',
        REPLACE(STR(?sitelink), '^.*wiki/', ''),
        ']]'
      ),
      ?d2
    ) AS ?description
  )

  # Labels in Swedish first, then English
  SERVICE wikibase:label {
    bd:serviceParam wikibase:language "sv,en"
  }
}
'''

* Property	Meaning
  * P18	Image
  * P373	Wikimedia Commons category
  * svwiki sitelink	Link to Swedish Wikipedia article


**🧱 Popup construction logic**

The popup text is built step-by-step:

Step 1 — Commons link
[[c:Category:...]]


Adds a link to the Commons category.

**Step 2 — Image**
[[File:...|200px]]

Displays a 200px image in the popup.

SUBSTR extracts the filename from the Commons URL.

Step 3 — Swedish Wikipedia link
[[:sv:Article]]

