# Relaunch muldenschloesschen.de – Gesamtplan

Stand: 15.10.2026 · Projekt: `muldenschloesschen-web` (eigenständig, getrennt vom PMS)

Ziel: Eine neue Website im Glass-/Pixel-UI der neuen Buchungsmaschine, die in wenigen Sekunden klar macht, **warum genau das Muldenschlösschen** – und die Besucher ohne Reibung in die Buchung führt. Sie muss bei Google und in KI-Suchen (Google AI Overviews/AI Mode, ChatGPT Search, Perplexity, Gemini, Copilot) für die relevanten Suchanfragen sichtbar sein.

---

## 1. Ausgangslage (Audit der bestehenden Seite)

### 1.1 Was die alte Seite gut macht
- Viel echter, regionaler Inhalt: Touren mit Kilometer- und Höhenangaben, Lutherweg-Etappe, Kanustrecke, Schlösser mit Entfernungen, Honesty Bar, Fahrradgarage mit E-Bike-Laden.
- Eigene, hochwertige Medien: Drohnenvideos (Rochsburg, Haus, Terrasse), Zimmer-, Frühstücks- und Regionsfotos, Burg-Icons.
- URLs mit Suchbegriffen (`/schloss-rochsburg/`, `/radfahren/`, `/wandern/` …) und brauchbare Meta-Beschreibungen (Rank Math).

### 1.2 Probleme, die der Relaunch beheben muss

| Bereich | Befund | Folge |
|---|---|---|
| Recht | Kein Impressum, keine Datenschutzerklärung (`/impressum`, `/datenschutz` = 404). Google Fonts und Komoot-Embeds laden ohne Einwilligung. | Abmahnrisiko (DDG § 5, DSGVO). **Höchste Priorität.** |
| Recht | Mehrfach identische, generisch wirkende Testimonials („Anna Müller“, „Thomas Becker“, „Maximilian Schmidt“ …) auf verschiedenen Seiten. | Nicht verifizierbare Bewertungen sind nach UWG § 5b unzulässig. Nicht übernehmen. |
| Inhalt | Startseite und Wandern/Wasser bewerben Restaurant, Sonntagsbraten, Rinderroulade, Hochzeiten bis 110 Gäste. Die Frühstücksseite sagt: **keine warme Abendküche mehr**. | Widersprüchliche Erwartungen, enttäuschte Gäste, schlechte Bewertungen. |
| Inhalt | Entfernung zum Schloss mal 400 m, 450 m, 550 m, 650 m. | Unglaubwürdig, für KI-Antworten unbrauchbar. Einmal messen, überall gleich verwenden. |
| Inhalt | Großteil der Termine (Jan.–Okt. 2026, „März-Spezial“) ist vorbei. | Veraltet wirkende Seite, schlechtes Qualitätssignal. |
| NAP | Drei Telefonnummern: 03075-425098 (Kontakt), +49 162 9115038 (Footer), +49 37383 159781 (Schema, Tourismusverband). Adresse im Schema „Bahnhoh**straße**“, Ort „Rochsburg“ statt „Lunzenau OT Rochsburg“. | Uneinheitliche NAP-Daten schwächen Local SEO und die Entitätserkennung in KI-Systemen. |
| Navigation | Links auf `/hotel`, `/restaurant` (404), `/unterseiteErsetzen` (Platzhalter), `${article.buttonLink}` (kaputtes Template). | Crawl-Fehler, Vertrauensverlust. |
| Barrierefreiheit | `maximum-scale=1.0, user-scalable=0` verhindert Zoomen. | WCAG-Verstoß, mobile Usability. |
| Technik | WordPress + Divi 5 **Alpha**, 45 Script-Tags, ~240 KB HTML, TTFB ≈ 1,1 s. | Schwache Core Web Vitals, Sicherheits- und Wartungsrisiko. |
| Schema | Nur `Organization`/`Place`, kein `Hotel`/`BedAndBreakfast`, keine Geo-Koordinaten, keine Ausstattung. | Verschenkte Entitätsinformationen. |
| Buchung | Externer Absprung zu RoomRaccoon (`booking.roomraccoon.de`), ohne vorbelegte Daten. | Medienbruch, Conversion-Verlust, kein sauberes Tracking. |

### 1.3 Reputation (öffentliche Bewertungen, Stand Recherche)
- Tripadvisor: 4,4/5 (29 Bewertungen) – „hidden gem“, Schlossblick beim Frühstück, „der Juniorchef ist ein lebendiger Reiseführer“.
- HolidayCheck: 5,7/6, 100 % Weiterempfehlung (18 Bewertungen).
- Booking.com: 7,3/10 (239 Bewertungen) – Lage 8,6, Personal 8,7, Ausstattung 7,2. **Schwachpunkt**, siehe Abschnitt 9.

---

## 2. Positionierung: Warum das Muldenschlösschen?

Kernversprechen (Hero, ein Satz):
> **Aufwachen mit Blick auf Schloss Rochsburg – Ihr familiengeführtes B&B direkt an der Zwickauer Mulde.**

Die fünf Gründe (in dieser Reihenfolge, je max. 12 Wörter auf der Seite):

