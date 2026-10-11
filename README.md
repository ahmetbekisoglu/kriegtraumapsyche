# Initiative: Krieg Trauma Psyche – Archiv-Website

Statischer Nachbau von kriegtraumapsyche.de (vorher WordPress.com) für GitHub Pages.
Reines HTML + CSS: kein Build, keine Skripte, keine Cookies, keine externen Schriften.

Die Adressen bleiben gleich wie bei WordPress (`/unser-ziel/`, `/uber-uns/`, `/impressum/`, `/datenschutzerklarung/`),
damit alte Links und Google-Einträge weiter funktionieren.

```
index.html                    Startseite
unser-ziel/index.html         Unser Ziel (mit Quellen)
uber-uns/index.html           Über uns
impressum/index.html          Impressum
datenschutzerklarung/         Datenschutzerklärung (auf GitHub Pages angepasst)
404.html                      Fehlerseite
assets/css/style.css          gesamtes Design
assets/img/                   alle Bilder (lokal gesichert, inkl. Instagram-Vorschaubilder)
CNAME                         eigene Domain für GitHub Pages
```

## Lokal ansehen

Im Terminal in diesem Ordner:

```bash
python3 -m http.server 8000
```

Dann im Browser `http://localhost:8000` öffnen. (Per Doppelklick auf `index.html` geht es auch,
dann führen die Menülinks aber zu Ordneransichten statt zu den Seiten.)

## Auf GitHub Pages veröffentlichen

1. Auf github.com **+** → **New repository**, Name z. B. `kriegtraumapsyche`, **Public**, ohne README → **Create repository**.
2. **uploading an existing file** → den *Inhalt* dieses Ordners ins Fenster ziehen
   (alle Dateien und Ordner, auch die versteckten `.nojekyll` und `CNAME` – im Finder mit Cmd+Shift+. einblenden).
3. **Commit changes**.
4. **Settings → Pages** → Branch `main`, Ordner `/ (root)` → **Save**.
5. Unter **Custom domain** steht dank `CNAME` bereits `kriegtraumapsyche.de`.

## Domain von WordPress.com auf GitHub umstellen

Die Domain nutzt aktuell die Nameserver von WordPress.com, und `info@kriegtraumapsyche.de`
läuft über die E-Mail-Weiterleitung von WordPress.com (`MX smtp-fwd.wordpress.com`).

1. Erst wenn die GitHub-Seite läuft: bei WordPress.com → **Upgrades → Domains → kriegtraumapsyche.de → DNS-Einträge**.
2. Die bestehenden `A`-Einträge für `@` ersetzen durch:
   `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
3. `CNAME` für `www` auf `DEINNAME.github.io` setzen.
4. **Den MX-Eintrag und die E-Mail-Weiterleitung nicht anfassen**, sonst kommen keine Mails mehr an.
   Den Google-`TXT`-Eintrag ebenfalls stehen lassen.
5. Nach einigen Minuten bis Stunden in GitHub **Settings → Pages → Enforce HTTPS** aktivieren.
6. Erst danach den WordPress.com-Plan der *Website* kündigen – die *Domain-Registrierung* (und damit die
   Mail-Weiterleitung) muss weiterlaufen. Vorher bei WordPress.com prüfen, ob die Weiterleitung auch ohne Website-Plan aktiv bleibt.

## Vor dem Go-live prüfen

- Impressum/Datenschutz: Die alte Seite nannte zwei Hausnummern (Stephanstraße **65** im Impressum, **55** in der Datenschutzerklärung).
  Hier ist überall 65 eingetragen – bitte prüfen und ggf. auf eine aktuelle ladungsfähige Anschrift ändern.
- Datenschutz: ist auf GitHub Pages + E-Mail-Weiterleitung umgeschrieben. Rechtlich nicht geprüft.
