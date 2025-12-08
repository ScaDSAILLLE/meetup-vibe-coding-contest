# **Void IDE – Installation & Setup Guide**

Void ist ein **Open-Source AI-Code-Editor**, der auf **VS Code** basiert und leistungsfähige KI-Funktionen wie Chat, Code-Transformationen, Inline-Edits und Multi-LLM-Support bereitstellt.
Dieser Guide führt durch:

1. Installation 
2. Konfiguration von OpenAI, Anthropic & OpenAI-kompatiblen Endpoints
3. Erste Funktionstests (Chat, Quick-Edit, Model-Check)

---

## **1. Installation**

### **Offizielle Downloads**

Die aktuellen Builds findest du unter:
➡️ **[https://voideditor.com/download](https://voideditor.com/download)**

Bitte die nötige OS-Plattform wählen und klassich den Installationsprozess durchspielen.

---

## **2. KI-Modelle konfigurieren**

Void unterstützt zahlreiche LLM-Backends/Provide/lokale Setups, ist also modelagnostisch. \
Entweder beim ersten Start oder in den *Void Settings*. \
Wir zeigen hier, wie man beispielhaft OpenAI-, Anthropic- und eine "openai-compatible"-API anbindet.

* **OpenAI / OpenAI-Platform**
* **Anthropic (Claude)**
* **OpenAI-compatible APIs**
  (z. B. **Ollama**, **vLLM**, **LM Studio**, **OpenRouter**, Self-Hosted Gateways)

Die *Void Settings* findest du in Void unter:

> **Linksklick auf Zahnrad-Symbol unten links → öffnet Menü → linksklick auf *Void Settings***

Oder über `Ctrl` + `Shift` + `p` → *„Void Settings“* suchen und `Enter` klicken.

---

## **2.1 OpenAI**

**Anleitung:**

1. API-Key eintragen\
Findet ihr für den Vibe-Coding-Contest über den in den Slides geteilten Cloud-Link.
Alternativ API-Key erstellen:
   [https://platform.openai.com/account/api-keys](https://platform.openai.com/account/api-keys)

2. In Void eintragen: \
***Void Settings* → Main Providers → OpenAI → API-KEY eintragen**

---

## **2.2 Anthropic (Claude)**

1. API-Key eintragen:\
Findet ihr für den Vibe-Coding-Contest über den in den Slides geteilten Cloud-Link.
Alternativ API-Key erstellen:
   [https://console.anthropic.com/account/keys](https://console.anthropic.com/account/keys)

2. In Void eintragen: \
***Void Settings* → Main Providers → Anthropic → API-KEY eintragen**

---

## **2.3 OpenAI-compatible (Ollama, vLLM, LM Studio etc.)**

### **KIARA Cluster URZ Beispiel**

Void-Konfiguration:

| Feld         | Eintrag                                 |
| ------------ | --------------------------------------- |
| API Endpoint | `https://kiara.sc.uni-leipzig.de/api`   |
| API Key      | s. Cloud                                |
| Model        | `vllm-meta-llama-llama-3-3-70b-instruct` |

### **2.4 Lokales Setup: LMStudio Beispiel**

1. LMStudio lokal installieren und starten, s. [Link](https://lmstudio.ai/)

2. In LMStudio unter "Entwickler" die API einschalten und in den nebenstehenden *"Server Settings"* "Im lokalen Netzwerk bereitstellen" einschalten.

3. In den *"Void Settings"* unter *Local Providers* in *LMStudio* `http://localhost:1234` eintragen.

Schon kannst du deine lokalen LLMs mittels LMStudio API in Void verwenden.

---

## **3. Erste Tests**

### **Test 1: Chat öffnen**

* Falls nicht bereits in der Sidebar geöffnet:
    * *"View"* in der Menüleiste klicken → *"Open View..."* wählen → *"Chat"* wählen → öffnet die Chat-Sidebar
    * `Ctrl` + `Shift` + `P` → „Chat“ eingeben → "Chat Focus on View" auswählen → öffnet die Chat-Sidebar
* Prüfen, ob richtiger "Provider" sowie korrekter Mode eingestellt ist 
    * für diesen Test *Chat*
    * *Gather*, um Ordner und Projekte einzulesen 
    * *Agent*, um etwas erstellen/ändern zu lassen

* Schreiben: 
    > "Hallo! Funktionierst du?"

Wenn ein Response kommt → LLM-Integration läuft.

---

### **Test 2: Code Quick-Edit**

Code Beispiel in `hello-world.py` anlegen:
```python
def main():
    print("Hello, World!")

if __name__ == "__main__":
    main()
```

1. Eine Codezeile markieren
2. *"Add to Chat"* bzw. `Ctrl` + `L` oder *"Edit inline"* bzw. `Ctrl` + `K`wählen.
3. Prompt Beispiel:

   > `Ändere das zu "Hallo {name}“`

Wenn der Code ersetzt/ergänzt wird → Editor-Integration funktioniert.

---

## **4. Troubleshooting**

### **„401 Unauthorized“**

→ Falscher API-Key
→ Falscher Header
→ Falsche Endpoint-URL

### **„Model not found“**

→ Modellname exakt prüfen

### **Keine Antwort**

→ Firewall / Proxy
→ Void benötigt Internetzugriff (außer bei lokalen Models)

---

## **5. Weitere Links**

* Offizielle Seite: [https://voideditor.com](https://voideditor.com)
* GitHub Repo: [https://github.com/voideditor/void](https://github.com/voideditor/void)
* Community / Issues: [https://github.com/voideditor/void/issues](https://github.com/voideditor/void/issues)

---