1. **Schlossblick** – Zimmer mit Blick auf die Rochsburg, zu Fuß über die Hängebrücke ins Schloss.
2. **Direkt am Mulderadweg** – Abschließbare Fahrradgarage, E-Bike-Laden und Reparaturset kostenlos.
3. **Basislager statt Kofferpacken** – Sieben Schlösser, Lutherweg und Kanustrecken in kurzer Fahrt erreichbar.
4. **Frühstück mit Aussicht** – Regional, liebevoll angerichtet, auf der Terrasse über der Mulde. Abends Honesty Bar.
5. **Persönlich** – Familiengeführt, Gastgeber mit echten Tourentipps aus der Region.

Zielgruppen (Priorität nach Buchungswert und Suchvolumen):

| Segment | Auslöser | Einstiegsseite |
|---|---|---|
| Paare / Kurzurlaub | Romantik, Schloss, Ruhe | Startseite, `/schloss-rochsburg/` |
| Radreisende (Etappe oder Sterntouren) | Mulderadweg, E-Bike | `/radfahren/` |
| Kultur- und Schlösserfans | Tal der Burgen, Colditz, Schlösserland-Karte | `/schloesser/` |
| Wanderer und Pilger | Lutherweg, Hängebrücke | `/wandern/` |
| Event-Besucher | Veranstaltungen auf der Rochsburg, Schokoladenfestival, Heavy24 | `/veranstaltungen/` |
| Familien / Aktive | Kanu, Schlauchboot, Stausee | `/wasser/` |

---

## 3. Content-Strategie: Was bleibt, was fliegt

### 3.1 Übernehmen (überarbeitet, gekürzt)
- Zimmer: 15 individuelle Zimmer (Einzel/Doppel), Kategorie **Schlossblick**, Ruhe, Flussrauschen.
- Frühstück: ofenfrische Brötchen, hausgemachte Marmeladen, regionale Käse- und Wurstspezialitäten, kein Massenbuffet, Terrasse mit Blick.
- Honesty Bar (ab 14 Uhr): regionale Biere, Limonaden, Wein, Whisky, Snacks.
- Restaurant-Empfehlungen für den Abend (Biergarten 300 m, Gartencafé Schievelbein 300 m, Chichetto Lunzenau, Rollmopsschänke Penig, Höllmühle Chursdorf, Paros Penig) – als ehrliche Lösung für „keine Abendküche“.
- Rad: Fahrradgarage, E-Bike-Ladestationen, Reparaturset; Touren „Burgen-Trilogie“ (ca. 45 km, flach), „Rochlitzer Bergkönig“ (ca. 70 km, 800 hm), „Hidden Trails & Bridges“ (ca. 35 km, S1); Komoot-Sammlungen.
- Wandern: Hängebrücke, Lutherweg Etappe 18 (Wechselburg–Penig), Muldentalweg, Göhrener Viadukt, Ortsteil „Amerika“, Bus 629 als Rückweg.
- Wasser: Kanu Wechselburg–Rochlitz (8 km), Schlauchboot ab 8 Personen, SUP/Tretboot Stausee Oberwald und Glauchau.
- Schlösser: Rochsburg, Rochlitz, Colditz, Wolkenburg, Waldenburg, Lichtenwalde, Augustusburg (+ Burg Kriebstein) mit Entfernung und Fahrzeit; Tipp Schlösserland-Karte; Routen Nord/Süd/Ost.
- Mehrtagesprogramme als **zeitlose** Vorlagen („3 Tage Burgen, Bohnen & Barock“, „Mulde-Klassiker Paddeln & Genießen“, „Historisches Wochenende“).
- Hausgeschichte: Errichtet um 1920, herrschaftliches Anwesen, liebevoll restauriert.
- Echte, belegbare Bewertungen (Google, HolidayCheck, Tripadvisor) mit Quelle und Datum.

### 3.2 Streichen
- Alles zu Restaurant, Abendessen, Sonntagsbraten, Rinderroulade, Café/Eisbecher, Tagungsraum, Hochzeiten bis 110 Gäste – **sofern der Betreiber nicht bestätigt, dass es das noch gibt** (offene Frage).
- Abgelaufene Termine 2026 und alle „März-Spezial“-Texte mit Datumsbezug.
- Platzhalter- und nicht belegbare Testimonials.
- Generische Fülltexte (z. B. „Wasser ist nicht nur ein Element …“, „Unsere Philosophie und Vision“ des Restaurants).
- Unsichere Angaben („falls existent“, „wahrscheinlich kostenlos“).

### 3.3 Schreibregeln
- **Answer first:** Jeder Abschnitt beginnt mit einer direkten Antwort in 40–60 Wörtern (gut für Nutzer, Featured Snippets und KI-Zitate), danach Details.
- Konkrete Zahlen statt Adjektive: „400 m Fußweg“, „15 Zimmer“, „E-Bike-Laden kostenlos“.
- Einheitliche Begriffe: „Das Muldenschlösschen – B&B am Schloss Rochsburg“, „Lunzenau OT Rochsburg“.
- Sie-Form durchgehend (die alte Seite mischt Du/Sie/Ihr).
- Kein Fakt nur im Bild: Alles, was zählt, steht als HTML-Text auf der Seite.

---

## 4. Informationsarchitektur und URLs

Bestehende, rankende URLs bleiben erhalten (keine Rankingverluste). Neue Seiten nur, wo ein klarer Suchintent besteht.

