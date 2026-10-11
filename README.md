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
assets/css/style.css          gesamtes Design (Calibri, Blocksatz, Dark Mode, Symbole im HTML)
assets/fonts/                 Carlito – freier Calibri-Ersatz für Geräte ohne Calibri (Lizenz: OFL.txt)
assets/img/                   alle Bilder (lokal gesichert, inkl. Instagram-Vorschaubilder und Preis-Logos)
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

## Domain bei Strato auf GitHub zeigen lassen

Die Domain zieht ab dem 12.10.2026 von WordPress.com zu Strato. Sobald der Umzug durch ist, ist die alte
WordPress-Seite unter kriegtraumapsyche.de weg – deshalb diese Reihenfolge:

1. **Vorher:** Die Seite bei GitHub hochladen (siehe oben) und prüfen, dass sie unter
   `https://DEINNAME.github.io/REPO/` läuft.
2. **Nach dem Umzug** im Strato-Kundenlogin: **Domains → Domainverwaltung → kriegtraumapsyche.de → DNS-Einstellungen**
   (Menünamen können je nach Paket leicht abweichen).
3. **A-Record** für die Domain auf GitHub setzen:
   `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   Falls Strato nur eine IP-Adresse zulässt, reicht `185.199.108.153`.
4. Für **www** einen **CNAME-Record** auf `DEINNAME.github.io` anlegen.
5. **MX-Einträge** (E-Mail) bleiben auf den Strato-Mailservern – nicht ändern.
6. In GitHub **Settings → Pages**: Custom domain `kriegtraumapsyche.de` prüfen, nach einigen Minuten bis Stunden
   **Enforce HTTPS** aktivieren.
7. Optional, aber empfohlen: In GitHub unter **dein Profil → Settings → Pages → Add a domain** die Domain
   verifizieren (GitHub nennt dafür einen TXT-Eintrag, der bei Strato angelegt wird). Das verhindert, dass
   jemand anderes die Domain auf GitHub für sich beanspruchen kann.
8. Danach den WordPress.com-Plan kündigen.

Der Umzugscode (AuthInfo) wird nur bei Strato für den Domain-Umzug gebraucht.

## E-Mail bei Strato

`info@kriegtraumapsyche.de` steht im Impressum und muss erreichbar bleiben. Die Weiterleitung von WordPress.com
endet mit dem Umzug.

- Bei Strato die Adresse `info@kriegtraumapsyche.de` als Postfach oder Weiterleitung einrichten – am besten
  direkt nach dem Umzug, damit keine Mails verloren gehen.
- Im Strato-Kundenlogin den **Auftragsverarbeitungsvertrag (AV-Vertrag)** abschließen. Die Datenschutzerklärung
  nennt Strato bereits als E-Mail-Anbieter mit AV-Vertrag.
