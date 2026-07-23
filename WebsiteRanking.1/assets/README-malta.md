# Malta — Unsere Spots

Eine kleine Website, auf der wir sechs Orte auf Malta nach unseren
eigenen Kriterien bewerten. Entstanden während einer Reise im
Sommer 2026.

## Über das Projekt

Jeder Ort wird in drei Kategorien auf einer Skala von 1 bis 5 bewertet:

| Kategorie | Bedeutung |
| --- | --- |
| **Aussehen** | Wie schön der Ort ist (bei Restaurants: **Essen**) |
| **Erreichbarkeit** | Wie leicht man hinkommt |
| **Andrang** | Wie voll es ist |

> **Wichtig:** Bei *Andrang* ist mehr **nicht** besser. Ein hoher Wert
> bedeutet, dass viel los ist. Deshalb ist diese Kategorie auf der
> Seite auch optisch anders dargestellt — mit schraffierter Leiste und
> in einem warnenden Terrakotta-Ton.

## Die bewerteten Orte

| Ort | Aussehen | Erreichbarkeit | Andrang |
| --- | :---: | :---: | :---: |
| St. Peter's Pool | 4,5 | 3 | 4 |
| Valletta | 5 | 5 | 2 |
| Mamma Mia *(Essen)* | 4,5 | 5 | 3 |
| Las Palmas | 4 | 3 | 2 |
| Blue Lagoon | 5 | 1 | 2,5 |
| Popeye Village | 5 | 2 | 2 |

## Design

Cleaner, an Apple angelehnter Look mit Weiß und Beige als
Primärfarben. Viel Weißraum, zurückhaltende Typografie
(**Fraunces** für Überschriften, **Inter** für den Fließtext) und
weiche Schatten.

Farbpalette:

- `#ffffff` Weiß
- `#f4efe6` Beige (Seitenhintergrund)
- `#fbf9f5` Kartenflächen
- `#1d1d1f` Text

## Struktur

```
.
├── index.html
└── css/
    └── styles.css
```

Es gibt keine Build-Tools, kein Framework und keine Abhängigkeiten —
reines HTML und CSS. Die Schriften werden über Google Fonts geladen.

## Lokal starten

Das Repository klonen und `index.html` im Browser öffnen. Mehr ist
nicht nötig.

```bash
git clone https://github.com/<dein-name>/<repo-name>.git
cd <repo-name>
open index.html          # macOS
# oder: start index.html  (Windows)
```

## Auf GitHub Pages veröffentlichen

1. Repository auf GitHub anlegen und den Code pushen.
2. Im Repo auf **Settings → Pages** gehen.
3. Unter *Source* den Branch `main` und den Ordner `/ (root)` wählen.
4. Speichern — die Seite ist nach kurzer Zeit unter
   `https://<dein-name>.github.io/<repo-name>/` erreichbar.

## Bilder

Aktuell nutzt die Seite eingebaute SVG-Grafiken als Platzhalter. Sie
sind direkt im HTML enthalten und laden immer, auch offline.

Um eigene Fotos einzusetzen, legst du einen Ordner `img/` an und
ersetzt den jeweiligen `<svg class="ph">…</svg>`-Block durch:

```html
<img src="img/st-peters.jpg" alt="St. Peter's Pool" loading="lazy" />
```

Das CSS ist bereits so geschrieben, dass `<img>` und `<svg>` die
Bildfläche gleichermaßen ausfüllen — am Styling musst du nichts
ändern.

## Anpassen

**Bewertung ändern:** Jede Leiste besteht aus einem Zahlenwert und
einer Breitenangabe. Beide müssen zusammenpassen (Breite = Wert ÷ 5):

```html
<span class="meter meter--look" style="--v:90%"><span></span></span>
<b>4,5</b><i>/5</i>
```

**Neuen Ort ergänzen:** Einen kompletten `<article class="spot">`-Block
kopieren, Texte und Werte anpassen und die Nummer in
`spot__index` hochzählen.

**Farben ändern:** Alle Farben stehen als CSS-Variablen ganz oben in
`css/styles.css` unter `:root`.

## Lizenz

Privates Reiseprojekt. Die Bewertungen sind unsere persönliche
Meinung.
