# Shortcuts

Every keyboard shortcut and mouse move in `builder.html`: the **ASCII Paste Builder** tab and the **Images converter** tab.
On a Mac, use ⌘ where it says Ctrl. Ctrl + Z and Ctrl + V go by key position, so they also work with Cyrillic and other keyboard layouts.

## ASCII Paste Builder

### Typing in the editor (✍ Text tool)

| Keys | What it does |
|---|---|
| Ctrl + Enter | **Split here**: the line with the cursor and the lines below it become a new block of the same type |
| Ctrl + Z | **Undo**, including everything the tools did. Other input fields keep their own undo |
| Alt + ← → ↑ ↓ | Move the target block 1 column or line while the cursor is in the editor (plain arrows move the cursor) |
| Alt + Shift + ← → ↑ ↓ | The same, 4 columns or lines at a time |

### Moving a block (nothing selected)

| Keys | What it does |
|---|---|
| ← → ↑ ↓ | Move the target block 1 column or line (when the cursor isn't in a text field) |
| Shift + ← → ↑ ↓ | 4 columns or lines at a time |

The **target block** is the one you double-clicked in Order; it glows and the rest dims. With no target, the whole paste moves.

### Draw tools (the Draw bar)

| Tool | Mouse |
|---|---|
| ⬚ Select | Drag a rectangle |
| ◌ Lasso | Draw around any shape |
| ▭ Box | Drag to draw a box; it joins existing lines. Clicking the button also opens the box style pop-up (╔═╗, ┌─┐, …) |
| ┼ Line | Drag a straight line; it snaps to horizontal or vertical and joins existing lines (├ ┬ ┼). Clicking the button also opens the line style pop-up |
| ⌫ Erase | Drag to blank a rectangle, or a lasso shape when Select is set to ◌ (the Select button glows to show which) |
| 🖌 Brush | Drag to paint characters with the current colour or combo (Tools → Color). Clicking the button also opens the size pop-up: · 1, ▪ 3, ■ 5 wide |

| Keys / mouse | What it does |
|---|---|
| Esc | Back to ✍ Text (when nothing is selected) |
| Mouse wheel | Scroll the paste while a tool is on; scrolling past the end adds empty room to draw in |
| Shift + mouse wheel | Scroll sideways |

The style and size pop-ups close by themselves after 3 seconds; keep the pointer on them to keep them open.

### With a selection

| Keys | What it does |
|---|---|
| ← → ↑ ↓ | Move the selected characters, with their colours, 1 cell |
| Shift + ← → ↑ ↓ | Put a **copy** right next to the selection in that direction, merged the Tools → Overlay way. Press again to keep tiling. At the left or top edge the copy is cut off there |
| Ctrl + V | Float a copy of the selection right where it is (see Floating art). A lasso copies only its shape |
| Delete / Backspace | Blank the selection |
| Esc | Drop the selection |

If the cursor is in a text field, hold Alt with these keys. The selection bar also has buttons for Frame, Split ┃ ━, Header, Fill, Particles, Clear, Paint, Uncolor and Copy.

### Floating art (overlay)

Floating art comes from dragging a palette card onto the editor, from Ctrl + V on a selection, or from **Overlay ▸** in the table editor.

| Keys / mouse | What it does |
|---|---|
| Drag the art | Move it |
| ← → ↑ ↓ | Move it 1 cell |
| Shift + ← → ↑ ↓ | Move it 4 cells |
| Enter | **Place** it, the Tools → Overlay way (See-through, Solid, Under, Clear box, Box + spaces) |
| Esc or Ctrl + Z | Cancel it |

### Palette and Order (right panel)

| Mouse | What it does |
|---|---|
| Drag a palette card onto the editor | It floats there: move it, then Enter |
| Drag a palette card onto Order | Insert that block at the drop spot |
| Add ▸ on a card | Add the block at the end |
| Click an Order item | Scroll to that block |
| Double-click an Order item | Make it the target block; double-click it again to work on the whole paste |
| Drag an Order item | Reorder the blocks (▲ ▼ move one step, ✕ removes, ▦ edits its table) |

### View

| Keys / mouse | What it does |
|---|---|
| Ctrl + mouse wheel over the editor | Zoom, keeping the spot under the pointer in place |
| Click the % label | Zoom back to 100% |
| ◧ Tools / Blocks ◨ | Show or hide the side panels |
| Click a section header | Fold or unfold that section |
| Esc | Close any dialog (table editor, Browse, Paste as blocks, HTML options, …) |

### Table editor (▦ Table…)

| Mouse | What it does |
|---|---|
| Drag the grid's right edge | Add or remove columns |
| Drag the grid's bottom edge | Add or remove rows (sections, in the Frame with particles template) |
| Drag the grid's corner | Columns and rows together |

Changes apply when you let go; if cells with text would be removed, it asks first. **Overlay ▸** floats the table into the editor.

## Images converter

### Getting a picture in

| Keys / mouse | What it does |
|---|---|
| Load image… | Pick an image file |
| Drop image files on the converter | Each one becomes a layer. Files dropped on the other tab are refused, so the page isn't replaced |
| Ctrl + V | Paste an image from the clipboard as a new layer |

### Result area

| Keys / mouse | What it does |
|---|---|
| Ctrl + mouse wheel | Zoom the result (2 to 28 px) |
| Click the px label | Back to 8 px |
| Drag the compare line | Show the original picture over the characters, on the left of the line |
| Double-click the compare line | Back to all characters |

### Layers window (▤ Layers…)

| Mouse | What it does |
|---|---|
| Click the picture | Select the topmost layer under the pointer |
| Drag | Move the selected layer |
| Mouse wheel | Resize the selected layer (5% to 400%) |

### Settings

| Keys / mouse | What it does |
|---|---|
| Adjustments → drag ⠿ on an effect card | Change the order sharpen, blur and denoise are applied in |
| Adjustments → focus ⠿ (Tab), then ↑ / ↓ | The same with the keyboard |
| Effects → neo ▶ Play | Animate the trails; Stop, turning neo off or leaving the tab stops them |
| ← → on a focused slider | Nudge it one step (as in any browser) |
| Esc | Close the open dialog (Layers window, HTML export options) |
