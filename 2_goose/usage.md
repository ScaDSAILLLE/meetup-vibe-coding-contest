# **Goose Desktop Usage Guide**

Dieser Guide erklärt dir, wie du Goose Desktop im Rahmen des Vibe Coding Contests verwenden kannst:
von der Oberfläche, über die grundlegende Bedienung, bis hin zur Auswahl des passenden Modells.

Goose Desktop ist ein **AI-Coding-Agent**, der:

* Chat,
* Tool-Use,
* Multi-Agent Reasoning,
* Code (Sandbox) -Ausführung
* und Automation (Recipes, Scheduler)

in einer einzigen, leicht verständlichen Oberfläche vereint.

---

# 🖥️ **1. Überblick über die Goose Desktop Oberfläche**

Basierend auf diesem Screenshot:

![Goose UI](../media/goose_ide.png)

---

## **1.1 Linke Sidebar – Navigation**

Die Sidebar ist das zentrale Navigationsmenü:

### **🏠 Home**

Dashboard mit:

* Überblick über deine Sessions
* Tokenverbrauch
* Letzte Chats
* Schnellzugriff

### **💬 Chat**

Der wichtigste Bereich für Vibe Coding:
Hier interagierst du mit dem Modell — ähnlich wie in VOID, aber erweitert um:

* Session-Kontext
* Tools
* Multi-Agent-Workflows
* Arbeitsordner
* Aktuell aktives Modell (hier *Devstral* von Mistral)

### **📜 History**

Chronologische Liste/Grid deiner Chat-Sitzungen.

### **🧪 Recipes**

Automatisierte Workflows, die du selbst bauen oder importieren kannst.

Beispiele:

* „Erstelle ein Python Projekt immer mit eigenem Projektordner, lege ein virtual-environment an, bspw. mit uv und führe uv init aus. Prüfe abschließend vor Beginn des Projekts, ob\
alles sauber eingerichtet wurde, die `.venv` aktiviert ist und ebenso eine pyproject.toml das Setup dokumentiert. Kläre den Nutzer über die Verwendung von uv auf und die nötigsten\
Befehle, um ein Python Projekt mit uv sauber zu managen.

### **⏱️ Scheduler**

Lässt Abläufe und konfigurierte Tasks (z.B. via `.yaml`) zeitgesteuert oder eventbasiert ausführen.

### **🧩 Extensions**

Zukünftige Erweiterungen, Tools, Agent-Packs.

### **⚙️ Settings**

Hier richtest du:

* Modelle und deren Anbindung
* Chat - zahllose Einstellungen dazu, wie du mit Goose interagierst und z.B. Erklärungen zu den verschiedenen Modi
* Sessions-Einstellungen zum Teilen von Arbeiten in Goose mit anderen
* App-Settings für bspw. das Erscheinungsbild der App
* uvm.
  ein.

---

## **1.2 Hauptbereich (rechts)**

Hier spielt sich alles ab:

* Oben: Session-Titel, Modell-Auswahl
* Mitte: Chat-Verlauf
* Unten: Eingabefeld + File-Attach + Modell-/Tool-Selector

Die Oberfläche ist bewusst minimal, damit du dich auf die Interaktion mit der AI konzentrieren kannst.

---

## **1.3 Modell-Auswahl (unten im Eingabebereich)**

Ganz unten rechts findest du:

* **Modell-Selector**
* **Modus-Auswahl** (z. B. Chat only / Smart / Manual / Autonomous)
* **Tokenverbrauch**
* **Status-LED** (grün = verbunden)

---

# 🧠 **2. Modelle einrichten & empfehlen**

Die vollständige Provider-Konfiguration findest du im `/goose/readme.md`.
Hier eine kurze Übersicht der **empfohlenen Modelle für den Contest**:

---

## 🦙 **KIARA (Uni Leipzig URZ Cluster)**

**Modell:**
`vllm-meta-llama-llama-3-3-70b-instruct`
**Vorteile:**

* gute Coding-Qualität
* schnell
* läuft *"on-prem"*, ist also *"kostenlos"*
* ausreichendes Modell für die meisten Tasks
* ideal, wenn wir die Rate-Limits ausreizen

---

## 🛠️ **Mistral – devstral-2512**

**Status:** derzeit kostenlos, da neuer Model-Launch (09.12.2025)
**Vorteile:**

* aktuell sehr starkes (kleines) Coding Modell 
* neueste Coding-Skills
* schlägt aktuell auch große Modelle, laut Benchmarks

---

## 🧠 **OpenAI – gpt-4.1**

**input**: $3/MTok
**output**: $12/MTok

**Vorteile:**

* gute Codequalität
* gut im Multi-Step-Reasoning
* auch geeignet für komplexe Aufgaben

