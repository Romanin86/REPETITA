# Palais Mental

[Français](README.fr.md) · **English**

A memory-palace and spaced-repetition study tool contained in **a single HTML file**. No installation, no account, no server of your own, no connection required.

Version 9.0 · **[romanin86.github.io/REPETITA](https://romanin86.github.io/REPETITA/)**

> **The interface is in French.** Button and menu names in this document are translations; the original French label is given in brackets where it helps you find it on screen.

---

## Quick start

**Online** — open **[romanin86.github.io/REPETITA](https://romanin86.github.io/REPETITA/)** in Firefox, Chrome or Edge. That's it.

**Offline** — in the application, Settings → Advanced → **Download the application** [*Paramètres → Avancé → Télécharger l'application*]. You get a single file, `palais-mental-v9.0.html`, which works without a connection, from disk or a USB stick. The same file is in this repository: `index.html`, with every version in `APPLICATIONS/`.

**On first launch**, the home screen offers four ways in: try a sample palace, create with an AI, import a spreadsheet, create by hand.

For your students, the application produces a standalone **reader file**, distributed like any other file.

**A word you don't know?** The **Glossary** [*Glossaire*], in the side menu, defines every term of the application in one sentence and tells you where to find it.

---

## Privacy, offline use, security

**Everything stays on your device.** Once the page has loaded, the application contacts no server: no Google, no analytics, no downloaded fonts, no external libraries. Everything it needs is inside the file.

**Everything works offline**, application and reader file alike: creating content, reviewing, reminders, reading aloud with the device's voices, spreadsheet import and export, backups, ZIP archives.

Only a few **optional** features use the internet, and only when you trigger them: image generation, free-licence photo and definition search, the buttons that open an AI from the prompt generator, and the online voices for reading aloud, if you allow them.

**Imported content is treated as untrusted.** A crafted spreadsheet, pasted AI answer or backup cannot execute code: text is neutralised before display, and only `https://` or `http://` web addresses can be opened.

---

## Platforms and browsers

| Platform | File opened from disk | The website, or any web address |
|---|---|---|
| **Windows, macOS, Linux — Firefox** | Full | Full |
| **Windows, macOS, Linux — Chrome, Edge** | Reduced capacity, see below | Full |
| **Android — Firefox, Chrome** | Full | Full |
| **iPad, iPhone** | Not supported | Not supported |

**Chrome and Edge** refuse full storage to files opened from disk. The application then switches to fallback storage and says so with a banner: everything works, but capacity drops to a few megabytes, quickly insufficient with images. Two solutions: open the file in **Firefox**, or use **the website**.

**The reader file** does not have this limit: a student's progress weighs a few kilobytes, which fallback storage handles easily.

**On a network drive**, use a drive letter (`Z:`) or a web address rather than a `\\server\share` path, which some browsers block. Data is never written to the share: each user has their own, on their own machine, and twenty students can open the same file at once.

**On iPad and iPhone**, the Files app preview does not execute JavaScript: the application cannot start from a local file. A message explains this instead of showing a blank page.

---

## Two forms

| | **The application** | **The reader file** |
|---|---|---|
| Who it's for | The teacher | The students |
| Create, edit, delete | Yes | No |
| Review, schedule reminders, listen to cards | Yes | Yes |
| Where progress is saved | On your device | On the student's device, never touching your copy |

---

# Part one — The application

## 1. How content is organised

Three levels, from broad to precise:

- **Palace** — a subject, a syllabus, a theme. *"Year 10 History"*
- **Room** — a chapter, a topic. *"The Second World War"*
- **Object** — a card, one thing to remember. *"D-Day landings"*

An object holds a **title** (the question), the **information to remember** (the answer), and optionally an **image**, a **mnemonic phrase**, **tags** and an **attached document**.

The sort order chosen on the home screen applies to every palace list in the application. In a room that contains images, each card shows its own as a thumbnail: every card keeps the same size.

## 2. Creating content

The **New palace** button [*Nouveau palais*] offers every route:

- **Create with an AI** [*Créer avec une IA*] — the prompt generator, the easiest way to start, see the next section.
- **Paste an AI's answer** [*Coller la réponse d'une IA*] — the table copied from the conversation, with no file and no spreadsheet software. Handy on a phone.
- **Import a spreadsheet**, filled in by hand or by an AI. Download the blank template from Settings → Create and organise content → Spreadsheet import/export [*Paramètres → Créer et organiser le contenu → Import / export tableur*]. One row = one card; missing palaces and rooms are created on import.
- **Create by hand**, palace by palace.
- **The sample palace** [*Palais d'exemple*], which teaches the application by using it.

You can also **import a backup** or an archive, JSON or ZIP.

> The spreadsheet column names stay in French — `palais`, `salle`, `objet`… — because they are the headers the application expects. See "Spreadsheet columns" below.

**An AI rarely delivers a perfect table**: a code block, a sentence before and after, a markdown table, empty columns left out. Pasting and `.csv` import catch these flaws. Whatever remains ambiguous — one column too many or too few in the middle of a row — is **set aside and reported**, never imported shifted.

**After an import**, a summary [*Import terminé*] confirms everything is saved — number of cards, details per palace, rows set aside — and offers, **as an option**, to add images, with an estimate of the time needed. This can also be done later.

## 3. The prompt generator

It writes the request to give an AI for you. Side menu → **Prompt generator** [*Générateur de prompt*].

**First, the approach** [*Votre approche*]:

| Approach | What it produces | Its own settings |
|---|---|---|
| **Memorise** [*Mémoriser*] | Short, independent cards: vocabulary, dates, definitions, formulas | Content types; in Expert, "Method" and "Trap" lines, mnemonics, answer length |
| **Understand to remember** [*Comprendre pour retenir*] *(experimental)* | A chain of questions that build on each other — why, how, what happens if… Rooms become the steps of a progression | Question types, editable ("Manage" [*Gérer*]); in Expert, prior knowledge, "Challenge" and "Explain" lines, mnemonic column, explanation length |
| **Tell a story** [*Raconter une histoire*] *(experimental)* | The palace becomes the setting of a story: each room is a place the hero passes through. The story passage reads in walk-through and serves as a hint in review, with the answer masked | Genre, hero, foreign-language learning (told in French or in the target language, level A1 to B2); in Expert, passage length |
| **Step-by-step sentences** [*Phrases pas à pas*] *(experimental)* | Simple sentences, longer and longer, that students rebuild by putting the words back in order. Each room is a level. For special-needs classes, French as a foreign language, early primary | Reading level (from first grade to upper primary), separate from the audience's age; levels; sentence length; constructions to practise; characters' first names; above the words: a question, a situation to work out, or a title; in Expert, hint and verb tenses |

**Then the level of customisation:**

| Level | What you fill in |
|---|---|
| **Express** | The subject, the audience, the number of cards — or "Let the AI estimate" [*L'IA estime*]. The AI proposes the rest. |
| **Guided** [*Guidé*] — *default* | + palace name, rooms, the approach's own settings, images, favourites |
| **Expert** | + the approach's advanced settings, image style, reference to follow, exclusions |

**The rules of a good card are added automatically**, at every level: a title that never contains the answer, answers that are all different for reverse review, a ban on inventing, no maps or distressing subjects in images. "Step-by-step sentences" adds its golden rule: only one correct way to order the words of each sentence.

**Adapt for** [*Adapter pour*], at every level:
- five boxes that combine: **dyslexia and dysorthographia, dyscalculia, dyspraxia, dysphasia, attention disorders**;
- **students learning French as a second language (FLS)**: 35 home languages to choose from, plus a free field, and a French level from A1 to B1. The AI adds a translation and, where needed, a transliteration into the Latin alphabet. Have it checked by a speaker when possible.

**The result** updates live. "Copy the prompt" [*Copier le prompt*], "Download the blank template" [*Télécharger le modèle vierge*], then eight AIs — Duck.ai, ChatGPT, Copilot, Perplexity, Claude, Gemini, Le Chat, DeepSeek: each button copies the prompt, then opens the site. Attach the blank template and paste. AIs marked **"no account"** [*sans compte*] work without signing in, with a limited number of messages. **"Manage AIs"** [*Gérer les IA*] lets you edit, hide or add AIs, including the built-in ones.

**For free AIs** that cannot produce a file, the prompt asks them for a semicolon-separated CSV table: copy it, then **"Paste the AI's answer"** [*Coller la réponse de l'IA*].

**The library** keeps your prompts: reload them into the form, rename, edit, copy, delete.

## 4. Refining content

Generated content is broadly right, never perfect. **Walk-through** mode [*Parcourir*] steps through cards with no questioning: it is the proofreading mode.

- **Edit** fixes the card and returns you to the same card.
- **The star** marks what deserves to be kept.

**The curation workflow**, to extract the best from a large generated palace:

1. Duplicate the palace ("More" menu [*Plus*])
2. Walk through the copy, starring what you keep
3. Inside a room, click **Favourites** until it reads **"Non favourites"** [*Non favoris*]
4. Select all, delete

Deletion stays undoable for twelve seconds, and a snapshot is taken beforehand.

## 5. Images

Three sources, for one card or a batch:

- **AI generation** — Pollinations.ai, free, no account, key optional
- **Free photo** [*Photo libre*] — Openverse, Wikimedia Commons; author, source and licence are kept
- **Import** from your device

**Style matters more than anything.** "True to subject" [*Fidèle au sujet*] illustrates the concept; the other styles create offbeat scenes, effective for an isolated word. In a batch, the style is fixed for the whole run.

**Batch images** [*Images en lot*]: Settings → Images and online services, or a palace's "More" menu.

## 6. Attached documents

Each card can carry a PDF or an office document. The PDF opens during review, even offline; other formats open in the student's own software. A batch import attaches each file to the card whose title matches its name.

## 7. Reviewing

Review is spaced: a card you knew comes back later, one you missed comes back soon.

**Above each question**, a line shows where the card comes from — *● Year 10 History › The Second World War* — in the palace's colour. You always know where you are, even in a review that mixes several rooms.

**What should be guessed?** [*Que faut-il deviner ?*] Four question types:

| Type | What is shown | What you recall |
|---|---|---|
| **The object's name** [*Le nom de l'objet*] | The image and the information | The title |
| **The information to remember** [*L'information à retenir*] | The title | The answer |
| **Everything, from the location** [*Tout, à partir de l'emplacement*] | Only the room and the rank, as in a real memory palace | Everything |
| **Put the words back in order** [*Remettre les mots dans l'ordre*] | The words of the answer, shuffled | The sentence, see the next section |

**Review settings** [*Réglages de la révision*]: question type, random order, automatic hint, automatic reading, images. During a review: edit the card, star it, **set it aside** [*De côté*] to resume later. An interrupted session is offered for resumption on your return.

**Keyboard**: Space or Enter reveals the answer, then 1, 2, 3, 4 for Again, Hard, Good, Easy [*Encore, Difficile, Bien, Facile*].

## 8. Putting the words back in order

The sentence to remember arrives as **shuffled word tiles**; the student taps them in order. The capital letter of the first word and the final full stop stay on their tiles: they are clues, as in classroom exercises.

**Marking is automatic, with two attempts.** After a first wrong attempt, the words in the right place stay, marked ✓. Right first time, the card counts as "Good"; on the second attempt, "Hard". Missed twice, or given up with "Show the answer" [*Voir la réponse*], the corrected sentence is shown and comes back a little later in the session.

**To turn it on:**
- the spreadsheet's `exercice` column, set to `ordre` — this is what the "Step-by-step sentences" approach produces;
- a card's **"In review, put the words back in order"** box [*En révision, remettre les mots dans l'ordre*];
- a palace's "More" menu → **"Review by putting the words back in order"** [*Réviser en remettant les mots dans l'ordre*], for a whole palace;
- or, for a single review, the **"Put the words back in order"** question type, on any palace.

Information that is too short or too long — fewer than 3 or more than 20 tiles — or written on several lines stays an ordinary question.

> The application only accepts the exact order of the written sentence. A sentence that can be ordered in two correct ways — "Léo lit le soir" and "Le soir, Léo lit" — will be marked wrong. Proofread sentences produced by an AI.

## 9. Reading aloud

A speaker button appears next to titles and answers: in review, in walk-through, on cards and in the reader file. The **language** is set per palace, and a room can switch to another; thirteen languages are offered. Settings → Appearance → **Reading aloud** [*Lecture à voix haute*]: speed, automatic reading of the answer, optional online voices, and a button to test each voice.

The voices are the device's own: a missing voice is installed in the system settings. Every device has its own — check the ones in the computer room.

## 10. Favourites

The star marks a card — in a room, during review or walk-through. Side menu → **Favourites** [*Favoris*] reviews them all, across palaces; **"Walk through favourites"** [*Parcourir les favoris*] rereads them without questioning.

A room's filter has three states: all, favourites, non favourites. **Bulk removal** in Settings → Create and organise content → Favourites.

## 11. Reminders

A reminder series schedules reviews on specific dates: what to revisit, a starting point, intervals — D+1, D+3, D+7…

Ready-made series: **Forgetting curve**, **Progressive**, **Weekly**, **Exam run-up**. All editable. The **Agenda** shows a calendar with colour dots.

The application cannot send notifications itself: it has no server. It creates a **calendar file** that your calendar imports, with one entry per due date, or prepares a ready-written **email**.

## 12. Printing

A palace's or a room's "More" menu → **Print** [*Imprimer*]. Two kinds of sheet: **complete** [*Fiche complète*] — name, information to remember and mnemonic, for rereading — or **practice** [*Fiche d'entraînement*] — names only, followed by blank lines, for written self-testing. Images and mnemonics are optional.

## 13. Backing up, archiving

Settings → Export and back up [*Exporter et sauvegarder*]:

- **Backup & transfer** [*Sauvegarde & transfert*] — the **full backup**, JSON or ZIP: palaces, images, documents, progress, reminders, wallpaper, services, prompt library, edited AIs and question types. And the **archive of selected palaces**, with no settings at all: re-importing it touches nothing else.
- **Automatic backups** [*Sauvegardes automatiques*] — snapshots taken before every risky operation, restorable.

> Service access keys are **never** exported.

**Moving from the website to an offline copy**, or the other way round: data is tied to the address, and the copy starts empty. Make a full backup, then import it into the copy.

## 14. Importing a large base

During an import, a window shows the current step, progress and an estimate of the time remaining. At the end, a summary places the base: **comfortable** under 3,000 cards, **loaded** up to 8,000, **heavy** beyond. These are estimated guidelines, not limits: beyond them everything works, more slowly on a phone. Archive inactive subjects at that point.

## 15. Exporting for students

Settings → Export and back up → **Read-only export** [*Exporter en lecture seule*]:

1. Unfold **"Choose palaces"** [*Choisir les palais*] and tick those to distribute
2. Check the **estimated size** and the comfort indicator
3. Choose a name, or one of the suggestions
4. Tick **"Reset review statistics"** [*Réinitialiser les statistiques*] if the file is for someone else
5. Keep the wallpaper or not, then generate

The reader file opens with your display sort orders; the student can change them.

| Size | What to expect |
|---|---|
| under 8 MB | Comfortable everywhere |
| 8 to 25 MB | Slightly slow to open on older devices |
| 25 to 60 MB | Email attachment often refused |
| over 60 MB | Risk of failure on a phone |

**After a correction, regenerate and redistribute**: a file already handed out does not update itself.

## 16. Wallpaper

Settings → Appearance → Wallpaper [*Apparence → Fond d'écran*], three tabs: **Generate (AI)**, **Free photo**, **Import**. A click places an image in preview; your current wallpaper stays until **"Apply this wallpaper"** [*Appliquer ce fond*], and **"Back to previous wallpaper"** [*Revenir au fond précédent*] undoes it.

## 17. Settings, explanations and glossary

Settings are organised under **five themes**, each with its colour: create and organise content, images and online services, export and back up, appearance, advanced. Each section shows **a one-line summary**, even when folded.

**Appearance**: two themes, Night and Parchment [*Nocturne, Parchemin*], and the reading text size. **Advanced**: download the application, storage status, and a **diagnostic** [*Diagnostic*] to send when something goes wrong — it contains no personal content, only numbers and technical messages.

**Detailed explanations are hidden** and open section by section with the **"?"**. To show them everywhere: Appearance → **"Always show explanations"** [*Toujours afficher les explications*].

**The Glossary** [*Glossaire*] — side menu — defines nearly fifty terms in five families, with a search and, for each word, where to find it. **Progress** [*Progression*] — side menu — shows how memorisation stands, palace by palace.

---

# Part two — The reader file

*Hand this section to students.*

## Opening it

Double-click the file. It opens in your browser. **No connection required**, and nothing is sent anywhere.

If a message says the file cannot open here, it is being shown in a simple preview: open it in Firefox, Chrome or Edge.

## What you can do

**Browse** palaces, rooms and cards, and **search** for a word. **Review**: a question appears, you think, you reveal, you say whether you knew it — or you put the words back in order, and marking is automatic. The line above the question always shows the palace and the room. **Listen** to titles and answers. **Set a review aside** to resume it later. **Schedule your own reminders**, and send them to your calendar. **Sort palaces**.

## What you cannot do

Create, edit or delete anything. The content is what your teacher approved.

## Your progress

It is saved **in your browser, on your device**, and reported to no one. You pick up where you left off on the same device and browser; it does not follow you to another computer.

If the browser refuses all storage, a banner warns you **before** you review for nothing.

---

# Part three — Technical reference

## Accepted formats

| Use | Formats |
|---|---|
| Content import | `.xlsx`, `.ods`, `.csv` (commas or semicolons), pasted table (CSV, markdown or tabs), `.json`, `.zip` |
| Images | `.jpg`, `.png`, `.webp`, `.gif` |
| Attached documents | `.pdf`, `.docx`, `.doc`, `.odt`, `.xlsx`, `.xls`, `.ods`, `.csv`, `.rtf`, `.txt` |

## Spreadsheet columns

| Column | Content |
|---|---|
| `palais`, `salle`, `objet` | Required: palace, room, card title. Missing palaces and rooms are created |
| `contenu` | The information to remember |
| `mnemo` | The mnemonic phrase, or the hint |
| `prompt` | An image description specific to the card, taking priority over the style |
| `tags` | Tags, separated by commas |
| `favori` | `oui` or `non` (yes or no) |
| `image` | An `https://` address of an image to fetch, or empty |
| `exercice` | Optional: `ordre` makes the student put the words back in order in review |

Re-importing a spreadsheet updates cards with the same title in the same room.

## Limits

- **Attached document**: warning above 2 MB, refused above 12 MB
- **Images**: resized to 640 px; wallpaper to 1600 px
- **Reader file**: above 25 MB, email attachment is often refused
- **Words in order**: 3 to 20 tiles, final punctuation included

## Where the data lives

In the browser's storage, **per address** and not per file: two copies of the application opened from the same address share the same base; the website and a downloaded copy each have their own. Data survives closing the browser, but not clearing browser data or changing device.

**Export regularly.** That is the only real backup.

## Image services

- **Pollinations** — AI generation. Delay imposed by the free service: about **16 seconds** for one image, **23 per image in a batch**. With a key: 6 and 9 seconds.
- **Free photos** — Openverse, Wikimedia Commons, and other services you can declare in Settings → Images and online services → Service access keys [*Clés d'accès aux services*].

## Troubleshooting

| Symptom | What to check |
|---|---|
| "Reduced storage in this browser" banner [*Stockage réduit dans ce navigateur*] | Chrome or Edge on a local file: open it in Firefox, or use the website |
| "Cannot open here" message | The file is shown in a preview: open it in Firefox, Chrome or Edge |
| The reader file shows nothing | It comes from an old version: regenerate it |
| Rows set aside on import | The AI's answer is malformed at those points: the summary lists them, fix them or ask for them again |
| Sentences are not shuffled in review | The AI left out the `exercice` column: palace "More" menu → "Review by putting the words back in order" |
| A voice does not read | It is not installed on this device: Settings → Reading aloud |
| Image generation fails | VPNs are often blocked by the service, as is a key whose account has run out of credits |
| Favourites you never set | They came from the imported spreadsheet: bulk removal in Settings → Favourites |
| The application is slow on a phone | See the volume summary: archive inactive subjects |
| A deletion you regret | The undo banner (twelve seconds), otherwise a snapshot |
| Unexpected behaviour | Settings → Advanced → Diagnostic: the report to send |

## Known limitations

- **iPad and iPhone**: not supported.
- **Chrome and Edge on a local file**: reduced storage capacity, see "Platforms and browsers".
- **Words in order**: only one order is accepted, that of the written sentence.
- **SheetJS 0.18.5**, embedded to read spreadsheets, has known vulnerabilities when importing crafted files. Do not import spreadsheets of unknown origin.

## Repository contents

| Folder or file | Content |
|---|---|
| `index.html` | The application, current version — the one the website serves |
| `APPLICATIONS/` | Released versions, from 6.0 to 9.0 |
| `READERS/` | Sample reader files: French for tourists, cybersecurity, French as a second language, a secondary-school demo |
| `SPREADSHEET/` | Palaces ready to import: ten secondary-school subjects, from Year 7 to Year 10 (`Claude/`), and spreadsheets produced with DeepSeek (`INBULK/`) |
| `PROMPTS/` | Sample prompts and the spreadsheets they produced |
| `GETTING_STARTED_GUIDE/` | The template file (`.xlsx`, `.ods`), ready-made prompts, an illustrated tutorial |
| `JSONS/` | Demo backups, to import |
| `manifest.png`, `manifeste fr.png` | The project manifesto: why and how the application came about |

Most of these files are in French.

## Third-party libraries

Embedded in the file, under their respective licences:

| Library | Version | Licence |
|---|---|---|
| Vue | 3.4 | MIT |
| SheetJS | 0.18.5 | Apache-2.0 |
| PapaParse | 5.3.0 | MIT |
| JSZip | 3.10.1 | MIT or GPLv3, at your choice |

## Licence

MIT — see the `LICENSE` file.
