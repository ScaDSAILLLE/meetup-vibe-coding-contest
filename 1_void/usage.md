# **VOID IDE Usage Guide**

Dieser Guide erklärt dir **die grundlegende Bedienung der VOID IDE**, zeigt dir die wichtigsten Bereiche der Benutzeroberfläche, die ersten Schritte mit Chat, Quick Edit & Agent-Modus und gibt Empfehlungen, welche Modelle du beim Vibe Coding Contest nutzen solltest.

---

# 🖥️ **1. Überblick über die VOID Oberfläche**

Basierend auf folgendem Screenshot:

![VOID UI](../media/void_ide.png)

Die VOID IDE ist ein **VS-Code-Fork**, somit ist die Bedienung vertraut, aber erweitert um drei KI-spezifische Bereiche:

---

## **1. Explorer (linke Sidebar)**

Hier findest du:

* Projekt- und Dateiübersicht
* Ordner & Dateien per Klick öffnen
* Kontextmenü wie gewohnt
* Virtuelle Umgebungen oder Build-Files (z. B. `pyproject.toml`)

**Tipp:**
Die KI arbeitet besser, wenn du das **Projekt einmal indexieren lässt** → über *Void: Gather* (oben im Chat-Fenster).

---

## **2. Editor-Bereich (Mitte)**

Hier schreibst und bearbeitest du deinen Code.
VOID bringt zwei KI-Funktionen direkt in den Editor:

### **a) Chat („Add to Chat“) → `Ctrl + L`**

Markiere Code → starte eine Diskussion über Änderungen.

### **b) Quick Edit („Edit Inline“) → `Ctrl + K`**

Markiere Code → lasse ihn *direkt inline* umschreiben, erweitern, kürzen, refaktorisieren.

---

## **3. Chat-Sidebar (rechte Seite)**

Das ist der Hauptarbeitsbereich für Vibe Coding:

* Prompt-Eingabe → natürliche Sprache
* Kontext: Datei, Workspace, ausgewählter Code
* Agent-Modus → AI führt aktive Aktionen aus (z. B. Code erzeugen / ändern)
* Gather-Modus → AI analysiert das Projekt
* Chat-Modus → klassische Unterhaltung

Hier wählst du auch das **Modell**, z. B.:

➡ *vllm-meta-llama-llama-3-3-70b-instruct*
➡ *devstral-2512*
➡ *gpt-4.1*
➡ *claude-3.5-sonnet (claude-sonnet-4-0)*

Die Modell-Picker befinden sich direkt über dem Texteingabefeld.

---

## **4. Statusleiste (unten)**

Hier siehst du:

* aktive Branches
* Linter & Interpreter
* Hinweis, ob VOID die KI erfolgreich erreicht
* Fehlermeldungen (z. B. rate limit / kein API-Key)

---

# 🚀 **2. Erste Schritte in VOID**

---

## **2.1 Chat öffnen**

Shortcut:

```
Ctrl + L
```

oder:

Menü → *View → Open View → Chat*

Dann:

> „Hallo, kannst du mir erklären, was in dieser Datei passiert?“

Wenn die KI antwortet → Setup funktioniert.

---

## **2.2 Quick Edit (Inline Edit)**

Markiere Code (z. B. in `hello_world.py`):

```python
def main():
    print("Hello, World!")
```

Drücke:

```
Ctrl + K
```

Beispiel-Prompt:

> „Mach daraus eine Funktion, die einen Namen annimmt und personalisiert grüßt.“

VOID ersetzt nun direkt die markierte Stelle.

---

## **2.3 Agent-Modus**

Im Dropdown rechts oben → *Agent* wählen.

Agenten können:

* Dateien anlegen
* gesamte Module refaktorieren
* Features implementieren
* Code reorganisieren

Beispiel:

> „Erstelle mir bitte eine Python-Datei `game.py` mit einer kleinen TicTacToe-Klasse.“

---

## **2.4 Gather-Modus**

Gather liest das Projekt ein.

Benutzen, wenn du willst:

* Code-Kontext aggregieren
* Architektur analysieren
* Zusammenhänge verstehen

Prompt-Beispiel:

> „Fasse mir die Struktur dieses Projekts zusammen und schlage Verbesserungen vor.“

---

# 🔧 **3. Empfohlene Modelle für den Contest**

Diese Modelle funktionieren erfahrungsgemäß *sehr gut* in VOID und sind ideal für den Workshop:

---

## 🦙 **KIARA (Uni Leipzig URZ Cluster)**

**Modell:**
`vllm-meta-llama-llama-3-3-70b-instruct`
**Vorteile:**

* sehr gute Coding-Qualität
* schnell
* kostenlos nutzbar
* ideal für Einsteiger

---

## 🛠️ **Mistral – devstral-2512**

**Status:** kostenlos
**Vorteile:**

* sehr stark beim Refactoring
* moderne Coding-Skills
* gut für Webentwicklung & JS

---

## 🧠 **OpenAI – gpt-4.1**

**input**: $3/MTok
**output**: $12/MTok

**Vorteile:**

* hervorragende Codequalität
* gut im Multi-Step-Reasoning
* ideal für komplexe Aufgaben

[Pricing](https://openai.com/de-DE/api/pricing/)

---

## 🤖 **Anthropic – claude-sonnet-4-0**

**input**: $3/MTok
**output**: $15/MTok

**Vorteile:**

* Top im Verständnis großer Projekte
* Sehr stark beim Erklären & Strukturieren
* Gut für Agent-basiertes Coding

[Pricing](https://platform.claude.com/docs/en/about-claude/pricing)

---

# 📂 **4. Weitere VOID Ressourcen**

VOID ist noch jung — die Dokumentation wächst. Hier findest du das Wichtigste:

* **VOID Docs (Overview):**
  *[https://voideditor.com/docs](https://voideditor.com/docs)* *(Platzhalter – bitte später ersetzen)*

* **Video: Einführung in VOID**
  *[https://youtu.be/PLACEHOLDER](https://youtu.be/PLACEHOLDER)* *(Platzhalter – kann ersetzt werden)*

* **GitHub Repo**
  [https://github.com/voideditor/void](https://github.com/voideditor/void)

---

# 🧪 **5. Typische Workflows für Anfänger – Beispiele**

### **A) Neue Datei generieren lassen**

> „Erstelle mir eine Datei `utils.py` und füge eine Funktion `calculate_stats()` ein, die aus einer Liste Mittelwert & Median berechnet.“

### **B) UI-Template generieren (Web)**

> „Erstelle mir eine einfache HTML+JS App mit einem Button, der ein zufälliges Meme anzeigt.“

### **C) Python-Projekt analysieren**

> „Schau dir alle Dateien an und fasse mir zusammen, was das Projekt macht.“

### **D) Fehler finden**

> „In `main.py` gibt es einen Bug – finde und behebe ihn bitte.“

---

# 📝 **6. Tipps für erfolgreiches Vibe Coding in VOID**

* **Arbeite iterativ** – kleine Schritte erzeugen bessere Ergebnisse.
* **Nutze Quick Edit großzügig** – es ist eines der mächtigsten Features.
* **Wechsle zwischen Chat, Gather und Agent-Modus** je nach Ziel.
* **Zeige der KI Beispiele** – sie lernt deinen Stil schnell.
* **Setze das Modell bewusst** – stärkere Modelle für komplexe Aufgaben.

---
