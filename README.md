<h1 align="center"><strong>ascii-bin</strong></h1>

<p align="center">
  <img src="https://raw.githubusercontent.com/amwhoi/ascii-bin/main/assets/preview1.png" alt="ASCII art index: searchable gallery of 272 arts with live thumbnails and tag filters" width="49%">
  <img src="https://raw.githubusercontent.com/amwhoi/ascii-bin/main/assets/preview2.png" alt="ASCII Paste Builder: tools, the paste editor and the block palette, in the Mono theme" width="49%">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/build%20step-none-success" alt="No build step">
  <img src="https://img.shields.io/badge/works-offline-informational" alt="Works offline">
  <img src="https://img.shields.io/badge/vanilla-JS-yellow" alt="Vanilla JavaScript">
  <img src="https://img.shields.io/badge/tools-MIT-blue" alt="Tools licensed MIT">
  <img src="https://img.shields.io/badge/art-CC0%20public%20domain-lightgrey" alt="Art dedicated to the public domain under CC0">
</p>

<p align="center">
  <a href="SHORTCUTS.md"> Shortcuts</a>
</p>

ASCII Art Database with more than 300 ready-to-paste arts in plain text & browser tools to search and decorate them

## Quick start

You can use tools via githuhb pages:

https://amwhoi.github.io/ascii-bin

https://amwhoi.github.io/ascii-bin/builder.html


Otherwise you can clone repo and double click index.html or builder.html, both self contained

Opened straight from `file://`, the browser blocks a page from reading files next to it, so the index starts on its drop screen.To skip that step and save edits straight back into the file, serve the folder over HTTP instead:

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

Two tabs: **ASCII Paste Builder** assembles and decorates a paste, **Images converter** turns pictures into ASCII.

#### ASCII Paste Builder

- **Three panels**: Tools on the left, the whole paste in the middle, Blocks (Palette + Order) on the right. Either side panel can be hidden.
- **Palette**: blocks from `pools.txt`, arts from `asciiart_db.txt` and your converted images. **Browse…** picks what it shows; tabs filter by type (opening, text, art, ending). **Add ▸** appends a block, or drag a card onto Order or straight onto the editor.
- **Order**: drag to reorder, ▲ ▼ ✕ per block. Double-click a block to make it the **target**: it glows, the rest dims, and the tools work on it alone. Double-click again for the whole paste.
- **Editing**: type straight into the paste. Undo, Reset, Right-trim, adjustable blank lines between blocks, zoom. **Split here** (Ctrl + Enter) cuts a block in two; **Paste as blocks…** splits pasted text into blocks by blank lines, `===EOF===` or a marker, and guesses each block's type.
- **Draw tools**: Select (rectangle or lasso), Box and Line (styles from the border kits; lines join existing ones as `├ ┬ ┼`), Erase, and a Brush 1, 3 or 5 cells wide.
- **Selections**: arrows move them, Shift + arrows tile copies next to them, Ctrl + V floats a copy to drag. The selection bar adds a frame, split lines, a header, fill, particles (variant + density), clear, paint and uncolor.
- **Colour**: paint with one colour or a random **combo** (built in, from `pools.txt`, or your own), at any density. Colours stay on their characters through edits, moves and undo.
- **Overlay art**: floating art is placed with Enter, in one of five modes: see-through, solid, under (fills blanks only), clear box, or box + spaces.
- **Tables**: border kits with every frame piece editable, **Frame target** and **Header above target**, and a **table editor** with a form view and two syntax views. Drag the grid's edges to add columns, rows or sections. Templates: Table, Frame, Frame with particles.
- **Export**: Copy and Save as plain text, Copy HTML and Save HTML… with colours (whole `<pre>` or a bare fragment, merged runs or one span per character), and Save PNG….

#### Images converter

- **Layers**: load, drop or paste any number of images. In the Layers window, move, resize and rotate them and set blend, opacity and visibility.
- **Adjustments**: brightness, contrast, saturation, midtones, highlights and hue, plus sharpen, blur and denoise in the order you drag them into.
- **Characters**: dozens of styles: classic ASCII ramps, letters and digits, blocks and bars, braille, dots and shapes, Greek, Cyrillic, Hebrew, Arabic, Chinese and Japanese. Or type your own characters. Sized by width or by cell size, rendered by brightness or **shape matching**, with optional edge characters.
- **Tone**: gamma, posterize, vignette, cut-out, invert and dithering (Floyd–Steinberg, Jarvis–Judice–Ninke, Stucki, Atkinson).
- **Color**: grey, the picture's own colours, gradient maps, palettes (built in, favourites, imported, or taken from the picture), a single ink colour, and any background colour, including transparent.
- **Effects**: **neo** draws glowing comet trails along the characters, with ▶ Play to animate them.
- **Presets**: save, load and import complete setups.
- **Compare line**: drag it across the result to see the original picture underneath.
- **Output**: Copy, Save, Copy HTML, Save HTML…, Save PNG…, or **Send to palette ▸** to use the result as a block in the builder.

Every keyboard shortcut and mouse move of the builder and its images converter is listed in [SHORTCUTS.md](SHORTCUTS.md).

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
- `pools.txt` holds every pool in one file, split into sections by `[[pool: NAME]]` lines (`blocks`, `particles`, `sideframes`, `kits`, `templates`, `combos`). Its entries use a `type:` line instead of tags: `opening | text | art | ending` for blocks, the name for kits, templates and combos.

## Contributing

Issues and pull requests are welcome, especially for new ascii arts. Adding one is a two-line change: append your art to `asciiart_db.txt` followed by a `===EOF===` line, in the format shown above. Tags and descriptions are optional and can be filled in later from the index UI.

By contributing art you agree to release it into the public domain under CC0, the same terms as the rest of the collection.

## License

Two licenses, because the repo holds two different kinds of thing:

- **The art** (`asciiart_db.txt` and `pools.txt`) is public domain under [CC0 1.0](LICENSE-DATA). Copy it, change it, sell it, no permission or attribution needed.
- **The tools** (`index.html` and `builder.html`) are [MIT](LICENSE). Same freedoms, but keep the copyright notice.

The art is a collected set, so some pieces were authored by other people and are reproduced as found. The dedication covers the compilation and whatever rights the maintainer holds; it cannot waive anyone else's. If a piece is yours and you want it removed or credited, open an issue.
