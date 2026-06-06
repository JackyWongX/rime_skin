# Rime Skin Designer Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a pure HTML single-file Rime Weasel skin designer with paste/import, color editing, live preview, copy, and download.

**Architecture:** Create one `index.html` containing the markup, CSS, and JavaScript. The app uses lightweight line-based parsing for `_color` fields and writes changes back into the original YAML text without requiring a server or build tool.

**Tech Stack:** HTML, CSS, vanilla JavaScript, browser FileReader, Blob download, Clipboard API fallback.

---

### Task 1: Single-File App Shell

**Files:**
- Create: `index.html`

- [ ] Create the HTML document with UTF-8 metadata, a three-column workbench, and responsive layout.
- [ ] Add left YAML editor controls: import file, parse, load example, and textarea.
- [ ] Add middle color editor container and add-color controls.
- [ ] Add right preview panel with copy and download controls.

### Task 2: YAML Color Parsing And Conversion

**Files:**
- Modify: `index.html`

- [ ] Add a default `weasel.custom.yaml` example.
- [ ] Implement color parsing for `0xRRGGBB`, `#RRGGBB`, `rgb(r, g, b)`, and `r,g,b`.
- [ ] Implement conversion helpers for HEX, RGB string, and Weasel `0xRRGGBB`.
- [ ] Implement line scanning for `key: value` entries where key ends with `_color`.

### Task 3: Color Controls And YAML Writeback

**Files:**
- Modify: `index.html`

- [ ] Render one color row per parsed field.
- [ ] Sync color picker, HEX input, RGB input, YAML text, and live preview on valid input.
- [ ] Mark invalid field input without mutating YAML.
- [ ] Support custom `_color` fields found in pasted YAML.
- [ ] Support adding a new color field by appending to the detected color scheme block or to the end of the YAML.

### Task 4: Import, Copy, Download, And Manual Verification

**Files:**
- Modify: `index.html`

- [ ] Implement file import for `.yaml`, `.yml`, and `.txt`.
- [ ] Implement copy YAML with Clipboard API and textarea fallback.
- [ ] Implement download as `weasel.custom.yaml`.
- [ ] Manually inspect the file and confirm key functions exist.
- [ ] Do not create or run test code files.