| URL | Seite | Primäres Keyword-Cluster | Status |
|---|---|---|---|
| `/` | Startseite (Landing, Conversion) | Muldenschlösschen, Hotel/B&B Rochsburg, Übernachtung Muldental | neu gestaltet |
| `/zimmer/` | Zimmer & Preise (Daten aus Buchungsmaschine) | Zimmer Schlossblick, Hotelzimmer Lunzenau | **neu** |
| `/b-and-b-uebernachtung-rochsburg/` | Das Haus, Geschichte, Gastgeber | B&B Rochsburg, Pension Lunzenau | beibehalten |
| `/fruehstueck-rochsburg/` | Frühstück, Honesty Bar, Abend-Tipps | Frühstück mit Schlossblick | beibehalten |
| `/schloss-rochsburg/` | Hub Schloss Rochsburg (Anreise zu Fuß, Museum, Choco del Sol) | Schloss Rochsburg Übernachtung/Hotel | beibehalten |
| `/schloesser/` | Tal der Burgen: 7 Schlösser, Karte, Routen | Schlösser Muldental, Tal der Burgen | beibehalten |
| `/radfahren/` | Mulderadweg, Touren, Fahrradgarage | Mulderadweg Unterkunft, Radurlaub Sachsen | beibehalten |
| `/wandern/` | Lutherweg, Hängebrücke, Muldentalweg | Wandern Muldental, Lutherweg Sachsen | beibehalten |
| `/wasser/` | Kanu, Schlauchboot, SUP | Kanu Zwickauer Mulde | beibehalten |
| `/veranstaltungen/` | Termine Region (Datenfile, abgelaufene blenden sich aus) | Schloss Rochsburg Veranstaltungen 2027 | **neu** |
| `/anreise/` | Lage, Anreise Auto/Bahn/Rad, Parken, Entfernungen | Anreise Rochsburg | **neu** |
| `/faq/` | Häufige Fragen | (Long Tail, KI-Fragen) | **neu** |
| `/kontakt/` | Kontakt, Formular | Muldenschlösschen Kontakt | beibehalten |
| `/agb/`, `/impressum/`, `/datenschutz/` | Rechtliches | – | Impressum/Datenschutz **neu** |

301-Weiterleitungen: `/hotel` → `/`, `/restaurant` → `/fruehstueck-rochsburg/`, `/unterseiteErsetzen` → `/`, `/feed/`, `/comments/feed/`, `/xmlrpc.php`, `/wp-json/*` → `410` bzw. `/`. Alte Upload-Pfade `/wp-content/uploads/*` für Bilder, die in der Bildersuche ranken, auf die neuen Bild-URLs weiterleiten (Mapping-Datei).

Sprachen: Launch auf Deutsch. Phase 2: Englisch (Colditz und Mulderadweg ziehen internationale Gäste an; Tripadvisor-Bewertungen sind teilweise englisch), danach optional Niederländisch. Mit `hreflang`.

---

## 5. Keyword-Recherche

Hinweis: Absolute Suchvolumina müssen vor dem Launch mit Google Keyword Planner bzw. Search Console der alten Seite validiert werden (Werkzeuge hier nicht verfügbar). Die Priorisierung folgt Suchintent, Wettbewerb (wenige, schwache lokale Mitbewerber: Villa Rochsburg, Zur Lochmühle, Zum Zuber) und Buchungsnähe.

### 5.1 Cluster und Priorität

**A – Transaktional lokal (höchste Priorität, direkte Buchungen)**
- hotel rochsburg · übernachtung rochsburg · pension rochsburg
- hotel lunzenau · pension lunzenau · unterkunft lunzenau
- hotel penig · übernachtung penig · unterkunft rochlitz · hotel rochlitz umgebung
- b&b sachsen · bed and breakfast mittelsachsen · hotel muldental · pension muldental
- hotel zwischen chemnitz und leipzig · hotel mit schlossblick sachsen

**B – Schloss Rochsburg (stärkster Alleinstellungsanker)**
- schloss rochsburg übernachtung · hotel schloss rochsburg · schloss rochsburg hotel in der nähe
- schloss rochsburg veranstaltungen · schloss rochsburg öffnungszeiten (informational, hoher Traffic – mit Verweis auf offizielle Seite)
- hängebrücke rochsburg · choco del sol rochsburg · schokoladenfestival rochsburg · irische nacht rochsburg

**C – Rad**
- mulderadweg unterkunft · mulderadweg übernachtung · mulderadweg etappen · zwickauer mulde radweg
- bett und bike sachsen (nur bei Zertifizierung) · hotel mit fahrradgarage · e-bike ladestation hotel sachsen
- radurlaub sachsen · radtour schlösser sachsen · mtb rochlitzer berg · heavy24 übernachtung

**D – Schlösser & Kultur**
- tal der burgen sachsen · schlösser muldental · burgen und schlösser mittelsachsen
- schloss colditz übernachtung · schlösserland karte · ausflugsziele mittelsachsen
- kurzurlaub sachsen schlösser · wochenende sachsen romantik

**E – Wandern & Pilgern**
- lutherweg sachsen etappe wechselburg penig · lutherweg unterkunft · wandern muldental · muldentalweg
- göhrener viadukt wandern · amerika penig

**F – Wasser**
- kanu zwickauer mulde · paddeln mulde wechselburg rochlitz · schlauchboot mulde · stausee oberwald

