# Jatin Mehta — Portfolio

Live at **https://jatinmehta-1.github.io**

A static site. One page (`index.html`) plus 20 asset files. No build step, no
framework, no dependencies except the Chakra Petch webfont from Google Fonts.
Every change you commit to `main` is live in about 40 seconds.

---

## Editing

### Swap a photo or video — no code at all

Every asset is referenced by filename. Upload a new file with the **same name**
and the site picks it up. Nothing else to change.

| Replace this file | To change |
|---|---|
| `jatin.jpg` | The portrait in the header |
| `bts-1.mp4`, `bts-2.mp4` | The two behind-the-scenes clips |
| `clapper.jpg`, `neon.jpg`, `timeline.jpg`, `suite.jpg` | The four stills in the closing sequence (currently stock placeholders) |
| `yt-*.jpg` | A project thumbnail |
| `logo-*.png` | A client logo |

**How:** repo → `Add file` → `Upload files` → drag it in → `Commit changes`.

Keep videos under ~10 MB and images under ~600 KB so the page stays fast.

### Change wording or numbers

Open the repo and press the **`.`** key. That opens a full VS Code editor in the
browser — no install, no terminal. Edit `index.html`, then commit from the left
sidebar.

For a one-line fix: click `index.html` → pencil icon → edit → commit.

Things that live in plain text in there: the headline, the bio paragraphs, the
stat figures, project titles, view counts, phone number, email address.

### Bigger changes

Start a new Claude session and give it this repo URL. It is public, so Claude can
read the whole site and continue from there. Mention it is a static site,
`index.html` plus assets, deployed on GitHub Pages.

---

## Two things that will break the site

**1. Do not rename `index.html`.**
GitHub Pages serves that exact filename from the repo root. Rename it and the
site goes offline immediately.

**2. Do not delete the `<head>` block.**
Everything between `<head>` and `</head>` — especially this line:

```html
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
```

Without it, phones render the page at a virtual 981px and shrink the whole site
down. It looks fine on a laptop and unusable on a phone, which makes it easy to
miss. The `<head>` also holds the Open Graph tags that make the link unfurl with
a preview image on WhatsApp and LinkedIn.

---

## Structure

```
index.html   the entire site: markup, CSS and JS in one file
jatin.jpg    portrait
bts-*.mp4    behind-the-scenes clips (autoplay, muted, looping)
yt-*.jpg     project thumbnails, pulled from the YouTube Shorts
logo-*.png   client logos
ic-*.png     Instagram / YouTube / LinkedIn glyphs
```

Sections in order: title card, client logos, about, selected work,
closing sequence, contact.

## Custom domain

Buy a domain, then in repo `Settings → Pages → Custom domain` enter it, and at
your registrar point four A records at GitHub:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

Leave "Enforce HTTPS" ticked. No files need to change.
