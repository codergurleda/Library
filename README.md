# Our Library

A personal book catalog for our home — 400+ volumes across two bookcases, a living room shelf, a desk stack, and the coffee table.

**Live site →** `https://[your-username].github.io/library`

---

## What it is

A single-page searchable catalog of our home library. Every book has a title, author, genre, and exact shelf location so you can actually find it.

No backend. No login. No dependencies. One HTML file.

---

## How to use it

**Search** — type any part of a title or author name in the search box.

**Filter by genre** — Fiction, History, Science, Bengali Fiction, Textbook, and 20+ others.

**Filter by location** — narrow to a specific shelf. Locations are:

| Code | Where |
|------|-------|
| Living Room · Top | On top of the living room unit |
| Living Room · Middle | Middle shelf, living room |
| Living Room · Lower | Bottom shelf, living room |
| Study A · Shelf 1–5 | Left bookcase in study (1 = bottom, 5 = top) |
| Study B · Shelf 1–5 | Right bookcase in study (1 = bottom, 5 = top) |
| Study · Stack | Horizontal pile on the desk |
| Coffee Table | Large format books on the coffee table |

**Sort** — click any column header to sort. Click again to reverse.

A small amber dot next to a title means the shelf location is approximate — the spine wasn't fully legible in the catalog photos.

---

## How it was built

We photographed every shelf — 25 photos across multiple sessions — and used Claude to identify titles, cross-reference shelf positions, correct capitalizations, remove duplicates, and resolve ambiguous spines. The Bengali shelf required close-up photos and manual title confirmation. Total time: a few hours across two afternoons.

---

## To update the catalog

Open `index.html` and find the `RAW` array (around line 200). Each entry is:

```js
["Title", "Author", "Genre", "LocationCode", confirmed]
```

`confirmed` is `true` if the spine was clearly read, `false` if approximate.

Add a new book:
```js
["The Remains of the Day", "Kazuo Ishiguro", "Fiction", "LR – Low", true],
```

Location codes: `LR – Top`, `LR – Mid`, `LR – Low`, `A1`–`A5`, `B1`–`B5`, `STK`, `CT`

---

## Deploying to GitHub Pages

1. Push `index.html` to the `main` branch of this repository
2. Go to **Settings → Pages**
3. Source: **Deploy from a branch** → `main` → `/ (root)` → Save
4. Site goes live at `https://[your-username].github.io/[repo-name]`

---

*Cataloged with Claude · Tribeca, NYC*
