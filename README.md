# hlsdeutschland.de — Website der HLS Deutschland GmbH

Dieses Repository enthält die **komplette öffentliche Website** der HLS Deutschland GmbH,
erreichbar unter <https://hlsdeutschland.de>.

Es ist eine reine **statische Website**: nur HTML, CSS und Bilder. Kein Build-Schritt,
kein Framework, keine Datenbank, keine Abhängigkeiten. Was hier im Repository liegt,
ist exakt das, was im Browser ausgeliefert wird.

## Hosting

Die Seite wird über **GitHub Pages** aus dem Branch `main` ausgeliefert. Die Datei
`CNAME` bindet die eigene Domain `hlsdeutschland.de` an diese GitHub-Pages-Seite.

Das bedeutet in der Praxis: **jeder Commit auf `main` geht live** — in der Regel
innerhalb ein bis zwei Minuten. Es gibt keine Staging-Umgebung und keine
Freigabestufe dazwischen.

> `CNAME` niemals löschen oder umbenennen. Ohne diese Datei fällt die Seite auf die
> GitHub-Adresse zurück und die Domain zeigt ins Leere.

## Inhalt der Dateien

| Datei | Zweck |
| --- | --- |
| `index.html` | Startseite. Enthält alle Texte, das komplette CSS (inline im `<style>`-Block) und die strukturierten Daten (JSON-LD) für Suchmaschinen. |
| `impressum.html` | Impressum nach § 5 DDG. Rechtlich vorgeschrieben. |
| `datenschutz.html` | Datenschutzerklärung nach DSGVO. Rechtlich vorgeschrieben. |
| `crest.png` / `crest.webp` | Firmenwappen im Hero-Bereich. Zwei Formate, WebP wird bevorzugt geladen. |
| `geschwinder.jpg` / `geschwinder.webp` | Porträtfoto im Abschnitt „Person". Ebenfalls zwei Formate. |
| `favicon.png` | Browser-Icon im Tab. |
| `CNAME` | Bindet die Domain `hlsdeutschland.de` an GitHub Pages. |
| `robots.txt` | Erlaubt Suchmaschinen alle Seiten und verweist auf die Sitemap. |
| `sitemap.xml` | Liste der drei Seiten für Google & Co. |
| `google630a63ead2efd5c7.html` | Bestätigungsdatei der Google Search Console. Belegt Google gegenüber den Besitz der Domain. |

> `google630a63ead2efd5c7.html` nicht löschen. Verschwindet die Datei, verliert das
> Konto den Zugang zur Search Console für diese Domain.

## Aufbau der Startseite

`index.html` besteht aus vier Abschnitten, die auch die Navigation oben bedient:

1. **Unternehmen** — was die Holding ist, plus die fünf Sektoren
   (Mobility, Digital Infrastructure, Energy, Leasing, Industrial Services).
   Die derzeit aktiven Sektoren tragen die CSS-Klasse `active`: Mobility und
   Digital Infrastructure.
2. **Schwerpunkte** — vier aktuelle Projekte: Schienenersatzverkehr in Bayern,
   Busdepot-Systemhalle mit Photovoltaik, PEK.digital, Fördersignal Bus.
   Projekte mit eigener Domain werden zusätzlich im JSON-LD-Feld `sameAs` geführt.
3. **Person** — Gerhard Geschwinder, Geschäftsführer.
4. **Kontakt** — E-Mail, Telefon, Anschrift, Registerdaten.

## Etwas ändern

Kleine Textänderungen gehen direkt auf github.com: Datei öffnen, Stift-Symbol,
bearbeiten, committen. Für größeres Arbeiten lokal:

```bash
git clone https://github.com/HLS-Deutschland/hlsdeutschland.git
cd hlsdeutschland
python3 -m http.server 8000   # danach http://localhost:8000 im Browser öffnen
```

Ein lokaler Server ist der Vorschau per Doppelklick vorzuziehen — nur so verhalten
sich Pfade und Bilder genauso wie später auf der echten Domain.

### Worauf zu achten ist

**Kontaktdaten stehen mehrfach im Repository.** Ändert sich Adresse, Telefonnummer,
E-Mail oder eine Registernummer, müssen *alle* diese Stellen angefasst werden:

- `index.html` — im JSON-LD-Block ganz oben im `<head>` **und** im Abschnitt „Kontakt"
- `impressum.html`
- `datenschutz.html` — im Abschnitt „1. Verantwortlicher"

**Bilder gibt es doppelt.** Wird ein Foto ausgetauscht, muss sowohl die
`.png`/`.jpg`- als auch die `.webp`-Variante ersetzt werden — sonst sehen
verschiedene Browser verschiedene Bilder.

**`sitemap.xml` mit pflegen.** Kommt eine Seite dazu, gehört sie in die Sitemap.
Bei inhaltlichen Änderungen das `<lastmod>`-Datum der betroffenen Seite aktualisieren.

**Impressum und Datenschutzerklärung sind Pflichtangaben.** Beide Seiten müssen
aus dem Footer heraus erreichbar bleiben und inhaltlich aktuell sein.

## Kontakt

HLS Deutschland GmbH · <admin@hlsdeutschland.de>