**G – Marke & Navigation**
- muldenschlösschen · muldenschlösschen rochsburg · muldenschlösschen lunzenau · das muldenschlösschen bewertungen

### 5.2 Fragen für FAQ und KI-Suche (konversationelle Long-Tail-Anfragen)
- Wo übernachtet man am besten bei Schloss Rochsburg?
- Wie weit ist es vom Muldenschlösschen zum Schloss Rochsburg zu Fuß?
- Welche Unterkunft am Mulderadweg hat eine Fahrradgarage mit E-Bike-Ladestation?
- Welche Schlösser kann man von Rochsburg aus an einem Tag besuchen?
- Gibt es im Muldenschlösschen Abendessen? (ehrliche Antwort + Empfehlungen)
- Ab wann ist Check-in, bis wann Check-out? Gibt es Parkplätze? Sind Hunde erlaubt?
- Wie komme ich ohne Auto nach Rochsburg? (Bahn/Bus 629)
- Lohnt sich die Schlösserland-Karte im Muldental?

### 5.3 Zuordnung
Jedes Keyword-Cluster hat genau **eine** Zielseite (keine Kannibalisierung). Title-Muster: `Primärkeyword – Nutzen | Das Muldenschlösschen` (≤ 60 Zeichen). Meta-Description mit Nutzen + Handlungsaufforderung (≤ 155 Zeichen), Emojis sparsam.

---

## 6. SEO-Technik (Stand 2026)

### 6.1 Fundament
- Statisch vorgerenderte Seiten (SSG): alle Inhalte im initialen HTML, keine Abhängigkeit von JavaScript für Text, Links, Preise-Fallback.
- Core-Web-Vitals-Ziele (Feld-Daten, 75. Perzentil, mobil): **LCP < 2,0 s, INP < 200 ms, CLS < 0,05**. JS-Budget Startseite < 60 KB komprimiert (ohne optionales Hero-WebGL, das nach LCP lädt).
- Bilder: AVIF/WebP, responsive `srcset`, feste Seitenverhältnisse, `fetchpriority="high"` nur für das LCP-Bild, sprechende Dateinamen und Alt-Texte, Bild-Sitemap.
- Video: Poster-Bild als LCP, Video erst nach LCP und nur bei ausreichender Verbindung (`navigator.connection`), stumm, `playsinline`, kein Autoplay bei `prefers-reduced-motion`.
- Eine H1 pro Seite, logische Überschriftenhierarchie, Breadcrumbs.
- Canonical, XML-Sitemap (Seiten + Bilder), `robots.txt`, saubere 404-Seite mit Buchungs-CTA, konsistenter Trailing Slash.
- Interne Verlinkung: Jede Aktivitätsseite verlinkt Zimmer + Buchung + zwei verwandte Aktivitäten; die Startseite verlinkt alle Hubs.

### 6.2 Strukturierte Daten (JSON-LD, serverseitig, deckungsgleich mit sichtbarem Text)
- `BedAndBreakfast` (Untertyp von `LodgingBusiness`) mit Name, Adresse (Bahnhofstraße 2, 09328 Lunzenau OT Rochsburg), `geo`, Telefon, E-Mail, `checkinTime`/`checkoutTime`, `numberOfRooms: 15`, `priceRange`, `amenityFeature` (kostenfreies Parken, WLAN, Fahrradgarage, E-Bike-Ladestation, Terrasse, Honesty Bar), `petsAllowed`, `image`, `sameAs` (Google-Profil, Booking.com, Tripadvisor, HolidayCheck, Social Media), `potentialAction: ReserveAction` mit Ziel-URL der Buchungsmaschine.
- `HotelRoom` + `Offer` auf `/zimmer/` (Daten aus Buchungsmaschinen-API).
- `BreadcrumbList` auf allen Unterseiten.
- `TouristAttraction`/`ItemList` für die Schlösser, `TouristTrip` für Mehrtagesprogramme.
- `Event` nur für kommende Termine mit gesicherten Daten (abgelaufene fliegen automatisch raus).
- `FAQPage` als Auszeichnung der sichtbaren FAQ (Rich Results gibt es dafür kaum noch, hilft aber der Entitätszuordnung).
- **Kein** `AggregateRating` für eigene Bewertungen (Google zeigt selbst ausgezeichnete Bewertungen bei LocalBusiness nicht an; Risiko einer manuellen Maßnahme).

### 6.3 Local SEO
- NAP vereinheitlichen (eine Telefonnummer!) auf Website, Google-Unternehmensprofil, Booking, Tripadvisor, HolidayCheck, Tourismusverband Rochlitzer Muldental, Bett+Bike, Apple Maps, Bing Places.
- Google-Unternehmensprofil: Kategorie „Bed & Breakfast“ (+ „Hotel“), Attribute (Parken, WLAN, Fahrradfreundlich), aktuelle Fotos, Fragen & Antworten mit denselben Formulierungen wie die FAQ.
- **Google Hotel Center / kostenlose Buchungslinks** über die Buchungsmaschine bzw. den Channel-Manager des PMS anbinden – Direktbuchung direkt aus Google Maps/Hotels.
- Lokale Backlinks: Rochlitzer Muldental e. V., Schlösserland Sachsen, Mulderadweg-Portal, Lutherweg Sachsen, Komoot-Sammlungen, Choco del Sol, Schloss Rochsburg, Veranstalter (Heavy24, Kanuverleih).

