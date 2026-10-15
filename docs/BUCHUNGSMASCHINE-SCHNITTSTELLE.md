# Schnittstelle Website ↔ Buchungsmaschine

Dieses Dokument beschreibt, was die Buchungsmaschine (Teil des PMS, eigenes Repository) öffentlich anbieten muss, damit **jede** Website sie anbinden kann – die neue muldenschloesschen.de ist nur ein Nutzer davon. Die Website kennt keinen PMS-Code, sondern nur diesen Vertrag.

Versionierung: Alle Pfade tragen `v1`. Brechende Änderungen nur in `v2`, `v1` bleibt mindestens bis zur Migration aller Websites erhalten.

Platzhalter: `{BOOKING}` = Basis-URL der Buchungsmaschine, empfohlen `https://buchen.muldenschloesschen.de`. `{PROPERTY}` = Kennung des Betriebs im PMS, z. B. `muldenschloesschen`.

---

## 1. Deep Link (Pflicht)

Funktioniert ohne JavaScript und ist der Fallback für alle anderen Modi.

```
{BOOKING}/{PROPERTY}?arrival=2026-11-13&departure=2026-11-15&adults=2&children=1&childAges=6&room=schlossblick-dz&lang=de&utm_source=website&utm_medium=booking-bar&utm_campaign=home-hero
```

| Parameter | Typ | Pflicht | Bedeutung |
|---|---|---|---|
| `arrival`, `departure` | `YYYY-MM-DD` | nein | Vorbelegter Zeitraum; fehlt er, startet die Buchung mit dem Kalender |
| `adults` | Zahl | nein | Standard 2 |
| `children`, `childAges` | Zahl, Komma-Liste | nein | Kinder und Alter |
| `room` | Slug | nein | Zimmerkategorie vorauswählen |
| `rate` | Slug | nein | Rate/Paket vorauswählen (z. B. Radler-Paket) |
| `promo` | String | nein | Aktionscode |
| `lang` | `de` \| `en` \| … | nein | Sprache |
| `returnUrl` | URL (URL-encoded) | nein | Ziel für „Zurück zur Website“; muss in der PMS-Konfiguration erlaubt sein |
| `transition` | `pixel` | nein | Einstiegsanimation im Pixel-Raster für nahtlosen Übergang |
| `utm_*` | String | nein | Werden bis zur Buchung mitgeführt und im PMS gespeichert |

Verhalten: Ungültige Parameter werden ignoriert, nie mit Fehlerseite beantwortet. Ist der Zeitraum ausgebucht, zeigt die Buchungsmaschine direkt Alternativen (nächste freie Termine).

## 2. Embed-Widget (Web Component)

```html
<script type="module" src="{BOOKING}/embed/v1/widget.js" async></script>

<pms-booking-bar
  property="{PROPERTY}"
  lang="de"
  mode="overlay"
  theme="glass-pixel"
  utm-source="website">
</pms-booking-bar>
```

- Shadow DOM, damit Website-CSS und Widget-CSS sich nicht beeinflussen. Anpassung nur über dokumentierte CSS Custom Properties (siehe Abschnitt 5) und `::part()`.
- `mode="link"`: Absenden öffnet den Deep Link. `mode="overlay"`: Absenden öffnet die Buchung als Overlay (Abschnitt 3).
- Script < 30 KB komprimiert, lädt nicht-blockierend, verursacht keinen Layout Shift (die Website reserviert die Höhe; das Widget meldet seine Höhe per Event).
- Progressive Enhancement: Vor dem Laden des Widgets steht auf der Website ein normales `<form>` mit `action="{BOOKING}/{PROPERTY}"` und `method="get"` – dieselben Feldnamen wie im Deep Link. Das Widget ersetzt es, ohne dass sich das Verhalten ändert.
- Barrierefrei (WCAG 2.2 AA): Tastatur-Kalender, ARIA-Labels, Fokusführung.

Weitere Elemente nach demselben Prinzip (optional):
- `<pms-next-free-dates property count="3" nights="2">` – Chips mit den nächsten freien Zeiträumen und Preis.
- `<pms-room-price property room="schlossblick-dz">` – Live-Ab-Preis einer Kategorie.

## 3. Overlay-Buchung

```js
import { openBooking } from '{BOOKING}/embed/v1/widget.js';
openBooking({ property: '{PROPERTY}', arrival, departure, adults, room, lang: 'de' });
```

- Vollbild-Sheet mit `<iframe src="{BOOKING}/{PROPERTY}?…&embed=overlay">`, Fokus-Falle, `Esc` und Browser-Zurück schließen das Overlay (History-Eintrag).
- Auf derselben Site (`*.muldenschloesschen.de`) funktionieren Cookies und Zahlungsanbieter ohne Third-Party-Cookie-Probleme. Bei fremden Domains muss die Buchungsmaschine automatisch auf den Deep Link (neuer Tab oder gleiche Seite) ausweichen, wenn Storage im iframe blockiert ist.
- Zahlungsschritte mit Redirect (3-D Secure, PayPal) laufen im Overlay oder brechen kontrolliert in ein eigenes Fenster aus – nie in einen toten Zustand.
- PMS-Konfiguration pro Betrieb: erlaubte Einbettungs-Origins → `Content-Security-Policy: frame-ancestors`.

