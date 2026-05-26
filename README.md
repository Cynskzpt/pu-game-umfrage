# Game-Umfrage · online + QR-Code

Die Seite läuft **ohne localhost** — du hostest sie im Internet und machst daraus einen QR-Code. Jede Antwort kommt **per E-Mail** zu dir.

---

## Schritt 1: E-Mail einrichten (einmalig)

1. Öffne [web3forms.com](https://web3forms.com)
2. Trag **deine E-Mail-Adresse** ein
3. Du bekommst einen **Access Key** (per Mail)
4. Öffne `config.js` und ersetze `HIER_DEIN_KEY_EINFÜGEN` mit deinem Key:

```js
const SURVEY_CONFIG = {
  WEB3FORMS_ACCESS_KEY: "dein-echter-key-hier",
};
```

Ab dann landet jede Umfrage-Antwort in deinem Postfach.

---

## Schritt 2: Seite online stellen (für QR-Code)

Der QR-Code braucht eine **öffentliche URL** (nicht `localhost`). Am einfachsten:

### Option A: Netlify Drop (ohne Account, ~2 Min.)

1. Geh auf [app.netlify.com/drop](https://app.netlify.com/drop)
2. Zieh den ganzen Ordner `umfrage` auf die Seite
3. Du bekommst eine URL wie `https://random-name-123.netlify.app`
4. Diese URL ist deine Umfrage-Adresse fürs Handy

### Option B: GitHub Pages (dauerhaft, kostenlos)

1. Projekt auf GitHub hochladen
2. Repository → **Settings** → **Pages**
3. Branch `main`, Ordner `/umfrage` (oder Root mit `index.html`)
4. URL: `https://deinname.github.io/repo-name/`

---

## Schritt 3: QR-Code erstellen

1. Kopiere deine **öffentliche URL** (z. B. von Netlify)
2. Geh z. B. auf [qr-code-generator.com](https://www.qr-code-generator.com/) oder suche „QR Code erstellen“
3. URL einfügen → QR speichern oder ausdrucken
4. Wer scannt, landet direkt auf der Umfrage

---

## Testen

1. `config.js` mit echtem Key speichern
2. Seite online hochladen (nicht nur lokal öffnen — sonst kann das Senden blockiert sein)
3. Einmal selbst ausfüllen → E-Mail sollte ankommen (auch Spam prüfen)

---

## Dateien

| Datei | Zweck |
|--------|--------|
| `index.html` | Umfrage-Seite |
| `config.js` | Dein Web3Forms-Key (nicht öffentlich teilen wenn du willst — Key ist nur für Formular-Senden gedacht) |

`server.py` wird **nicht mehr** gebraucht.