### 6.4 KI-Suchmaschinen (GEO/AEO)
Faktenlage 2026: Für Google AI Overviews/AI Mode gibt es keine Sonder-Optimierung – es zählt gutes SEO plus Zugänglichkeit. KI-Zitate hängen an **sichtbaren, eindeutigen, belegbaren Fakten**, nicht an Markup-Tricks.
- **Crawler-Zugang:** `robots.txt` erlaubt Googlebot, Bingbot, `OAI-SearchBot`, `ChatGPT-User`, `PerplexityBot`, `Claude-SearchBot`/`ClaudeBot`, `Applebot`. Entscheidung zu Trainings-Bots (`GPTBot`, `Google-Extended`, `CCBot`) bewusst treffen (Empfehlung: erlauben – Sichtbarkeit vor Schutz). CDN/WAF so konfigurieren, dass deklarierte Crawler keine 403/Challenges bekommen (der aktuelle RoomRaccoon-Link liefert z. B. 403 an Nicht-Browser).
- **Bing Webmaster Tools + IndexNow** (Bing speist Copilot und Teile von ChatGPT Search).
- **„Auf einen Blick“-Faktenblock** auf Start- und Zimmerseite: Lage, Zimmeranzahl, Check-in/-out, Frühstückszeiten und -preis, Parken, Haustiere, Entfernungen (gemessen), Fahrradgarage, Kontakt. Als echte HTML-Tabelle/`<dl>`.
- **Eigene, zitierfähige Daten:** gemessene Entfernungen und Fahrzeiten zu allen Schlössern, Touren mit km/hm/Schwierigkeit und GPX-Download, Saisontipps. Solche einzigartigen Fakten werden bevorzugt zitiert.
- **E-E-A-T:** Gastgeber mit Name, Foto, kurzer Geschichte („Tourentipps vom Gastgeber“) – Bewertungen loben genau das.
- `llms.txt`: optional, kostet nichts, aber nachweislich ohne Wirkung auf Google – nicht als Maßnahme verkaufen.
- **Monitoring:** Monatlich feste Prompt-Liste (Fragen aus 5.2) in ChatGPT, Perplexity, Gemini, Google AI Mode, Copilot prüfen und Zitate protokollieren.

---

## 7. UX- und Conversion-Konzept

### 7.1 Leitprinzipien (aus Wahrnehmungs- und Usability-Forschung)
| Prinzip | Anwendung |
|---|---|
| Erster Eindruck in ~50 ms (Lindgaard et al.), 5-Sekunden-Test | Hero zeigt sofort Schloss + Fluss + Kernversprechen + Buchungsfeld. Ein Bild sagt „Schlossblick“, bevor jemand liest. |
| Scan-Muster (NN/g: F- und Layer-Cake-Pattern) | Kurze, aussagekräftige Zwischenüberschriften; Kernaussage immer links/oben im Abschnitt. |
| Hick’sches Gesetz | Eine primäre Handlung pro Ansicht: „Verfügbarkeit prüfen“. Sekundär nur „Anrufen“. |
| Fitts’sches Gesetz / Daumenzone | Mobil: fixierte Buchungsleiste unten, Ziele ≥ 44 × 44 px. |
| Von-Restorff-Effekt | Die CTA-Farbe kommt sonst nirgends vor. |
| Sozialer Beweis, Autorität (Cialdini) | Echte Bewertungen mit Quelle, Plattform-Bewertungen als Chips im Hero, ggf. Bett+Bike-Siegel. |
| Knappheit – nur echt | Live-Verfügbarkeit aus der Buchungsmaschine („Schlossblick-Zimmer am 13.–15.11.: noch 2 frei“). Keine erfundenen Countdown-Timer (UWG). |
| Verlustaversion / Direktbuchungsvorteil | Klar benennen, was Direktbucher bekommen (z. B. Bestpreis + Begrüßungsgetränk an der Honesty Bar – Entscheidung Betreiber). |
| Peak-End-Regel (Kahneman) | Starkes, emotionales Schlussbild mit konkreten freien Terminen statt eines generischen „Jetzt buchen“. |
| Kognitive Last / Progressive Disclosure | Details (Touren, Programme) in aufklappbaren Glass-Karten; die Startseite bleibt kurz. |
| Banner-Blindheit | Wichtige Fakten nie in banner-artigen Boxen, sondern im Fließ-Layout. |
| Zielgradient-Effekt | Buchungsmaschine zeigt Fortschritt; Website übergibt bereits gewählte Daten, damit Schritt 1 schon „erledigt“ ist. |

