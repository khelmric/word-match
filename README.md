# WordMatch

## Project Overview

WordMatch is a multilingual, browser-based word matching game designed to challenge players to find pairs of words under configurable constraints. The game supports multiple languages and symbol sets, providing an engaging and educational experience. It features a clean, responsive UI with customizable settings such as syllable limits, included/excluded characters, and countdown timers.

---

## Game website

The game is available on the following website: [https://wm.app.helmrich.hu/](https://wm.app.helmrich.hu/)

## Architecture

WordMatch is implemented as a static web application, primarily using HTML, CSS, and JavaScript. The core logic and UI are contained within a single HTML file (`index.html`), complemented by styling in `static/style.css` and language/word data in text files under `static/txt/`.

### Key Components

- **User Interface (UI):**  
  Defined in `index.html`, the UI includes the game board, controls, settings popup, and language selection menu. It dynamically updates based on game state and user interactions.

- **Game Logic:**  
  Embedded in the script section of `index.html`, the JavaScript code manages game state, word pair generation, timing, and user input handling.

- **Localization:**  
  Language data and UI text are managed via JavaScript objects within `index.html` and word lists stored in `static/txt/` for Hungarian (`list-hu.txt`), English (`list-en.txt`), German (`list-de.txt`), and symbol/nature sets.

- **Assets:**  
  Static images such as flags, favicon, and title graphics are located in `static/img/`.

- **Styles:**  
  The visual styling is defined in `static/style.css`, providing responsive design and animations.

---

## Folder Structure

```
/
├── index.html               # Main HTML file with embedded JS and UI
├── LICENSE                 # Apache License 2.0
├── .gitignore              # Git ignore rules
├── .github/
│   └── workflows/
│       └── static.yml      # GitHub Actions workflow for deployment
└── static/
    ├── style.css           # CSS styles for the game
    ├── img/                # Image assets (flags, favicon, title)
    └── txt/                # Word lists and symbol sets
        ├── list-hu.txt     # Hungarian word list
        ├── list-en.txt     # English word list
        ├── list-de.txt     # German word list
        ├── list-symbols.txt# Symbol characters list
        └── list-nature.txt # Nature emoji list
```

---

## Setup & Installation

WordMatch is a static web application requiring no backend or build process.

1. **Clone the repository:**
   ```bash
   git clone https://github.com/khelmric/word-match.git
   cd word-match
   ```

2. **Serve the files:**
   - Open `index.html` directly in a modern web browser (Chrome, Firefox, Edge).
   - Or serve via a local HTTP server for full functionality (recommended):
     ```bash
     # Using Python 3
     python3 -m http.server 8000
     ```
     Then open `http://localhost:8000` in your browser.

3. **Optional:**  
   The project includes a GitHub Actions workflow (`.github/workflows/static.yml`) for automatic deployment to GitHub Pages on pushes to the `main` branch.

---

## Usage Instructions

- **Starting the Game:**  
  Click the green **Start** button to begin a new game.

- **Stopping the Game:**  
  Click the red **Stop** button to end the current game session.

- **Settings:**  
  Click the 🛠 (Settings) icon in the top-left menu to open the settings popup. Configure:
  - Maximum syllables per word (1 to 5+).
  - Required letters to include in words.
  - Letters to exclude from words.
  - Countdown timer duration (5 to 99 seconds).

- **Language Selection:**  
  Use the flag icon dropdown in the top-left menu to switch between supported languages:
  - Hungarian (Magyar)
  - English
  - German (Deutsch)
  - Symbols
  - Nature emojis

- **Sharing:**  
  Click the clipboard icon 📋 to copy the current game URL to the clipboard for sharing.

- **Game Play:**  
  Match pairs of words/cards displayed on the screen before the timer runs out. Progress through levels as you succeed.

---

## Configuration

All game settings are configurable via the settings popup UI. The game state and settings are managed in JavaScript within `index.html`. No external configuration files are required.

Settings include:

- `syllables`: Maximum number of syllables allowed in words.
- `includeChar1`, `includeChar2`, `includeChar3`: Required characters that must appear in words.
- `excludeCharsContainer`: Letters to exclude from word selection.
- `counter`: Countdown timer duration in seconds.

---

## Development Notes

- The entire game logic and UI are contained in `index.html` for simplicity.
- Word lists are plain text files in `static/txt/` and can be updated or extended.
- Language support is managed via the `i18n` object in the embedded script.
- Styling is responsive and uses CSS animations for UI feedback.
- The project uses modern JavaScript features and requires a modern browser.

---

## Warnings & Assumptions

- The game assumes a modern web browser with support for ES6 JavaScript and Clipboard API.
- Word lists are assumed to be UTF-8 encoded plain text files with one word per line.
- The game runs entirely client-side; no server or database is involved.
- The settings UI and language menu rely on JavaScript event handling; disabling JS will break functionality.
- The game does not currently support persistence; refreshing the page resets the game.

---

Thank you for exploring WordMatch! For questions or contributions, please refer to the repository issues or contact the maintainer.