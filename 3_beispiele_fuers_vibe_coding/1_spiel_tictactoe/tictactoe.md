# **Beispiel 1 – TicTacToe (Python) mit Goose Desktop**

Dieses Beispiel zeigt, wie du mit **Goose Desktop** und einem starken Coding-Modell (z. B. *devstral-2512*, *Llama-3-70B-Instruct*, *gpt-4.1*, *claude-sonnet-4.0*) Schritt für Schritt ein TicTacToe-Spiel in Python entwickelst.

Wir gehen dabei so vor, wie es AI-Coding-Best-Practice empfiehlt:

* **eigener Projektordner**
* **eigene virtuelle Umgebung (uv)**
* **klare Datei-Struktur & `pyproject.toml`**
* Nutzung von **Goose Chat** für Code-Erstellung
* Nutzung eines **Goose Recipes**, das die Struktur automatisch erzeugt

---

# 📁 **1. Projekt anlegen**

Erstelle einen Ordner z. B.:

```
~/vibe_projects/tictactoe
```

Öffne Goose Desktop und wähle unten den Ordner aus
(*unten links in der Leiste auf den Ordnernamen klicken → „Change directory“*).

---

# 🐍 **2. Virtuelle Umgebung mit uv erzeugen**

Falls du `uv` installiert hast (empfohlen):

📌 Im Chat eingeben:

> Erstelle bitte für dieses Projekt eine neue uv-venv und ein minimalistisches `pyproject.toml`, sodass ich eine moderne Python-Projektstruktur habe.

Goose führt (über das Python-Tooling) typischerweise Kommandos aus wie:

```bash
uv init
uv venv
```

oder erzeugt Dateien wie:

```toml
# pyproject.toml (Minimal)
[project]
name = "tictactoe"
version = "0.1.0"
requires-python = ">=3.10"
```

➡ Vorteil: Die KI bekommt eine **saubere Entwicklungsumgebung**, und Goose kann Python-Code automatisch in der Sandbox ausführen.

Falls du kein uv nutzt → Goose anweisen, **venv** zu verwenden.

---

# 🧠 **3. Grundgerüst per Goose Chat erzeugen**

Öffne **Chat** und schreibe:

> Bitte lege eine Datei `tictactoe.py` an.
> Erstelle darin eine Klasse `TicTacToe` mit folgendem Grundgerüst:
>
> * 3×3 Spielfeld als Liste von Listen
> * Methode `make_move(player, row, col)`
> * Methode `check_winner()`
> * Methode `is_draw()`
>   Schreibe sauberen, gut kommentierten Python-Code.

Goose wird:

1. Die Datei erzeugen
2. Den Code einfügen
3. Dir eine Zusammenfassung geben

---

# 🧪 **4. Code testen (Goose Sandbox)**

Im Chat:

> Führe bitte `tictactoe.py` in der Python-Sandbox aus und teste folgenden Ablauf:
>
> * Spieler X setzt auf Position (0,0)
> * Spieler O setzt auf Position (1,1)
> * Spieler X setzt auf Position (0,1)
> * Spieler O setzt auf Position (2,2)
> * Spieler X setzt auf Position (0,2)
>
> Sage mir anschließend, wer gewonnen hat oder ob ein Fehler auftritt.

Goose führt den Code in einer **isolierten Python-Umgebung** aus und zeigt das Ergebnis.

---

# ♻️ **5. Refactoring per Quick Chat**

Beispiel:

> Bitte refaktoriere die Klasse so, dass sie Exceptions wirft, falls ein Feld bereits belegt ist.
> Und ergänze eine Methode `print_board()` zur Visualisierung.

oder:

> Schreibe Unit Tests für die Klasse in einer neuen Datei `test_tictactoe.py` und führe sie aus.

---

# ⚙️ **6. TicTacToe erweitern**

Jetzt kannst du die KI kreativ nutzen:

### 💡 Vorschläge:

* „Baue ein CLI-Menü“
* „Baue einen minimax-Computergegner“
* „Baue eine einfache Weboberfläche via Flask oder FastAPI“
* „Exportiere das Board als JSON“
* „Logge alle Spielzüge“

---

# 🧩 **7. BONUS: TicTacToe per Goose Recipe generieren lassen**

Wenn du zeigen willst, wie man **automatisierte Vibe-Coding-Workflows** baut, nutze **Recipes**:

1. In Goose links **Recipes → New Recipe**
2. Name: `init_tictactoe_project`
3. Schritte definieren (z. B.):

```yaml
steps:
  - tool: python
    code: |
      import os
      os.makedirs("tictactoe", exist_ok=True)
  - write_file:
      path: tictactoe/pyproject.toml
      content: |
        [project]
        name = "tictactoe"
        version = "0.1.0"
        requires-python = ">=3.10"
  - agent:
      prompt: |
        Erzeuge bitte die Datei `tictactoe/tictactoe.py` mit einer TicTacToe-Klasse,
        die Spiellogik, Gewinnerkennung und eine einfache CLI bietet.
```

4. **Recipe starten**

Goose erzeugt nun automatisch:

* Ordner
* Projektdateien
* funktionsfähigen Code

➡ Das ist perfektes „Vibe Coding auf Autopilot“.

---

# 🧗 **8. Optional: Web-Variante oder separater Branch**

Falls Teilnehmende Web lieber mögen:

> Erstelle eine Datei `index.html` mit einem 3×3 Grid, das TicTacToe spielbar macht.
> Nutze CSS für Hover-Effekte und JS für die Spiel-Logik.

Goose kann auch:

* CSS generieren
* Animationen hinzufügen
* lokale Tests ausführen

---

# 🏁 **9. Mini-Challenges für Teilnehmende**

### **Level 1 – Basis**

* Gewinnerlogik reparieren
* Input validieren
* Board hübscher ausgeben

### **Level 2 – Mittel**

* CLI Menü
* mehrere Spielmodi
* Undo-Funktion

### **Level 3 – Fortgeschritten**

* KI-Gegner (minimax)
* WebUI
* Multiplayer über WebSocket

### **Level 4 – Ultra**

* Goose Recipe: Gestalte aus dem Gelernten ein Recipe, dass jedwedes (simple) Spiel erstellen kann. Lasse die Erfahrungen aus dem Beispiel hier einfließen.
* Goose Scheduler: z.B. automatisches Testen jede Stunde oder neue Spielvariante pro Tag?

---

# ✔️ **Fertig!**

Dies ist Beispiel 1 des Workshops.
Es zeigt, wie man mit **Vibe Coding + Goose Desktop**:

* ein Projekt strukturiert
* Code generiert
* Gooses Code-Ausführung nutzt
* Refactoring/Codeverbesserung betreibt
* und sogar Automatisierung per Recipes baut