### 7.2 Startseite – Abschnitte in Reihenfolge
1. **Hero „Pixel zu Wirklichkeit“:** Vollflächiges Drohnenvideo der Rochsburg. Beim Laden setzt sich das Bild aus groben Pixeln zusammen und „löst sich auf“ in das echte Video (Mosaik-Shader). H1 + Unterzeile + **Glass-Buchungsleiste** (Anreise, Abreise, Gäste, „Verfügbarkeit prüfen“). Darunter Vertrauens-Chips: „Tripadvisor 4,4/5 · HolidayCheck 5,7/6 · Familiengeführt“.
2. **Warum wir – 5 Gründe** als Glass-Karten mit animierten Pixel-Icons (Burg, Fahrrad, Karte, Kaffeetasse, Hand).
3. **Zimmer mit Schlossblick:** „Blick aus dem Fenster“-Vergleich (Schieberegler Morgen/Abend), Ab-Preis live aus der API, CTA mit vorgewählter Kategorie.
4. **Basislager-Karte:** Interaktive Pixel-Art-Karte des Muldentals mit Muldenschlösschen in der Mitte, 7 Schlössern (vorhandene Burg-Icons im Pixel-Stil), Mulderadweg und Lutherweg. Tippen öffnet Glass-Karte mit Entfernung, Fahrzeit, Highlight und Link.
5. **Ein Tag bei uns:** Scroll-gesteuerte Zeitleiste – eine Pixel-Sonne wandert über die Zinnen der Rochsburg: Frühstück auf der Terrasse → Rad/Wandern/Kanu → Honesty Bar bei Sonnenuntergang.
6. **Für Radfahrer:** Fahrradgarage, E-Bike-Laden, Reparaturset; drei Touren als Karten mit km/hm; Komoot erst nach Klick (2-Klick-Lösung, DSGVO).
7. **Gäste sagen:** Echte Zitate mit Plattform und Datum; manuell blätterbar, kein Autoplay.
8. **„Auf einen Blick“ + FAQ** (6–8 Fragen, Antwort zuerst).
9. **Finale (Peak-End):** „Ihr Fenster zur Rochsburg ist noch frei“ + Chips der nächsten freien Wochenenden mit Preis (Live-API) → Klick öffnet Buchung mit vorbelegten Daten.
10. **Footer:** NAP, statische Karte (Klick → Maps), Anreise, Rechtliches.

### 7.3 Unterseiten-Muster (einheitlich)
Hero mit Answer-first-Absatz → 3–5 Kernfakten → Inhaltsblöcke (Touren/Schlösser/Programme) → „Passend dazu: Zimmer“ mit Live-Preis → FAQ zum Thema → CTA. Auf jeder Seite ist die Buchung **maximal einen Klick** entfernt.

### 7.4 Barrierefreiheit
WCAG 2.2 AA: Kontraste auch auf Glas (Hintergrund-Abdunklung hinter Text, mind. 4,5 : 1), Zoom erlaubt, Tastaturbedienung aller Karten/Slider, sichtbarer Fokus, `prefers-reduced-motion` schaltet alle Effekte auf statische Versionen, Untertitel/Transkript für Videos mit Inhalt, Alt-Texte. Das BFSG verpflichtet Kleinstunternehmen bei Dienstleistungen zwar nicht, wir erfüllen es trotzdem – auch weil die Buchungsmaschine darunter fallen kann, wenn sie von anderen Betrieben genutzt wird.

---

## 8. Design-System „Glass × Pixel“

### 8.1 Abgleich mit der Buchungsmaschine (Schritt 0)
Die Buchungsmaschine liegt im PMS-Repository und ist hier nicht einsehbar. Vor der Umsetzung werden ihre Design-Tokens übernommen – **ohne gemeinsamen Code**: Die Buchungsmaschine veröffentlicht ihre Tokens unter einer öffentlichen URL (siehe `docs/BUCHUNGSMASCHINE-SCHNITTSTELLE.md`, Abschnitt Theming), die Website kopiert sie versioniert nach `src/styles/tokens.css`. Bis dahin gelten die Annahmen aus 8.2.

### 8.2 Bausteine (Annahme, wird an die Tokens angeglichen)
- **Glass:** halbtransparente Flächen (`backdrop-filter: blur()` + Sättigung), feine helle Ränder (1 px, ~20 % Weiß), weiche Schatten, Innenglanz-Verlauf. Immer mit Fallback ohne `backdrop-filter`.
- **Pixel:** Pixel-Schrift ausschließlich für Mikro-Elemente (Labels, Zahlen, Badges), Pixel-Icons, Raster- und Dither-Muster, stufige Animationen (`steps()`), Pixel-Auflösungs-Übergänge.
- **Typografie:** gut lesbare Text-Schrift + Display-Schrift für Überschriften; alle Schriften selbst gehostet (keine Google-Fonts-CDN).
- **Farben:** aus den Motiven abgeleitet – Porphyr-Rot (Rochlitzer Porphyr), Flussgrün/-blau der Mulde, Sandstein, Nachtblau für Abendszenen. CTA-Farbe exklusiv.
- **Komponenten:** GlassCard, BookingBar, DateRangePicker (vom Widget der Buchungsmaschine geliefert), PixelIcon, PixelReveal, StatCounter, MapPin, ReviewCard, FactSheet, FAQ-Accordion, StickyMobileCTA.

### 8.3 Animationen (Eyecatcher, aber performant)
| Effekt | Technik | Fallback |
|---|---|---|
| Hero „Pixel zu Wirklichkeit“ | WebGL-/Canvas-Mosaik-Shader über Poster und Video, lädt nach LCP | Statisches Poster |
| Scroll-Reveals der Glass-Karten | CSS `animation-timeline: view()` (scroll-driven), kein JS | Sofort sichtbar |
| Pixel-Sonne über den Zinnen | Scroll-Timeline + Sprite mit `steps()` | Statische Illustration |
| Interaktive Pixel-Karte | SVG/Canvas, Pins mit Hover/Tap | Liste der Schlösser |
| Zahlen-Zähler („15 Zimmer“, „400 m“) | IntersectionObserver, einmalig | Endwerte |
| Seitenwechsel | View Transitions API (Same-Origin) | Normaler Seitenwechsel |
| **Übergang in die Buchung** | Pixel-Dissolve deckt die Seite ab, die Buchung öffnet sich aus demselben Raster (Overlay-Modus) bzw. die Buchungsseite blendet mit gleichem Raster ein (Parameter `transition=pixel`) | Direkter Link |

