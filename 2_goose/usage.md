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
* Python-Sandbox
* Multi-Agent-Workflows

### **📜 History**

Chronologische Liste deiner Chat-Sitzungen.

### **🧪 Recipes**

Automatisierte Workflows, die du selbst bauen oder importieren kannst.

Beispiele:

* „Fasse mein Projekt zusammen“
* „Baue automatisch Dokumentation aus Code“
* „Erzeuge CSV-Berichte“

### **⏱️ Scheduler**

Lässt Recipes zeitgesteuert oder eventbasiert ausführen.

### **🧩 Extensions**

Zukünftige Erweiterungen, Tools, Agent-Packs.

### **⚙️ Settings**

Hier richtest du:

* Modelle
* API-Keys
* Tools
* File-System-Zugriff
* Sandbox-Einstellungen
  ein.

---

## **1.2 Hauptbereich (rechts)**

Hier spielt sich alles ab:

* Oben: Session-Titel, Modell-Auswahl
* Mitte: Chat-Verlauf
* Unten: Eingabefeld + File-Attach + Tool-Selector

Die Oberfläche ist bewusst minimal, damit du dich auf die Interaktion mit der AI konzentrieren kannst.

---

## **1.3 Modell-Auswahl (unten im Eingabebereich)**

Ganz unten rechts findest du:

* **Modell-Selector**
* **Modus-Auswahl** (z. B. Chat only / Tools / Sandbox)
* **Tokenverbrauch**
* **Status-LED** (grün = verbunden)

---

# 🧠 **2. Modelle einrichten & empfehlen**

Die vollständige Provider-Konfiguration findest du im `/goose/README.md`.
Hier eine kurze Übersicht der **empfohlenen Modelle für den Contest**:

---

## 🦙 **KIARA Cluster (Uni Leipzig URZ)**

**Modell:**
`vllm-meta-llamna-llama-3-3-70b-instruct`

Vorteile:

* sehr gute Coding-Performance
* kostenlos
* hohe Kontextlänge
* ideal für Einsteiger

---

## 🔧 **Mistral – devstral-2512** *(kostenlos)*

Perfekt für:

* Refactoring
* schnelle Code-Interpretation
* Python & Webentwicklung

---

## 🧠 **OpenAI – gpt-4.1**

**input:** $3/MTok
**output:** $12/MTok

Vorteile:

* sehr gute Multi-Step-Fähigkeiten
* ideal für komplexe Code-Generierung
* stabil

[Pricing](https://openai.com/de-DE/api/pricing/)

---

## 🤖 **Anthropic – claude-sonnet-4-0**

**input:** $3/MTok
**output:** $15/MTok

Vorteile:

* extrem gut im Erklären
* stark in Projekt-Analyse
* ideal für Refactoring & Architekturfragen

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

Goose kann Python-Code lokal in einer sicheren Umgebung ausführen.

Im Chat:

> „Erzeuge eine neue Datei `calc.py` und schreibe eine Funktion, die Statistiken berechnet. Führe sie aus.“

Goose wird:

1. Datei erzeugen
2. Code einfügen
3. Sandbox öffnen
4. Ergebnis anzeigen

---

## **3.4 Multi-Agent Reasoning**

Goose kann intern mit mehreren Agenten arbeiten (z. B. Analyzer, Builder, Tester).

Beispiel:

> „Erstelle bitte einen kleinen HTML/JS Color Picker und zeige mir die Struktur und die Dateien.“

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

Du kannst Recipes zeitgesteuert laufen lassen.

Beispiele:

* „Analysiere dieses Repo jeden Morgen um 9 Uhr.“
* „Führe dieses ETL-Script stündlich aus.“

Für den Workshop: optional, aber ein tolles Fortgeschrittenen-Feature.

---

# 🧪 **4. Typische Anfängerworkflows**

Damit Teilnehmer *sofort* loslegen können:

---

### **A) Datei generieren und refaktorieren**

> „Erstelle eine Datei `game.py` mit einer TicTacToe-Klasse.“

> „Refaktoriere die Klasse so, dass sie objektorientierter wirkt.“

---

### **B) Kleine App-Prototypen**

> „Erstelle eine einfache HTML/JS Webapp, die eine Farbe auswählt und das Ergebnis anzeigt.“

---

### **C) Sandbox-Tests**

> „Erstelle eine Datei `math_utils.py` und teste sie in der Sandbox mit zufälligen Eingaben.“

---

### **D) Projektzusammenfassung**

> „Lies alle Dateien ein und gib mir eine Projektübersicht.“

---

# 📚 **5. Weiterführende Funktionen (für Fortgeschrittene)**

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
* Nutze **Python Sandbox**, um Code schnell zu testen
* Frage die KI bewusst nach *Verbesserungen & Alternativen*
* Nutze **File-Attach**, wenn du Code analysieren lässt
* Speichere Workflows als **Recipes**, wenn du sie wieder brauchst

---