## 4. Öffentliche Lese-API

Nur lesend, ohne Authentifizierung, mit CORS für die im PMS hinterlegten Origins, Rate-Limit, `Cache-Control` (Preise ≤ 5 min, Stammdaten ≤ 1 h).

| Endpunkt | Antwort (Auszug) | Nutzung auf der Website |
|---|---|---|
| `GET {BOOKING}/api/public/v1/{PROPERTY}/rooms?lang=de` | `[{ slug, name, description, maxOccupancy, size, beds, amenities[], images[{url,width,height,alt}], fromPrice{amount,currency} }]` | `/zimmer/` zur Build-Zeit, JSON-LD `HotelRoom` |
| `GET …/availability?arrival&departure&adults` | `[{ room, available, roomsLeft, totalPrice{amount,currency}, nightly[] }]` | Live-Preis, echte Knappheitshinweise |
| `GET …/next-free?nights=2&count=3&adults=2&room=` | `[{ arrival, departure, fromPrice }]` | Chips „Nächste freie Wochenenden“ |
| `GET …/property` | `{ name, address, geo, phone, email, checkin, checkout, policies, amenities[] }` | Faktenblock, JSON-LD – eine Quelle für NAP |

Preise immer inklusive MwSt.; Zusatzkosten (z. B. Kurtaxe, Frühstück) als eigene Felder, damit die Website PAngV-konform „ab“-Preise anzeigen kann.

## 5. Theming / Design-Tokens

- `GET {BOOKING}/embed/v1/tokens.json` und `{BOOKING}/embed/v1/tokens.css` – die Glass-/Pixel-Tokens der Buchungsmaschine (Farben, Radien, Blur, Schatten, Schriften, Pixel-Raster, Animationsdauern).
- Die Website **kopiert** diese Werte versioniert in ihr eigenes Repo (`src/styles/tokens.css`), sie lädt sie nicht zur Laufzeit. So bleibt sie unabhängig, sieht aber gleich aus.
- Das Widget liest optionale Überschreibungen über CSS Custom Properties mit Präfix `--pms-*` (z. B. `--pms-accent`, `--pms-glass-blur`, `--pms-radius`), damit andere Websites es an ihr eigenes Design anpassen können.

## 6. Ereignisse für Analyse und Conversion-Messung

Die Buchungsmaschine sendet aus Widget, Overlay und Deep-Link-Seite (`window.opener`/`parent`, falls vorhanden):

```js
window.parent.postMessage({ source: 'pms-booking', version: 1, type: 'purchase',
  data: { transactionId, value, currency: 'EUR', room, arrival, departure, nights, adults } }, targetOrigin);
```

| `type` | Wann |
|---|---|
| `ready` | Widget/Overlay geladen (inkl. `height`) |
| `search` | Zeitraum/Gäste gesucht |
| `view_rooms` | Ergebnisliste angezeigt |
| `select_room` | Zimmer/Rate gewählt |
| `begin_checkout` | Gästedaten-Schritt geöffnet |
| `purchase` | Buchung bestätigt |
| `close` | Overlay geschlossen (mit letztem Schritt) |

- `targetOrigin` ist immer der konkrete, erlaubte Origin – nie `*`.
- Keine personenbezogenen Daten (Name, E-Mail) in Events.
- Zusätzlich serverseitig: Die Buchung speichert `utm_*` und `referrer`, damit das PMS Direktbuchungen pro Kanal auswerten kann, auch wenn Browser-Events blockiert werden.

## 7. PMS-Konfiguration pro Website

| Einstellung | Zweck |
|---|---|
| Erlaubte Origins | CORS der API, `frame-ancestors`, `postMessage`-Ziel |
| Erlaubte `returnUrl`-Präfixe | Schutz vor Open Redirects |
| Standardsprache, Währung | Vorgaben |
| Theme-Variante | z. B. `glass-pixel` |
| Feeds für Google Hotel Center / Metasuche | Preise und Verfügbarkeit (ARI) für kostenlose Buchungslinks |

## 8. Abnahmekriterien

- Eine leere Test-HTML-Datei auf einer fremden Domain kann mit Abschnitt 1–3 buchen (Beweis, dass die Website keinen Sonderweg nutzt).
- Deep Link funktioniert mit deaktiviertem JavaScript.
- Widget verursacht CLS = 0 und verschlechtert INP der Host-Seite nicht messbar.
- API liefert bei Ausfall des PMS-Backends einen sauberen Fehler; die Website zeigt dann den Deep Link ohne Live-Preis.
- Alle Events kommen in der Website an, `purchase` genau einmal pro Buchung.
- Website-Repository enthält einen Mock dieser Schnittstelle für Entwicklung und CI; Contract-Tests prüfen die Antwortformate aus Abschnitt 4.
