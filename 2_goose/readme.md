# Goose Desktop Installation & Setup Guide**

**Goose Desktop** ist eine lokale, KI-Agent(en) basierte Entwicklungsumgebung für KI-gestützte Workflows und Automation.
Es kombiniert:

* modellagnostische LLM-Anbindung (OpenAI, Anthropic, OpenAI-kompatibel, etc.)
* bietet von Code-Vorschlägen über Code schreiben und ausführen, Fehler beheben bis hin zum koordinieren von Workflows sowie interagieren externer APIs zahlreiche nützliche Features 
* Chat + Tools (MCP) + Agenten 

Dieser Guide führt durch: \
1. Installation 
2. Konfiguration von OpenAI, Anthropic & OpenAI-kompatiblen Endpoints
3. Erste Funktionstests (Chat, Quick-Edit, Model-Check)

---

# **1. Installation**

### **Offizielle Downloads**

Die offiziellen Installationen stehen hier:
➡️ **[https://block.github.io/goose/docs/getting-started/installation/](https://block.github.io/goose/docs/getting-started/installation/)**

Bitte die nötige OS-Plattform wählen und klassich den Installationsprozess durchspielen. \
Weitere Informationen dazu findest du [hier](https://block.github.io/goose/docs/quickstart).

---

# **2. LLM-Provider konfigurieren**

Goose unterstützt zahlreiche Provider von den nahmhaften über Anbieter von Proxys (z.B. OpenRouter, die alle proprietären Modelle hinter ihrer API anbieten) bis hin zu lokal anzubindenden LLM-Backends (Ollama, LMStudio). Wir nutzen heute folgende: 

* **OpenAI**
* **Anthropic**
* **OpenAI-compatible APIs**
  (KIARA Cluster URZ, es gehten aber auch z. B. Ollama, LM Studio)

Die Provider-Konfiguration findest du hier:
➡️ **[https://block.github.io/goose/docs/getting-started/providers/](https://block.github.io/goose/docs/getting-started/providers/)**

In der App unter:
**Settings → *Models*-Tab → *Configure Providers* klicken**

---

## **2.1 OpenAI konfigurieren**

1. API-Key eintragen\
Findet ihr für den Vibe-Coding-Contest über den in den Slides geteilten Cloud-Link.
Alternativ API-Key erstellen:
   [https://platform.openai.com/account/api-keys](https://platform.openai.com/account/api-keys)

2. In Goose:
   **Settings → *Models*-Tab → *Configure Providers* klicken → *OpenAI* auswählen → API-Key eintragen**

3. Weitere Einträge:
   * API-Host `https://api.openai.com` und 
   * Base Path `v1/chat/completions` sollten beide bereits eingetragen sein.

Verfügbare Modelle werden dann automatisch erfragt und für den Chat angeboten. 

---

## **2.2 Anthropic (Claude) konfigurieren**

1. API-Key eintragen\
Findet ihr für den Vibe-Coding-Contest über den in den Slides geteilten Cloud-Link.
Alternativ API-Key erstellen:
   [https://console.anthropic.com/account/keys](https://console.anthropic.com/account/keys)

2. In Goose:
   **Settings → *Models*-Tab → *Configure Providers* klicken → *OpenAI* auswählen → API-Key eintragen**

3. Weitere Einträge:
   * API-Host `https://api.anthropic.com` sollte bereits eingetragen sein.

---

## **2.3 OpenAI-compatible Provider (z. B. KIARA, Ollama, LM Studio)**

Goose unterstützt jede API, die das **OpenAI-v1-Format** spricht.

Doku:
➡️ [https://block.github.io/goose/docs/getting-started/providers/#openai-compatible](https://block.github.io/goose/docs/getting-started/providers/#openai-compatible)

---

### **KIARA Cluster URZ (vLLM)**

1. API-Key eintragen\
Findet ihr für den Vibe-Coding-Contest über den in den Slides geteilten Cloud-Link.

2. In Goose:
   **Settings → *Models*-Tab → *Configure Providers* klicken → *Add custom provider* auswählen**

3. Weitere Einträge:
   * Provider Type: *OpenAI Compatible* auswählen
   * Display Name: KIARA
   * API-URL `https://kiara.sc.uni-leipzig.de/api`
   * API-KEY eintragen
   * Modell(e) eintragen (komma-separiert, falls mehrere eingetragen werden sollen); wir nutzen heute: `vllm-meta-llama-llama-3-3-70b-instruct`
   * *Create Provider* klicken

---

# **3. Erste Tests**

## **Test: Chat / LLM-Provider erreichbar**

1. Links „Chat“ öffnen
2. Falls  nötig unten bei der Texteingabe vom Chat Provider auswählen (OpenAI / Anthropic / KIARA / lokal) oder unter **Settings → *Models*-Tab** (s. oben)
3. Nachricht senden:

> „Hallo Goose! Funktionierst du?“

Wenn eine Antwort kommt → Modell funktioniert.

---

# **4. Weiterführende Features (für Fortgeschrittene)**

Goose bietet viele leistungsstarke Funktionen, die über den Grund-Setup hinausgehen:

🔗 **Guides:**
[https://block.github.io/goose/docs/category/guides](https://block.github.io/goose/docs/category/guides)

Empfohlen für Contest-Teilnehmende:

* **Multi-Sessions** – persistente Arbeitskontexte über diverse Chats (Stichwort *Sub-Agents*)
* **Recipes** – wiederverwendbare automatisierte Abläufe
* **Scheduler** – zeit- oder eventbasierte Agent-Runs
* **Tools** – Dateisystem, Python, Bash, Browser, Custom Tools
* **Extensions** – diverse Integrationen / Anbindungen via MCP (Model Context Protocol)

Diese Features erlauben echtes **Vibe Coding mit autonomen Agenten**.

# **5. Troubleshooting**

### **„401 Unauthorized“**

→ Falscher API-Key
→ Falscher Endpoint 

### **„Model not found“**

→ Modellname exakt prüfen

### **Keine Antwort**

→ Netzwerkblocker / Firewall
→ ggf. timeout?
→ LMStudio/Ollama/vLLM nicht gestartet

---
