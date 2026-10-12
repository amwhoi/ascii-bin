<h1 align="center"><strong>ascii-bin</strong></h1>

<p align="center">
  <img src="https://raw.githubusercontent.com/amwhoi/ascii-bin/main/assets/preview1.png" alt="ASCII art index: searchable gallery of 272 arts with live thumbnails and tag filters" width="49%">
  <img src="https://raw.githubusercontent.com/amwhoi/ascii-bin/main/assets/preview2.png" alt="ASCII art editor: pools, particle density and the frame pipeline beside the editing canvas" width="49%">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/build%20step-none-success" alt="No build step">
  <img src="https://img.shields.io/badge/works-offline-informational" alt="Works offline">
  <img src="https://img.shields.io/badge/vanilla-JS-yellow" alt="Vanilla JavaScript">
  <img src="https://img.shields.io/badge/tools-MIT-blue" alt="Tools licensed MIT">
  <img src="https://img.shields.io/badge/art-CC0%20public%20domain-lightgrey" alt="Art dedicated to the public domain under CC0">
</p>

ASCII Art Database with more than 300 ready-to-paste arts in plain text & browser tools to search and decorate them

## Quick start

Double-click `index.html` to browse the collection, or `builder.html` to decorate an art. Both are self-contained pages, nothing to install.

Opened straight from `file://`, the browser blocks a page from reading files next to it, so the index starts on its drop screen. Drag `asciiart_db.txt` onto it, or use **Choose a file**. To skip that step and save edits straight back into the file, serve the folder over HTTP instead:

```bash
python -m http.server 8765
```

Then open <http://localhost:8765/> and the database loads by itself.

## Features

### `index.html`: the ASCII art library

- **Instant search** across tags and descriptions; `#tag` searches tags only
- **Tag chips** with counts, click to filter
- **Full-art thumbnails**: every row drawn, scaled to fit, measured per glyph so braille and box-drawing art never gets clipped
- **Viewer** with font-size controls and an Enter flow (tags, then description, then next art) for fast bulk tagging
- **Copy any art** to the clipboard in one click
- **Sort** by file order, largest or smallest; **Random** button to rediscover your own collection
- **Light/dark theme**, remembered between visits
- **Export** the updated `.txt` with tags and descriptions written back in, original line endings preserved
- Edits survive a reload (`localStorage`); the file always wins on re-import, so nothing silently overwrites your data

### `builder.html`: the ASCII art editor & paste builder

- **Particles**: sprinkle `*`, `.`, `` ` `` or any charset into blank cells only; never overwrites art, never adds rows. Adjustable density, regenerate until it looks right.
- **Side frames**: wrap the block in `│ ║ ┃ ▌` or any character.
- **Top/bottom frames**: title bars and footers that auto-stretch to the block's width.
- **Overlay art**: load a second file of small stamps, then **drag** one over the canvas and merge it in. Spaces can be transparent, or "under" mode fills blanks only.
- **Move (shift)**: slide the whole block sideways, identical on every line, clamped so it never clips at the left edge.
- **Space cleaning**: right-trim every line; tab expansion with a configurable tab width.
- **Paste builder**: load a library, reorder blocks by drag handle, set blank lines between them, and copy or save the combined paste.

## File format

One plain-text format for everything: the database, the block library and the pools. Entries are separated by a line containing exactly `===EOF===`:


```
      /\
     /  \      <- the art, any characters, any width
    /____\

tags: house, building
description: a small house
===EOF===
```

- `tags:` and `description:` are optional trailing lines; leave them empty and fill them in from the index UI.
- Pool files use a `type:` line instead: `opening | text | art | ending` for libraries, `top`/`bottom` for frames.

## Contributing

Issues and pull requests are welcome, especially for new ascii arts. Adding one is a two-line change: append your art to `asciiart_db.txt` followed by a `===EOF===` line, in the format shown above. Tags and descriptions are optional and can be filled in later from the index UI.

By contributing art you agree to release it into the public domain under CC0, the same terms as the rest of the collection.

## License

Two licenses, because the repo holds two different kinds of thing:

- **The art** (`asciiart_db.txt` and everything in `pools/`) is public domain under [CC0 1.0](LICENSE-DATA). Copy it, change it, sell it, no permission or attribution needed.
- **The tools** (`index.html` and `builder.html`) are [MIT](LICENSE). Same freedoms, but keep the copyright notice.

The art is a collected set, so some pieces were authored by other people and are reproduced as found. The dedication covers the compilation and whatever rights the maintainer holds; it cannot waive anyone else's. If a piece is yours and you want it removed or credited, open an issue.
