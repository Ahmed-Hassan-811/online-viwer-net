# 💻 Offline Coding Assistant

A self-contained, single-file coding reference that works completely offline. Open it in any browser — no server, no internet, no dependencies required.

Built for developers and beginners who want instant access to snippets across **8 languages**, especially useful in mobile coding environments like Termux and Acode.

---

## ✨ Features

- **100% Offline** — a single `.html` file with zero external dependencies
- **163 Snippets across 8 Languages** — HTML, CSS, JavaScript, Python, Java, Rust, React, and Kotlin
- **Animated Splash Screen** — polished intro animation on load
- **Searchable Snippet Library** — instantly filter by keyword across all snippets
- **Language & Category Filters** — narrow results by language or domain/category
- **Beginner Mode** — toggle plain-English explanations alongside every snippet
- **One-Click Copy** — copy any code snippet to the clipboard with visual feedback
- **Live Header Stats** — real-time count per language shown in the header
- **Termux & Acode Guide** — collapsible built-in setup guide for mobile coding
- **Quick Tips Panel** — contextual tips shown when no filters are active
- **Responsive Design** — works on desktop and mobile screens

---

## 📸 Preview

Open `index.html` directly in your browser — no build step needed.

The app opens with a branded splash screen, then loads the full snippet library. The dark indigo/violet theme is designed for comfortable extended use.

---

## 🚀 Getting Started

### Option 1 — Direct Use
1. Download or clone this repository
2. Open `index.html` in any modern browser
3. Start searching and copying snippets

### Option 2 — GitHub Pages
1. Fork this repository
2. Go to **Settings → Pages**
3. Set the source to your main branch
4. The file will be live at `https://<your-username>.github.io/<repo-name>/`

### Option 3 — Termux & Acode (Android)
1. Copy `index.html` to your device storage
2. Open the file in Acode or any browser (e.g. Firefox, Chrome)
3. Bookmark it for offline use — works with no data connection

---

## 📚 Snippet Library

The built-in library covers **163 snippets** across 8 languages:

| Language | Snippets | Example Topics Covered |
|---|---|---|
| **HTML** | 32 | Document structure, headings, links, images, tables, forms, semantic elements, canvas, SVG, meta tags, data attributes, dialog, details/summary, picture, iFrame |
| **CSS** | 29 | Colors, backgrounds, gradients, typography, box model, flexbox, grid, animations, transitions, media queries, custom properties, clamp(), dark mode, glassmorphism, scroll snap, clip-path, container queries |
| **JavaScript** | 26 | Variables, functions, DOM manipulation, events, loops, arrays, objects, async/await, fetch, localStorage, destructuring, spread/rest, template literals, Map/Set, ES Modules, regex |
| **Python** | 16 | Print, variables, lists, dicts, control flow, loops, functions, OOP, inheritance, file I/O, exceptions, comprehensions, lambda, decorators, generators, imports |
| **Java** | 15 | Hello World, primitives, arrays, ArrayList, switch, loops, methods, encapsulation, inheritance, interfaces, exceptions, HashMap, String methods, streams/lambdas, generics |
| **Rust** | 15 | Hello World, mutability, data types, ownership, borrowing, structs, enums, Option/Result, Vec, traits, closures, iterators, String vs &str, HashMap, threads/Arc/Mutex, lifetimes |
| **React** | 15 | Functional components, useState, useEffect, useRef, useContext, useReducer, custom hooks, conditional rendering, list rendering, useMemo/useCallback, forms, data fetching, fragments, portals, React Router |
| **Kotlin** | 15 | Hello World, val/var, when expression, data classes, null safety, extension functions, classes/inheritance, collections, object/companion, sealed classes, scope functions, coroutines, lambdas, generics, strings |

Each snippet includes:

- A **code example** ready to copy and paste
- A **Technical Description** for experienced developers
- A **Simple Explanation** (in Beginner Mode) using everyday analogies

---

## 🧭 How to Use

### Search
Type into the search bar to filter snippets in real time. Try terms like:

`button`, `form`, `flexbox`, `loop`, `fetch`, `ownership`, `useState`, `coroutine`, `lambda`

### Filters
Click **Show Filters** to reveal dropdowns for:

- **Language** — HTML, CSS, JavaScript, Python, Java, Rust, React, Kotlin
- **Domain/Category** — Structure, Forms, Events, Layout, OOP, Async, etc.

### Beginner Mode
Click **Beginner Mode ON/OFF** to toggle plain-English explanations under each snippet. Great for learners who want to understand *why* code works, not just *what* it does.

### Copy Code
Click the clipboard icon on any snippet card to copy the code. The icon turns green to confirm the copy was successful.

---

## 🏗️ Project Structure

This is intentionally a single-file project.

```
index.html
│
├── <style>          — All CSS: splash screen, layout, cards, animations
├── <body>
│   ├── Splash screen overlay (fades out after ~2.4s)
│   ├── Header with live per-language snippet stats
│   ├── Termux/Acode collapsible guide
│   ├── Search bar + filter controls
│   ├── Quick tips panel
│   └── Snippet grid (rendered dynamically)
└── <script>
    ├── codeDatabase[]   — All 163 snippet objects
    ├── updateStats()    — Populates live header counts per language
    ├── filterSnippets() — Search and filter logic
    ├── renderSnippets() — Dynamic card rendering
    ├── copyCode()       — Clipboard API integration
    └── Splash dismiss   — Auto-hides splash after animation
```

---

## 🎨 Splash Screen

On load, an animated intro screen is displayed featuring:

- Scrolling grid background
- Pulsing glow orb
- Bouncing logo icon with spinning orbit ring
- Staggered fade-up title, subtitle, and language tag pills
- Animated progress bar

The splash automatically fades out after ~2.4 seconds and is removed from the DOM entirely.

---

## 🛠️ Customisation

### Adding Snippets

All snippets live in the `codeDatabase` array inside the `<script>` tag. Each entry follows this shape:

```js
{
    language: "Python",          // "HTML" | "CSS" | "JavaScript" | "Python"
                                 // "Java" | "Rust" | "React" | "Kotlin"
    domain: "OOP",               // Category label shown in the filter dropdown
    task: "Classes and Objects", // Snippet card title
    code_example: `class Dog:
    def __init__(self, name):
        self.name = name`,
    description: "Technical description for experienced developers.",
    simple_explanation: "Plain-English explanation for beginners."
}
```

> **Note:** If your code example contains `</script>` literally (e.g. in an HTML snippet), write it as `<\/script>` to prevent the browser's HTML parser from closing the outer script block early.

### Changing the Theme

The colour palette uses a consistent set of indigo/violet values. The primary accent is `#6366f1` (indigo-500). Search for this value in the CSS to update the theme globally.

---

## 📱 Mobile & Offline Use

The file is designed as a PWA-like offline tool without requiring service workers or a manifest. Simply save the `.html` file to your device:

- **Android** — Save to device storage, open with Firefox or via Acode
- **iOS** — Open in Safari → Share → Add to Home Screen
- **Desktop** — Bookmark the local file path in your browser

---

## 🤝 Contributing

Contributions are welcome! To add snippets or improve the tool:

1. Fork the repository
2. Add entries to the `codeDatabase` array in `index.html`
3. Test that search, filters, and both display modes work correctly
4. Open a pull request with a brief description of what was added

Please keep snippets practical, copy-paste ready, and beginner-friendly where possible.

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

*Save it. Open it. Code anywhere.*