Regeln: Nur `transform`/`opacity`/Filter animieren, keine Layout-Animationen, Effekte pausieren außerhalb des Viewports, alles respektiert `prefers-reduced-motion`.

---

## 9. Integration der Buchungsmaschine

Website und Buchungsmaschine bleiben **zwei getrennte Projekte**. Die Website bindet die Buchungsmaschine genau so an, wie es jede andere Website auch könnte – über die öffentlichen Mittel des PMS. Der vollständige Vertrag steht in `docs/BUCHUNGSMASCHINE-SCHNITTSTELLE.md`. Kurzfassung:

1. **Deep Link (Basis, funktioniert immer, auch ohne JS):** `https://buchen.muldenschloesschen.de/?arrival=…&departure=…&adults=…&room=…&lang=de` plus UTM-Parameter.
2. **Embed-Widget (Web Component, Script vom PMS):** Buchungsleiste und Kalender mit Live-Preisen direkt auf der Website.
3. **Overlay-Buchung:** Die komplette Buchung öffnet sich als Vollbild-Sheet über der Website (kein Seitenwechsel, Zurück-Taste schließt). Fallback: Deep Link.
4. **Öffentliche Lese-API:** Ab-Preise, nächste freie Termine, Zimmerkategorien (Single Source of Truth für `/zimmer/`). Zur Build-Zeit für statisches HTML, zur Laufzeit für Live-Werte.
5. **Ereignisse:** Die Buchungsmaschine meldet Suche, Zimmerauswahl, Checkout-Start und Buchung (Wert, Währung, ID) per `postMessage` – für einwilligungsfreie Conversion-Messung.

Für die Website ist die Buchungs-URL nur Konfiguration (`PUBLIC_BOOKING_URL`). Damit kann die neue Website auch schon live gehen, solange noch RoomRaccoon im Einsatz ist, und später ohne Code-Änderung umschalten.

Empfehlung zur Domain: Buchungsmaschine unter `buchen.muldenschloesschen.de` (CNAME auf das PMS). Vorteile: gleiche Site für Cookies (kein Safari-ITP-Problem im Overlay), Vertrauen durch eigene Domain, einfaches Cross-Domain-Tracking.

Booking.com-Abhängigkeit reduzieren: Direktbuchungsvorteil kommunizieren, Bewertungsanfrage nach dem Aufenthalt aus dem PMS (Google + HolidayCheck), Antworten auf Bewertungen. Ausstattung (Booking 7,2) gezielt verbessern und die Verbesserungen auf der Website zeigen.

---

## 10. Technik und Projektstruktur

### 10.1 Stack
- **Astro** (statische Ausgabe, Islands nur dort, wo Interaktion nötig ist), TypeScript, natives CSS mit Custom Properties (Tokens), keine Abhängigkeit zum PMS-Code.
- Inhalte als **Content Collections** (Markdown/MDX + typisierte Schemata) im Repo; optional git-basiertes CMS (z. B. Keystatic) für den Betreiber – ohne Server und Datenbank.
- Bilder über `astro:assets` (AVIF/WebP, responsive), Originale aus dem bestehenden WordPress-Upload-Ordner übernommen (Bildrechte liegen beim Betreiber).
- Hosting: statisch, EU-Standort (z. B. Hetzner + Caddy oder ein EU-Static-Host), HTTP/3, Brotli, lange Cache-Header für Assets.
- Analyse: cookielos und datensparsam (Matomo selbst gehostet oder Plausible EU) → kein Consent-Banner für Basis-Analyse nötig. Externe Inhalte (Komoot, Karten, Videos Dritter) nur per 2-Klick.

### 10.2 Repository-Aufbau (geplant)
```
muldenschloesschen-web/
├─ docs/                     Plan, Schnittstelle zur Buchungsmaschine
├─ public/                   robots.txt, Favicons, _redirects
├─ src/
│  ├─ content/               seiten, touren, schloesser, veranstaltungen, faq, bewertungen
│  ├─ components/            GlassCard, BookingBar, PixelReveal, PixelMap, …
│  ├─ layouts/               BaseLayout (SEO-Head, JSON-LD, Skip-Link)
│  ├─ lib/booking/           Adapter zur Buchungsmaschine (Deep Link, Embed, API, Events)
│  ├─ pages/                 Routen (bestehende URLs 1:1)
│  └─ styles/                tokens.css (aus Buchungsmaschine kopiert), base.css
├─ tests/                    Playwright (E2E, A11y mit axe), Contract-Tests gegen Booking-Mock
└─ .github/workflows/        Build, Lighthouse-CI-Budgets, Link-Checker, Deploy
```
Die vorhandene `.gitignore` (Composer/PHP-Vorlage) wird beim Projektsetup durch eine Node/Astro-Variante ersetzt.