[Pricing](https://openai.com/de-DE/api/pricing/)

---

## 🤖 **Anthropic – claude-sonnet-4-0**

**input**: $3/MTok
**output**: $15/MTok

**Vorteile:**

* Top im Verständnis großer Projekte
* Sehr stark beim Erklären & Strukturieren
* Gut für Agent-basiertes Coding
* Nach wie vor *"das beste"* Coding Modell

[Pricing](https://platform.claude.com/docs/en/about-claude/pricing)

---

# 🚀 **3. Goose Desktop – Erste Schritte**

---

## **3.1 Chat starten**

Links auf **Chat** klicken → unten Modell auswählen → schreiben:

> „Hallo Goose! Funktionierst du?“

Wenn eine Antwort kommt → Setup ist erfolgreich.

---

## **3.2 Dateien anhängen**

Ziehe Dateien direkt ins Chatfenster
oder verwende das kleine **📎-Symbol** rechts neben dem Eingabefeld.

Goose analysiert Code, erstellt Zusammenfassungen, refaktoriert, erzeugt neue Dateien etc.

Beispiel:

> „Bitte analysiere diese `main.py` und erkläre, was sie macht.“

---

## **3.3 Python Sandbox (Tool-Use)**

Goose kann Python-Code lokal in einer eigenen (sicheren) Umgebung bzw. Laufzeit ausführen.

Im Chat:

> „Erzeuge eine neue Datei `calc.py` und schreibe eine Funktion, die Grunrechenarten (+, -, *, /) an Beispielen berechnet. Führe sie aus.“

Goose wird:

1. Datei erzeugen
2. Code einfügen
3. Laufzeit starten / ggf. eigene virtuelle Python Umgebung aufsetzen (s. Recipes)
4. Code ausführen & Ergebnis anzeigen

---

## **3.4 Multi-Agent Reasoning**

Goose kann intern mit mehreren Agenten arbeiten (z. B. Analyzer, Builder, Tester).

Beispiel in 3 Chats:

> „Du bist ein Planner Subagent: Erstelle bitte einen Projektplan für einen kleinen HTML/JS/CSS Color Picker und zeige mir die Struktur und die nötigen Dateien.\
Bereite das entsprechend für weitere Subagenten auf!“
> "Du bist ein HTML/JS/CSS Builder Subagent, nimmst den Plan vom Planner Subagent für die Color Picker App entgegen und entgegen und arbeitest den Code aus."
> "Du bist ein Tester Subagent, nimmst den Code vom Builder Subagenten entgegen, liest, prüfst und testest diesen und zeigst das Ergebnis an."

---

## **3.5 Recipes nutzen**

Recipes sind gespeicherte Workflows.
Diese findest du links unter **Recipes**.

Beispiele:

* Dokumentation generieren
* Code analysieren
* bestimmte Tasks automatisieren

---

## **3.6 Scheduler (optional, aber cool!)**

Du kannst Abläufe und Tasks zeitgesteuert laufen lassen.

Beispiele:

* „Analysiere dieses Repo jeden Morgen um 9 Uhr.“
* „Führe dieses ETL-Script stündlich aus.“

Für den Workshop: optional, aber ein tolles Fortgeschrittenen-Feature, wer Lust hat sich reinzufuchsen, gerne testen!

---

# 🧪 **4. Typische Anfängerworkflows**

Damit Teilnehmer *sofort* loslegen können:

---

### **A) Datei generieren und refaktorieren**

> „Erstelle eine Datei `game.py` mit einer TicTacToe-Klasse.“

> „Baue mir eine persönliche Website. Ich bin ...“

---

### **B) Kleine App-Prototypen**

> „Erstelle eine einfache HTML/JS/CSS Webapp, die eine Farbe auswählt und das Ergebnis anzeigt.“


### **C) Projektzusammenfassung**

> „Lies alle Dateien ein und gib mir eine Projektübersicht.“ *Achtung: nur bei bereits vorhandenen Projekten!*

---

# 📚 **5. Weiterführende Funktionen (für Fortgeschrittene)** *...eher für nach dem Meetup!*

Diese Features sind extrem mächtig – ideal nach den ersten Erfolgen:

➡ **Sessions**
→ persistente, wiederverwendbare Chat-Umgebungen

➡ **Recipes**
→ programmierbare Automatisierungen (z. B. CI/CD-ähnliche Workflows)

➡ **Scheduler**
→ zeitgesteuerte Ausführung von Recipes

➡ **Extensions**
→ Tools wie Browser, Dateisystem, Python, Terminal

➡ **Tools**
→ geben Agents Zugriff auf Funktionen (z. B. „FileWrite“, „PythonRun“)

Doku dazu:
👉 [https://block.github.io/goose/docs/category/guides](https://block.github.io/goose/docs/category/guides)

---

# 📝 **6. Tipps für erfolgreiches Vibe Coding in Goose**

* Arbeite **inkrementell** – kleine Prompts → gute Ergebnisse
* Beschreibe dich zu deiner Lösung
* Nutze **Goose** eigens zum testen, um Code schnell zu testen
* Frage die KI bewusst nach *Verbesserungen & Alternativen*
* Nutze **File-Attach**, wenn du Code analysieren lässt oder gar Zeichnungen/Bilder deines Nutzerinferfaces hast- das hilft ggf. schneller zur Lösung und näher\
an deine Vorstellung zu kommen, als es minutiös doch trotzdem vage in Worten zu beschreiben.
* Speichere Workflows als **Recipes**, wenn du sie wieder brauchst, so gewöhnst du dir gleich "best practices" an und sparst dir Zeit/Aufwand

---
