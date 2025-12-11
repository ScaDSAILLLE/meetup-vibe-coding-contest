# **Beispiel 3 – Voting-App für die Contest-Siegerabstimmung**

In diesem Beispiel entwickelst du **iterativ gemeinsam mit einem KI-Modell** (Goose *oder* Void, beides ist möglich) eine kleine Voting-Lösung für die Abstimmung über die Siegerprojekte des Vibe Coding Contests.

Die App soll im Idealfall **über das Netzwerk erreichbar** sein – z. B. als kleine Web-App, die auf einem Laptop läuft und über einen Browser auf anderen Geräten aufgerufen werden kann.

---

## 🧠 Ziel der Aufgabe

Baue mit Hilfe von KI (Vibe Coding!) eine Voting-Lösung, mit der am Ende des Workshops alle Teilnehmenden für ihre Lieblingsprojekte abstimmen können.

**Minimalziel:**

* Eine Oberfläche, auf der eine Liste von Projekten / Teams angezeigt wird
* Ein einfacher Button „Stimme abgeben“ (z. B. 1 Stimme pro Person, pro Gerät oder pro Session)
* Tracking einer Stimme pro Person / Gerät
* Eine Auswertung / Anzeige der aktuellen Stimmverteilung
* Ansprechende Darstellung und Nutzerinferace für die Abgabe der Stimme

**Nice-to-have:**

* Erreichbar im Netzwerk (z. B. `http://<IP>:<Port>` im WLAN) oder über einen share-link / localtunnel o.ä.
* Einfache Admin-Ansicht, um die Liste der Projekte zu pflegen
* Live-Update oder Refresh-Funktion der Ergebnisse

---

## 🧰 Technologiewahl – zusammen mit der KI

Die Wahl des Stacks ist **Teil der Aufgabe**. Nutze VOID oder Goose und kläre im Chat zuerst:

> „Ich möchte eine einfache Voting-App für unseren Vibe Coding Contest bauen, die im lokalen Netzwerk erreichbar ist. Welche Technologie würdest du empfehlen (z. B. Python/Flask, FastAPI, Node/Express, einfache statische Seite + kleines Backend)?
> Rahmenbedingungen:
>
> * Ich habe begrenzt Zeit (Workshop-Setting)
> * Deployment möglichst einfach
> * Browserbasierte Nutzung für die Teilnehmenden.“

Lass dir **2–3 Vorschläge** machen und entscheide dich dann – z. B.:

* **Python + Flask/FastAPI** (Goose-freundlich, Sandbox-Execution)
* **Node.js + Express**
* **Statische HTML/JS-Seite + minimales API-Backend**

---

## 🔁 Arbeitsweise (Vibe Coding Style)

Die Idee ist, **nicht alles vorauszuplanen**, sondern Schritt für Schritt gemeinsam mit der KI zu entwickeln.

Ein möglicher Ablauf:

### 1️⃣ Konzept & Datenmodell

Prompt-Ideen:

> „Hilf mir, ein ganz simples Datenmodell für die Voting-App zu entwerfen. Wir brauchen:
>
> * eine Liste von Projekten (Name, Beschreibung, Team)
> * eine repräsentative Zählung der Stimmen
>
> Keine komplexe Authentifizierung, aber möglichst einfach zu benutzen.“

Lass dir danach:

* JSON-Struktur
* Python/JS-Klassen oder einfache Dicts/Objekte
* erste Stub-Funktionen

erzeugen.

---

### 2️⃣ Basic Backend / Logik

Prompt-Ideen:

> „Erzeuge mir bitte einen minimalen Server (in [deiner gewählten Sprache/Technologie]), der:
>
> * eine Startseite / Voting-Seite ausliefert
> * eine API-Route `POST /vote` bereitstellt, die eine Stimme für ein Projekt zählt
> * eine API-Route `GET /results` bereitstellt, die die aktuellen Ergebnisse zurückgibt.“

Nutze danach weitere Prompts wie:

> „Erkläre mir den Code und zeige mir, wie ich den Server starte.“

---

### 3️⃣ UI – einfache Voting-Seite

Prompt-Ideen:

> „Erzeuge eine `index.html`, die per Fetch-Request die Projektliste lädt,
> für jedes Projekt einen Vote-Button anzeigt
> und bei Klick eine Stimme per `POST /vote` sendet.
>
> Baue darunter eine einfache Anzeige der aktuellen Ergebnisse (Projektname + Stimmenzahl).“

Optional:

> „Bitte füge ein automatisches Refreshing der Ergebnisse alle 5 Sekunden hinzu.“

---

### 4️⃣ Netzwerk-Erreichbarkeit

Wenn euer Setup es erlaubt, kannst du mit der KI besprechen, wie die App im Netzwerk erreichbar wird, z. B.:

> „Erkläre mir, wie ich diesen Server so starten kann, dass andere Geräte im selben WLAN über meine IP-Adresse darauf zugreifen können (z. B. `http://192.168.x.x:8000`).
> Was muss ich bei `host` und `port` einstellen?“

Hinweis: je nach Umgebung sind ggf. Firewalls / Ports zu beachten – das ist für den Contest ein „Best Effort“.

---

### 5️⃣ Ergebnisanzeige für die Abschlussrunde

Ziel ist, am Ende etwas zu haben, das man **auf einem Beamer oder Bildschirm zeigen** kann:

Prompt-Ideen:

> „Erstelle bitte eine kleine Ergebnisseite `results.html`, die nur die aktuellen Projekte nach Stimmen sortiert anzeigt, schön formatiert (z. B. Balken, Prozentangaben) – geeignet für eine Präsentation.“

---

## ⭐ Bonus-Ideen

Wenn ihr Zeit und Lust habt:

* **Einmalige Stimmabgabe:**
  Simple Schutzmechanismen (z. B. Session-ID, Cookie, einfacher Token)

* **QR-Code-Link:**
  KI bitten, dir einen QR-Code-Generator-Link oder HTML einzubauen, damit Leute mit dem Smartphone scannen können.

* **Admin-Panel:**
  Eine kleine Seite, auf der ihr Projekte anlegen, bearbeiten oder zurücksetzen könnt.

---

## ✅ Abgabe / Dokumentation

Dokumentiere kurz in einer `README` oder `NOTES.md`:

* Welche Technologie ihr verwendet habt
* Wie man die App startet
* Wie andere im Netzwerk abstimmen können
* Welche Rolle die KI bei der Entwicklung gespielt hat (Prompts, wichtige Schritte)

---

**Wichtig:**
Es geht nicht darum, eine perfekte, produktionsreife Voting-Plattform zu bauen,
sondern darum, **Vibe Coding** zu erleben:

> Idee → KI → Code → Test → Anpassung → Erweiterung → fertig genug für den Contest 🎉

---
