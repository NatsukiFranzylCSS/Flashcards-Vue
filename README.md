# Agentic Vue Flashcards

A lightweight, clean desktop flashcard application built with Vue 3, Vite, and Tauri. 

## Features
- **JSON Powered**: Empty by default. Just upload a `.json` file containing an array of `{ term: "", definition: "" }` objects to instantly load your deck. Perfect for having AI generate study materials for you.
- **Phased Reviewing**: Cards you mark as "Not Memorized" are kept in a bucket. Once you clear the current deck, the app automatically shuffles your missed cards and starts the next phase until you've mastered them all.
- **Searchable Dictionary**: Click "View All Cards" to open a 3-column, responsive grid showing every card in the deck, complete with a real-time search bar.
- **End-of-Session Analytics**: When you finish a deck, the app displays a grid of any terms you struggled with (missed 2 or more times) so you know exactly what to focus on.

## Json Formatting 

```json
[
  {
    "id": 1,
    "term": "",
    "definition": ""
  }
]
```

## Prerequisites

- [Node.js](https://nodejs.org/) and npm
- [Rust](https://www.rust-lang.org/tools/install) (stable)
- Platform-specific Tauri dependencies: see the [Tauri prerequisites guide](https://v2.tauri.app/start/prerequisites/)

## Development Setup

To run the desktop app in development mode (with hot-reloading):

```bash
npm install
npm run tauri:dev
```

To run just the web frontend in a browser: `npm run dev`.

## Building the Desktop App

This project uses [Tauri v2](https://v2.tauri.app/) to package the web code into small, native desktop apps. Output is placed in `src-tauri/target/release/bundle/`.

Tauri does not cross-compile, so build on the OS you are targeting:

- **macOS** (`.app`, `.dmg`)
- **Windows** (`.msi`, `.exe`)
- **Linux** (`.deb`, `.rpm`, `.AppImage`)

```bash
npm run build
```

To build a specific bundle: `npm run build -- --bundles app` (or `dmg`, `msi`, `nsis`, `deb`, `appimage`, ...).
