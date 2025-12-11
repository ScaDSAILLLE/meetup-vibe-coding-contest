# **Beispiel 2 – Funktionale Klaviatur-UI (Web) mit VOID**

In diesem Beispiel baust du mit Hilfe von **VOID** und einem KI-Modell eine kleine **virtuelle Klaviatur im Browser**:

* Tasten (z. B. C–B) als UI
* Klick auf eine Taste → Ton oder zumindest visuelles Feedback
* Optionale Features: Keyboard-Shortcuts, Sustain, Themes etc.

Der Fokus liegt auf:

* HTML/CSS (Layout & Styling)
* JavaScript (Event-Handling & Audio)
* **Vibe Coding mit Void**: die KI hilft dir beim Aufbau, Refactoring und bei Erweiterungen.

---

## 🎯 Ziel

Am Ende solltest du eine Seite `index.html` haben, die:

* eine Reihe von Tasten anzeigt (weiße & ggf. schwarze Tasten),
* bei **Klick** (oder Tastaturdruck) reagiert,
* idealerweise **einen einfachen Ton** spielt (via Web Audio API oder Audio-Dateien).

---

# 🧰 1. Projekt in VOID vorbereiten

1. Neuen Ordner anlegen, z. B.:

   ```text
   ~/vibe_projects/klaviatur-web
   ```

2. VOID öffnen und diesen Ordner als Workspace wählen.

3. Lege (ggf. per Datei-Menü) zunächst **eine leere `index.html`** an.

---

# 🤖 2. Grundgerüst per VOID-Chat erzeugen

Öffne in VOID die **Chat-Sidebar** (z. B. `Ctrl + L`) und wähle ein geeignetes Modell, z. B.:

* `vllm-meta-llama-llama-3-3-70b-instruct` (KIARA)
* `devstral-2512` (Mistral)
* `gpt-4.1` oder `claude-sonnet-4-0`

Dann schreibe in den Chat (im Modus *Agent* oder *Chat* + „Edit inline“):

> Ich möchte eine kleine Webanwendung bauen: eine virtuelle Klaviatur in HTML/CSS/JS.
> Bitte erstelle mir eine Datei `index.html`, die
>
> * ein simples, responsives Layout enthält,
> * eine Klaviatur mit mindestens einer Oktave (C4 bis B4) anzeigt,
> * jede Taste als Button oder DIV rendert,
> * ein separates `<script>` nutzt, in dem die Grundlogik für Klick-Events vorbereitet ist.
>   Nutze semantisches HTML und moderne, verständliche CSS-Klassen.

Lass VOID die Datei generieren und öffne sie dann im Editor.

---

# 🎹 3. Funktionale Klaviatur – Events & Web Audio

Als nächstes soll die Klaviatur **reagieren**, wenn du auf Tasten klickst:

> Ergänze bitte JavaScript in einem `<script>`-Block in `index.html` (oder in einer separaten Datei `app.js`), das:
>
> * für jede Taste ein `click`-Event registriert,
> * beim Klick die Taste kurz visuell hervorhebt (z. B. andere Hintergrundfarbe),
> * einen einfachen Ton mit der Web Audio API erzeugt (z. B. Sinus-Oszillator),
> * pro Taste unterschiedliche Frequenzen verwendet (C4, D4, E4, …).
>   Nutze eine gut lesbare Datenstruktur (z. B. Array oder Objekt), in dem die Notennamen den Frequenzen zugeordnet sind.

Beispiel, was die KI erzeugen *könnte* (nur als grobe Vorstellung, du lässt es die KI schreiben):

```js
const notes = {
  C4: 261.63,
  D4: 293.66,
  E4: 329.63,
  // ...
};

function playNote(freq) {
  const audioCtx = new (window.AudioContext || window.webkitAudioContext)();
  const osc = audioCtx.createOscillator();
  const gain = audioCtx.createGain();

  osc.type = "sine";
  osc.frequency.value = freq;
  osc.connect(gain);
  gain.connect(audioCtx.destination);

  osc.start();
  gain.gain.exponentialRampToValueAtTime(
    0.0001,
    audioCtx.currentTime + 0.5
  );
  osc.stop(audioCtx.currentTime + 0.5);
}
```

> Falls nötig: Bitte passe den Code so an, dass der AudioContext nicht bei jedem Klick neu erstellt wird, sondern wiederverwendet werden kann.

---

# ⌨️ 4. Keyboard-Shortcuts hinzufügen (optional, aber empfehlenswert)

Lass die KI nun **Tastatur-Eingaben** ergänzen:

> Bitte ergänze Keyboard-Events, sodass folgende Tasten auf der Computertastatur die Klaviatur spielen:
>
> * `A` → C4
> * `S` → D4
> * `D` → E4
> * `F` → F4
> * `G` → G4
> * `H` → A4
> * `J` → B4
>
> Beim Tastendruck soll dieselbe Funktion wie bei einem Mausklick aufgerufen werden.
> Achte darauf, dass `keydown` und `keyup` entsprechend visuelles Feedback (Taste aktiv/inaktiv) geben.

---

# 🎨 5. Styling & UI-Verbesserungen mit VOID

Nun kannst du über **Quick Edit (`Ctrl + K`)** und Chat das Styling verfeinern:

Beispiele für Prompts:

> Mach bitte die Klaviatur optisch mehr wie ein Piano:
>
> * weiße Tasten mit leichtem Schatten
> * schwarze Tasten als Overlay
> * Hover-Effekt (leichter Glow)
> * responsive Layout, das auf kleine Bildschirme skaliert.

> Erstelle bitte eine einfache Titelzeile über der Klaviatur („Vibe Coding Piano“) und zentriere alles.

> Füge unten eine kurze Anleitung hinzu, welche Tasten auf der Computertastatur welche Noten spielen.

---

# 🧪 6. Testen

Öffne die `index.html` in deinem Browser (z. B. per Datei-Explorer oder mit einem kleinen Live-Server).

Checkliste:

* Werden alle Tasten angezeigt?
* Bekommst du visuelles Feedback beim Klicken/Drücken?
* Hörst du Töne?
* Funktioniert die Tastaturbelegung?

Wenn etwas nicht läuft:

> Bitte debugge den Fehler. Die Töne spielen nicht, wenn ich auf die Tasten klicke.
> Erkläre mir, wo das Problem liegt und korrigiere den Code.

---

# 🧩 7. Bonus-Challenges

Wenn du weiter viben möchtest:

* **Skalen- oder Akkord-Modus**

  > Füge Buttons hinzu, mit denen ich Dur- oder Moll-Akkorde mit einem Klick spielen kann.

* **Aufnahme-Funktion**

  > Implementiere eine einfache Recording-Funktion, die die gespielten Noten aufzeichnet und als Liste oder Zeitlinie anzeigt.

* **Metronom**

  > Ergänze ein kleines Metronom, das in einem frei wählbaren BPM taktet.

* **Theme-Switcher** (Dark/Light-Mode)

  > Baue einen Knopf, mit dem ich zwischen hellem und dunklem Design umschalten kann.

---

# 📌 8. Vibe-Coding-Tipps speziell für dieses Beispiel

* Lass dir von der KI zuerst eine **einfache Version** erstellen, dann iteriere.
* Nutze **Quick Edit** für kleine, gezielte Änderungen (z. B. nur Styling).
* Nutze den **Chat**, um dir Code erklären zu lassen, den die KI generiert hat.
* Frage explizit nach **Refactoring** („Bitte mach das lesbarer“ / „Trenne Logik und UI“).
* Scheue dich nicht, die KI um **Bugfixes** zu bitten, wenn etwas nicht funktioniert.

---
