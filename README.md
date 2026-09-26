<div align="center">

# the nano family

**Eleven apps for people who do not code.** No accounts. No internet needed. Nothing to install.

Every app here does one useful thing — talk to an AI, ask a document a
question, find a lost file, keep a folder safe, play your music — and does it
in plain words, on your own computer. Each one is a double-click: it needs
nothing but Python, and it works with the internet switched off.

[![license](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![python](https://img.shields.io/badge/python-3.9+-58a6ff.svg)]()
[![dependencies](https://img.shields.io/badge/runtime%20deps-0-f0883e.svg)]()
[![tests](https://img.shields.io/badge/tests-800%2B%20passing-3ddc97.svg)]()

[The apps](#the-apps) · [How they fit together](#how-they-fit-together) · [The promises](#the-promises) · [Start here](#start-here)

</div>

---

## What this is, in one paragraph

The nano family started as one question: *what if somebody who has never
opened a terminal could still use the powerful things a computer can do?* The
answer grew into a set of siblings that all follow the same rules — one useful
job each, a web page instead of a command line, the Python standard library
instead of an install, your files staying on your machine, and honest words
when something cannot be done. This repository is the map of the family: what
each app is for, how they fit together, and where to get them.

---

## The apps

Every one of these is its own repository, and every one starts the same way:
**double-click `run.bat`** (Windows) or `./run.sh` (macOS/Linux).

| app | what it is for | tests |
|---|---|---|
| 🧭 [**nanoHome**](https://github.com/Agarwalrishu13/nanohome) | One front door for every nano app on this computer — it finds them, explains them, starts them | 53 |
| 🧠 [**nanoLaama**](https://github.com/Agarwalrishu13/nanolaama) | Talk to an AI on your own computer — offline, no account, no key | 23 |
| 📚 [**nanoDoc**](https://github.com/Agarwalrishu13/nanodoc) | Drop in a document, ask it anything — every answer shows the paragraph it came from | 122 |
| 📊 [**nanoLearn**](https://github.com/Agarwalrishu13/nanolearn) | Drop a spreadsheet, get an answer machine — which column matters, and how well it guessed | 32 |
| 🔊 [**nanoSay**](https://github.com/Agarwalrishu13/nanosay) | Have anything read out loud, by the voice already in your computer | 66 |
| 🧲 [**nanoPick**](https://github.com/Agarwalrishu13/nanopick) | Find your files by saying what you remember — "a picture called receipt, last month" | 35 |
| 🎵 [**nanoTune**](https://github.com/Agarwalrishu13/nanotune) | Your music, one page, no account — point it at a folder and press play | 26 |
| 🧰 [**nanoWrap**](https://github.com/Agarwalrishu13/nanowrap) | The programs already on your computer, with buttons — shrink a video, join PDFs, make a zip | 71 |
| ⌨️ [**nanoShell**](https://github.com/Agarwalrishu13/nanoshell) | Any program at all, with words instead of flags — its `--help` becomes a form you fill in | 55 |
| 🗂 [**nanoGit**](https://github.com/Agarwalrishu13/nanogit) | Your folder, kept safe and put online, without learning git — *checkpoints*, not commits | 218 |
| 🖥 [**nanoDesk**](https://github.com/Agarwalrishu13/nanodesk) | Every nano-style app you have, one click away, each explained like to a stranger | 57 |
| 🃏 [**nonoForge**](https://github.com/Agarwalrishu13/nonoforge) | Pick a card, answer two questions, press one button — you have a working app | 42 |

## The engine room

Four repositories for people who want to see the gears — how a small AI is
actually built, trained and run. They are projects rather than tools, and
they are what nanoLaama runs on.

| repo | what it is |
|---|---|
| ⚙️ [**nanollama.c**](https://github.com/Agarwalrishu13/nanollama.c) | The inference engine: run a model in ~1400 lines of C, with nothing to install |
| 🧬 [**nanobrain**](https://github.com/Agarwalrishu13/nanobrain) | Pre-training from scratch: Llama-2 in raw PyTorch, its own tokenizer, every line hand-written |
| 🏗 [**nanoforge**](https://github.com/Agarwalrishu13/nanoforge) | The offline studio: describe an architecture, train it, export it to the engine |
| 🎯 [**nanorl**](https://github.com/Agarwalrishu13/nanorl) | Alignment for tiny models: SFT and DPO from scratch — the step from completing text to answering |

---

## How they fit together

```
                       ┌─────────────┐
                       │  nanoHome   │  the front door: finds every app,
                       └──────┬──────┘  explains it, starts it
                              │
        ┌──────────┬──────────┼──────────┬──────────┐
        ▼          ▼          ▼          ▼          ▼
   everyday     your files  your       your       making
   things       and music   computer   work       things
        │          │          │          │          │
   nanoLaama   nanoPick   nanoWrap   nanoGit    nonoForge
   nanoDoc     nanoTune   nanoShell             (makes new
   nanoLearn              nanoDesk               nano-style
   nanoSay                                        apps)

   the engine room (for people who want the gears):
   nanobrain ──trains──▶ nanoforge ──exports──▶ nanollama.c ──runs──▶ nanoLaama
                                       nanorl ──aligns──┘
```

Every app is a folder with a `start.py`, a small Python package, and a web
page — the same three-part shape, so nanoHome can start any of them with the
same command, and a person who has learned one has learned them all.

---

## The promises

Every app in the family keeps the same five promises:

1. **Nothing to install.** Python 3.9+ and nothing else — `run.bat` is the
   entire setup. Each README says exactly which tests prove it.
2. **Nothing leaves your computer.** No accounts, no telemetry, no uploads.
   The one exception is choosing to press *Put it online* in nanoGit, to the
   GitHub account you picked.
3. **Plain words everywhere.** Buttons say what they do. Failures are
   explained, not printed as exit codes. When an app does not know something,
   it says so instead of guessing.
4. **Nothing is destroyed.** No app deletes, overwrites or moves your files
   without being asked, and "go back" always keeps the newer version.
5. **It works offline.** Airplane-mode approved, every one.

---

## Start here

1. Install Python if you do not have it — [python.org/downloads](https://www.python.org/downloads/) (tick *Add to PATH*).
2. Pick an app from the table above and open its **Releases** page — or see them all with pictures at [agarwalrishu13.github.io/nano](https://agarwalrishu13.github.io/nano/).
3. Download the ZIP, unzip it anywhere.
4. **Windows:** double-click `run.bat`. **macOS / Linux:** `./run.sh`.
5. A browser window opens with the app. That is all there is.

The best first app is [**nanoHome**](https://github.com/Agarwalrishu13/nanohome) —
after that you never have to choose from a list again; it shows whatever is on
your machine.

---

## The machine-readable map

[`apps.json`](apps.json) describes the whole family — ids, names, ports,
repositories — so tools (like nanoHome) can know the family without parsing
prose.

---

## Building your own nano app

The family shape is deliberate and small: an `__init__.py` that says what the
app is, an `__main__.py` with a `doctor` command, a `server.py` that only
answers its own page, a `web/` folder, and tests that run the real thing. The
best templates to read are [nanopick](https://github.com/Agarwalrishu13/nanopick)
(small and complete) and [nanogit](https://github.com/Agarwalrishu13/nanogit)
(the most tested). nonoForge can also generate starter apps for you.

---

MIT license · made by [Priyanshu Agarwal](https://github.com/Agarwalrishu13)
· every app thanks the Python standard library for existing.
