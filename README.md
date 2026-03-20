# 💻 Offline Coding Assistant

A self-contained, single-file web development reference that works **completely offline**. Open it in any browser — no server, no internet, no dependencies required.

Built for developers and beginners who want instant access to HTML, CSS, and JavaScript snippets, especially useful in mobile coding environments like **Termux** and **Acode**.

---

## ✨ Features

- **100% Offline** — a single `.html` file with zero external dependencies
- **Animated Splash Screen** — polished intro animation on load
- **Searchable Snippet Library** — instantly filter by keyword across all snippets
- **Language & Category Filters** — narrow results by HTML, CSS, JavaScript, or domain
- **Beginner Mode** — toggle plain-English explanations alongside every snippet
- **One-Click Copy** — copy any code snippet to the clipboard with visual feedback
- **Termux & Acode Guide** — collapsible built-in setup guide for mobile coding
- **Quick Tips Panel** — contextual tips shown when no filters are active
- **Responsive Design** — works on desktop and mobile screens

---

## 📸 Preview

> Open `online_viewer_net.html` directly in your browser — no build step needed.

The app opens with a branded splash screen, then loads the full snippet library. The dark indigo/violet theme is designed for comfortable extended use.

---

## 🚀 Getting Started

### Option 1 — Direct Use
1. Download or clone this repository
2. Open `online_viewer_net.html` in any modern browser
3. Start searching and copying snippets

### Option 2 — GitHub Pages
1. Fork this repository
2. Go to **Settings → Pages**
3. Set the source to your main branch
4. The file will be live at `https://github.com/Ahmed-Hassan-811/online-viwer-net/blob/main/index.html`

### Option 3 — Termux & Acode (Android)
1. Copy `online_viewer_net.html` to your device storage
2. Open the file in **Acode** or any browser (e.g. Firefox, Chrome)
3. Bookmark it for offline use — works with no data connection

---

## 📚 Snippet Library

The built-in library covers foundational web development across three languages:

| Language   | Example Topics Covered |
|------------|------------------------|
| **HTML**   | Document structure, headings, paragraphs, links, images, lists, tables, forms, semantic elements, audio/video, div & span |
| **CSS**    | Colors & backgrounds, gradients, typography, box model, flexbox, grid, animations, transitions, responsive/media queries, variables |
| **JavaScript** | Variables, functions, DOM manipulation, events, loops, arrays, objects, fetch/API calls, localStorage, form validation |

Each snippet includes:
- A **code example** ready to copy and paste
- A **Technical Description** for experienced developers
- A **Simple Explanation** (in Beginner Mode) using everyday analogies

---

## 🧭 How to Use

### Search
Type into the search bar to filter snippets in real time. Try terms like:
- `button`, `form`, `color`, `click`, `flex`, `loop`, `fetch`.

### Filters
Click **Show Filters** to reveal dropdowns for:
- **Language** — HTML, CSS, JavaScript
- **Domain/Category** — Structure, Forms, Events, Layout, etc.

### Beginner Mode
Click **Beginner Mode ON/OFF** to toggle plain-English explanations under each snippet. Great for learners who want to understand *why* code works, not just *what* it does.

### Copy Code
Click the clipboard icon on any snippet card to copy the code. The icon turns green to confirm the copy was successful.

---

## 🏗️ Project Structure

This is intentionally a single-file project.

```
online_viewer_net.html
│
├── <style>          — All CSS, including splash screen, layout, cards, animations
├── <body>
│   ├── Splash screen overlay (fades out after ~2.4s)
│   ├── Header with live snippet stats
│   ├── Termux/Acode collapsible guide
│   ├── Search bar + filter controls
│   ├── Quick tips panel
│   └── Snippet grid (rendered dynamically)
└── <script>
    ├── codeDatabase[]   — All snippet data
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

The splash automatically fades out after **~2.4 seconds** and is removed from the DOM entirely.

---

## 🛠️ Customisation

### Adding Snippets
All snippets live in the `codeDatabase` array inside the `<script>` tag. Each entry follows this shape:

```JavaScript
{
    language: "HTML",            // "HTML" | "CSS" | "JavaScript"
    domain: "Forms",             // Category label shown in the filter dropdown
    task: "Basic Form",          // Snippet card title
    code_example: `<form>...</form>`,
    description: "Technical description for experienced developers.",
    simple_explanation: "Plain-English explanation for beginners."
}
```

### Changing the Theme
The colour palette uses a consistent set of indigo/violet values. The primary accent is `#6366f1` (indigo-500). Search for this value in the CSS to update the theme globally.

---

## 📱 Mobile & Offline Use

The file is designed as a **PWA-like offline tool** without requiring service workers or a manifest. Simply save the `.html` file to your device:

- **Android** — Save to device storage, open with Firefox or via Acode
- **iOS** — Open in Safari → Share → Add to Home Screen
- **Desktop** — Bookmark the local file path in your browser

---

## 🤝 Contributing

Contributions are welcome! To add snippets or improve the tool:

1. Fork the repository
2. Add entries to the `codeDatabase` array in `online_viewer_net.html.`
3. Test that search, filters, and both display modes work correctly
4. Open a pull request with a brief description of what was added

Please keep snippets practical, copy-paste ready, and beginner-friendly where possible.

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

*Save it. Open it. Code anywhere.*
