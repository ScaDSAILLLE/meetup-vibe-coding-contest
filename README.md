# **Vibe Coding Contest – ScaDS.AI Meetup** 12/2025

---

## 🧠 **Worum geht’s?**

Der **Vibe Coding Contest** ist ein hands-on Workshopformat im ScaDS.AI Living Lab, in dem du lernst:

* was **Vibe Coding** ist,
* warum KI-gestütztes Coding (Agents, LLM-IDE, autonome Workflows) gerade so viel Aufmerksamkeit bekommt,
* und wie du es **selbst praktisch** nutzen kannst, indem du mit modernen AI-Tools software-ähnliche Artefakte erzeugst – spontan, kreativ, iterativ.

**Die Grundidee:**

> *Idee rein → Produkt raus.*

Vibe Coding ist ein AI-getriebener Coding-Workflow, bei dem Software im kreativen Austausch mit einem KI-Agenten entsteht. Planung tritt in den Hintergrund, Flow und Iteration stehen im Fokus. 

Weitere Infos findest du in der [Präsentation](251211_scads_ai_meetup_vibe_coding_contest.pdf)

---

# 📚 **Table of Contents**

* [Einführung](#einführung)
* [Tools](#tools)

  * [VOID](#void)
  * [Goose](#goose)
* [Beispiele & Tutorials](#beispiele--tutorials)
* [Ablauf des Contests](#ablauf-des-contests)
* [Lizenz](#lizenz)

---

# 🛠️ **Einführung**

Dieses Repository stellt **alles bereit, was ihr während des Vibe Coding Contests benötigt**:

* Installations- und Setup-Guides
* Beispielprojekte & Tutorials
* Vorlagen für eure Präsentation
* Links zu API Keys
* Hinweise zur Nutzung der Tools

Entstanden ist das Ganze im Rahmen des ScaDS.AI Meetups „Vibe Coding Contest“.
(Slide S. 14 zeigt den direkten Repo-Link) 

---

# 🧰 **Tools**

Während des Workshops arbeiten wir primär mit **VOID** und **Goose**, zwei AI-Tools mit unterschiedlichen Stärken:

## **VOID**

➡️ **Ordner im Repo:** [`/1_void`](./1_void)\
➡️ **Offizielle Website:** [https://voideditor.com/](https://voideditor.com/)

VOID ist ein **Open-Source AI-Code-Editor**, basierend auf VS Code und ähnlich Cursor, nur eben free. 

Kurz zusammengefasst:

* Bekannte VS-Code-Umgebung + integrierte LLM-Funktionen
* Alternative zu Cursor / GitHub Copilot
* Model-agnostisch: OpenAI, Claude, lokale Modelle (Ollama, vLLM, LM Studio), OpenAI-compatible APIs, ...
* Vollständige Setup-und Nutzeranleitungen findest du im `/void`-Ordner

---

## **Goose**

➡️ **Ordner im Repo:** [`/2_goose`](./2_goose)\
➡️ **Offizielle Docs:** [https://block.github.io/goose/](https://block.github.io/goose/)

Goose ist ein:

* **AI-gestütztes Multi-Agent-System**
* orchestrierbarer **Agent-Workflow** für Development & Automatisierung
* kompatibel mit OpenAI, Anthropic und OpenAI-ähnlichen APIs (z. B. KIARA, LM Studio, Ollama), OpenAI-compatible APIs, ...

Im Ordner `/2_goose` findest du:

* Eine vollständige Setup-und Nutzeranleitungen

---

# 🎮 **Beispiele & Tutorials**

➡️ **Ordner im Repo:** [`/3_beispiele_fuers_vibe_coding`](./3_beispiele_fuers_vibe_coding)

Wir stellen euch mehrere Beispiele zur Verfügung, um die Tools, Agenten und Vibe-Coding-Workflows kennenzulernen:

### **Beispiel 1 – TicTacToe**

Varianten:

* Python in Goose Sandbox
* HTML+CSS+JS in VOID

➡ Eine vollständige Anfänger-Tutorial-Datei liegt im Ordner.

### **Beispiel 2 – Virtuelle Klaviatur**

Ein interaktives Web-Instrument (JS + HTML + Audio).
Perfekt für UI-Events und KI-unterstützte Erweiterungen.

### **Beispiel 3 – *

tba

---

# 🧩 **Ablauf des Contests**

1. Findet euch in Teams oder arbeitet alleine.
2. Macht euch mit VOID & Goose vertraut, richtet eure Tools ein.
3. Sucht Ideen oder nutzt die vorbereiteten Beispiele.
4. **Vibe Coding, Vibe Coding, Vibe Coding.**
5. Bereitet eine kleine Präsentation vor (Vorlage liegt im Repo).
6. Spaß haben, etwas lernen — und die Rate Limits testen. 😉

Achtung: Behaltet Kontext / Tokenverbrauch und Rate Limits im Auge. 

---

# 🔑 **API Keys & Ressourcen**

Die für das Meetup vorgesehenen API Keys findet ihr unter dem in den Slides angegebenen Cloud-Link.

Empfohlen werden folgende Modelle:

* KIARA: *vllm-meta-llamna-llama-3-3-70b-instruct* ((URZ) Uni-Rechenzentrum-gehostetes LLM-CLuster, **free**)
* Mistral: *devstraö-2512* (neuestes Coding-LLM von Mistral! Derzeit ebenfalls **free**)
* OpenAI: *gpt-4.1* (API-Key vorkonfiguriert oder per Cloud-Link zu bekommen; FYI: input: $3/MTok; output: $12/MTok) [Pricing](https://openai.com/de-DE/api/pricing/)
* Anthropic: *claude-sonnet-4-0* (API-Key vorkonfiguriert oder per Cloud-Link zu bekommen; FYI: input: $3/MTok; output: $15/MTok) [Pricing](https://platform.claude.com/docs/en/about-claude/pricing)


---

# 📜 **Lizenz**

Workshop-Material steht unter **CC BY 4.0**, Oliver Welz\
Code: MIT-Lizenz (see [LICENSE](LICENSE.md))

---