### 10.3 Trennung von PMS und Website (Regeln)
- Kein Git-Submodul, kein gemeinsames Paket, kein Monorepo. Einzige Verbindung ist der öffentliche Vertrag (URL-Parameter, Embed-Script, API, Events).
- Der Booking-Adapter in `src/lib/booking/` kapselt alles; im Dev-Modus und in der CI läuft ein lokaler Mock der Schnittstelle, damit die Website ohne PMS baut und testet.
- Fällt die Buchungs-API aus, baut und funktioniert die Website trotzdem (Fallback: Deep Link ohne Live-Preise).

---

## 11. Recht und Datenschutz
- Impressum (DDG § 5) und Datenschutzerklärung vor Launch – Daten vom Betreiber.
- Schriften lokal, keine Google-Fonts-CDN. Komoot, Google Maps, YouTube nur nach Klick.
- Nur echte Bewertungen mit Quelle; Hinweis, wie Echtheit sichergestellt wird (UWG § 5b Abs. 3).
- Preise inkl. MwSt. und Kurtaxe-Hinweis (falls zutreffend) gemäß PAngV; „Ab“-Preise müssen buchbar sein.
- Kontaktformular mit minimalen Pflichtfeldern, Versand ohne Drittanbieter-Tracking.

---

## 12. Umsetzung in Phasen

| Phase | Ergebnis | Abhängigkeiten |
|---|---|---|
| 0 – Klärung | Offene Fragen (Abschnitt 14) beantwortet, Entfernungen gemessen, NAP festgelegt, Design-Tokens der Buchungsmaschine vorhanden | Betreiber, PMS-Team |
| 1 – Fundament | Astro-Projekt, Tokens, Layout, SEO-Head, JSON-LD-Bausteine, CI mit Lighthouse-Budgets, Hosting-Vorschau, Impressum/Datenschutz | – |
| 2 – Startseite | Alle Abschnitte aus 7.2 mit statischen Inhalten, Deep-Link-Buchung | Phase 1 |
| 3 – Unterseiten & Inhalte | Alle Seiten aus Abschnitt 4, Content Collections, FAQ, Veranstaltungen mit Auto-Ablauf, Bildmigration | Phase 1 |
| 4 – Buchungsintegration | Embed-Widget, Overlay, Live-Preise, freie Termine, Event-Tracking, Contract-Tests | PMS liefert Schnittstelle (parallel) |
| 5 – Eyecatcher & Feinschliff | Pixel-Reveal-Hero, Pixel-Karte, Sonnen-Zeitleiste, Buchungsübergang; Performance- und A11y-Audit | Phasen 2–4 |
| 6 – Migration & Launch | 301-Mapping inkl. Bild-URLs, Search Console + Bing, Sitemap-Einreichung, GBP/NAP-Abgleich, Hotel Center, Monitoring | Phasen 1–5 |
| 7 – Wachstum | A/B-Tests (Hero-Headline, CTA-Text), englische Version, Veranstaltungen 2027 pflegen, KI-Zitat-Monitoring, Bewertungsprozess | Launch |

---

## 13. Erfolgsmessung

| KPI | Messung | Ziel nach Launch |
|---|---|---|
| Buchungs-Conversion (Sitzung → Buchung) | Events der Buchungsmaschine | Basiswert erfassen, dann kontinuierlich steigern |
| Buchungsstart-Rate (Klick auf Verfügbarkeit) | Website-Event | > 8 % der Sitzungen |
| Anteil Direktbuchungen vs. OTA | PMS-Auswertung | steigend |
| Organische Klicks und Rankings je Cluster | Search Console | Top 3 für Cluster A/B, Top 10 für C–F |
| KI-Zitate | Monatliches Prompt-Protokoll | In Antworten auf Fragen aus 5.2 genannt |
| Core Web Vitals | CrUX / Search Console | alle „gut“ |
| Barrierefreiheit | axe in CI, manuelle Prüfung | 0 kritische Befunde |

---

## 14. Offene Fragen an den Betreiber
1. Gibt es noch Restaurant/Abendessen, Sonntagsbraten, Hochzeiten/Feiern, Tagungen? (Bestimmt, ob diese Inhalte komplett entfallen.)
2. Welche **eine** Telefonnummer gilt? (03075-425098 / +49 162 9115038 / +49 37383 159781)
3. Frühstück: Zeiten, Preis, inklusive oder optional („Frühstück nach Reservierung“ laut Booking.com)?
4. Check-in/Check-out-Zeiten, Haustiere, Kinderbetten, Parkplätze, barrierefreie Zimmer?
5. Zimmerkategorien, Anzahl Zimmer mit Schlossblick, aktuelle Fotos je Kategorie?
6. Ist das Haus Bett+Bike-zertifiziert (oder soll es das werden)?
7. Welcher Direktbuchungsvorteil wird angeboten?
8. Finale Domain der Buchungsmaschine und Zeitpunkt der Ablösung von RoomRaccoon?
9. Daten für Impressum (Muldenschlösschen GmbH, Geschäftsführung, Registereintrag, USt-ID).
10. Gastgeber-Vorstellung (Name, Foto, Text) für E-E-A-T gewünscht?
11. Gewünschte Sprachen nach dem Launch (EN, NL)?
12. Gemessene Fußweg-Entfernung zum Schloss Rochsburg (über die Hängebrücke).
