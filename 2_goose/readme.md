# Goose Desktop Installation & Setup Guide**

**Goose Desktop** ist eine lokale, sichere und isolierte Entwicklungsumgebung für KI-gestützte Workflows.
Es kombiniert:

* LLM-Anbindung (OpenAI, Anthropic, OpenAI-kompatibel)
* isolierte Sandboxes für Codeausführung
* Chat + Tools + Agenten

Dieser Guide zeigt nur das **Nötigste für Installation, Setup und erste Tests**.
Vertiefende Features werden unten verlinkt.

---

# **1. Installation**

Die offiziellen Installationen stehen hier:
➡️ **[https://block.github.io/goose/docs/getting-started/installation/](https://block.github.io/goose/docs/getting-started/installation/)**

### **1.1 Download Goose Desktop**

Lade die passende Version herunter:

* **macOS (.dmg)**
* **Windows (.exe)**
* **Linux (.AppImage)**

Downloadseite (offizielle Docs):
[https://block.github.io/goose/docs/getting-started/installation/](https://block.github.io/goose/docs/getting-started/installation/)

### **1.2 Installation je OS**

**macOS**

1. `.dmg` öffnen
2. Goose in „Applications“ ziehen
3. Falls macOS fragt: *„App erlauben“* bestätigen

**Windows**

1. `.exe` starten
2. Installer durchklicken
3. Goose Desktop starten

**Linux**

```bash
chmod +x GooseDesktop*.AppImage
./GooseDesktop*.AppImage
```

Nach der Installation Goose öffnen → du siehst links *Chat*, *Agents*, *Files*, *Run*, *Settings*.

---

# **2. LLM-Provider konfigurieren (nur das Nötigste)**

Goose unterstützt standardmäßig drei Provider:

* **OpenAI**
* **Anthropic**
* **OpenAI-compatible APIs**
  (z. B. Ollama, LM Studio, lokale KI-Cluster wie KIARA)

Die Provider-Konfiguration findest du hier:
➡️ **[https://block.github.io/goose/docs/getting-started/providers/](https://block.github.io/goose/docs/getting-started/providers/)**

In der App unter:
**Settings → Providers**

---

## **2.1 OpenAI konfigurieren**

1. API-Key eingeben
   (Contest-Key aus der Cloud oder selbst erzeugt über [https://platform.openai.com/account/api-keys](https://platform.openai.com/account/api-keys))

2. In Goose:
   **Settings → Providers → OpenAI**

Eintragen:

| Feld     | Beispiel                                   |
| -------- | ------------------------------------------ |
| API Base | `https://api.openai.com/v1`                |
| API Key  | `sk-...`                                   |
| Model    | z. B. `gpt-4.1`, `gpt-4.1-mini`, `o3-mini` |

**Verbindung mit „Test Connection“ prüfen.**

---

## **2.2 Anthropic (Claude) konfigurieren**

1. API-Key eintragen
   (Contest-Key oder: [https://console.anthropic.com/account/keys](https://console.anthropic.com/account/keys))

2. In Goose:
   **Settings → Providers → Anthropic**

Eintragen:

| Feld     | Beispiel                                                       |
| -------- | -------------------------------------------------------------- |
| API Base | `https://api.anthropic.com/v1/messages` *(Standard laut Docs)* |
| API Key  | `sk-ant-...`                                                   |
| Model    | `claude-3-sonnet`, `claude-3-opus`, `claude-3-haiku`           |

**„Test Connection“ klicken.**

---

## **2.3 OpenAI-compatible Provider (z. B. KIARA, Ollama, LM Studio)**

Goose unterstützt jede API, die das **OpenAI-v1-Format** spricht.

Doku:
➡️ [https://block.github.io/goose/docs/getting-started/providers/#openai-compatible](https://block.github.io/goose/docs/getting-started/providers/#openai-compatible)

---

### **Beispiel 1: KIARA Cluster URZ (vLLM)**

| Feld     | Eintrag                                       |
| -------- | --------------------------------------------- |
| API Base | `https://kiara.sc.uni-leipzig.de/api`         |
| API Key  | Contest-Cloud                                 |
| Model    | z. B. `vllm-meta-llama-llama3-3-70b-instruct` |

„Test Connection“ → sollte sofort grün werden.

---

### **Beispiel 2: Ollama (lokal)**

1. Installieren: [https://ollama.com](https://ollama.com)
2. Modell verfügbar machen:

   ```bash
   ollama run llama3
   ```
3. Goose:

| Feld     | Eintrag                     |
| -------- | --------------------------- |
| API Base | `http://localhost:11434/v1` |
| API Key  | beliebig („ollama“)         |
| Model    | `llama3`                    |

---

### **Beispiel 3: LM Studio**

1. LM Studio starten
2. „OpenAI-compatible API Server“ aktivieren
3. Goose:

| Feld     | Eintrag                          |
| -------- | -------------------------------- |
| API Base | z. B. `http://localhost:1234/v1` |
| Model    | Auswahl aus LM Studio            |

---

# **3. Erste Tests**

Analog zu deiner Void-README – minimal, aber funktional.

---

## **Test 1: Chat**

1. Links „Chat“ öffnen
2. Provider auswählen (OpenAI / Anthropic / KIARA / lokal)
3. Nachricht senden:

> „Hallo Goose! Funktionierst du?“

Wenn eine Antwort kommt → Modell funktioniert.

---

## **Test 2: Code-Ausführung**

1. Links „Run“ oder „Sandbox“ öffnen
2. Code eingeben:

```python
print("Hello from Goose Desktop!")
```

3. „Run“ klicken

→ Ausgabe erscheint im unteren Fenster.

---

## **Test 3: Einfacher Agent-Workflow**

1. Links „Agents“ öffnen
2. „Default Agent“ oder eigenen erstellen
3. Prompt:

> „Erstelle drei Projektideen für ein Micro-SaaS.“

Wenn Goose mehrere Schritte ausführt → Agenten funktionieren.

---

# **4. Troubleshooting**

### **„401 Unauthorized“**

→ Falscher API-Key
→ Falscher Endpoint (Achtung: muss `/v1` haben)

### **„Model not found“**

→ Modellname exakt prüfen
→ Bei Ollama Modell vorher „ziehen“

### **Keine Antwort**

→ Netzwerkblocker / Firewall
→ LM Studio/Ollama/vLLM nicht gestartet

---

# **5. Weiterführende Features (für Fortgeschrittene)**

Goose bietet viele leistungsstarke Funktionen, die über den Grund-Setup hinausgehen:

🔗 **Guides:**
[https://block.github.io/goose/docs/category/guides](https://block.github.io/goose/docs/category/guides)

Empfohlen für Contest-Teilnehmende:

* **Sessions** – persistente Arbeitskontexte
* **Recipes** – wiederverwendbare automatisierte Abläufe
* **Scheduler** – zeit- oder eventbasierte Agent-Runs
* **Tools** – Dateisystem, Python, Bash, Browser, Custom Tools
* **Agents** – komplexe Multi-Step Reasoning Workflows
* **Sandboxes** – isolierte sichere Coding-Umgebungen

Diese Features erlauben echtes **Vibe Coding mit autonomen Agenten**.
