# Submitting this mod to the Zen Mods store

Zen's store is **issue-based**: you open a GitHub issue from a template and a bot generates
the store files and opens the PR for you. Your repo just needs to host the screenshot.

## 1. Push this repo to GitHub first

```bash
# from this folder
git remote add origin https://github.com/movsq/zen-back-fwd-hidden-ext.git
git branch -M main
git push -u origin main
```

This makes the image available at:
`https://raw.githubusercontent.com/movsq/zen-back-fwd-hidden-ext/main/image.png`

## 2. Open the submission issue

Go to: https://github.com/zen-browser/theme-store/issues/new?template=create-theme.yml

Title: `[create-theme]: Back Fwd Hidden (ext)`

Fill the fields with these exact values:

| Field | Value |
|---|---|
| **name** | `Back Fwd Hidden (ext)` |
| **description** | `Hides back/forward buttons while keeping extension buttons right-aligned.` |
| **image** | `https://raw.githubusercontent.com/movsq/zen-back-fwd-hidden-ext/main/image.png` |
| **is-color-theme** | leave unchecked (this is a CSS mod, not a color theme) |
| **styles** | paste the full contents of `chrome.css` (see below) |
| **readme** | paste the contents of `readme.md` (or a short version) |
| **homepage** | `https://github.com/movsq/zen-back-fwd-hidden-ext` |
| **preferences** | leave empty (this mod has none) |

### styles (paste verbatim)

```css
:root:not([customizing]) #back-button,
:root:not([customizing]) #forward-button {
  display: none !important;
}
:root:not([customizing]) #zen-sidebar-top-buttons-separator {
  flex: 1 1 auto !important;
}
```

## 3. Submit

Submit the issue. The bot validates it (name ≤ 25 chars ✓, description ≤ 100 chars ✓,
image is PNG ✓), creates `themes/<uuid>/` files, and opens a PR. Once a maintainer merges
it, it appears at https://zen-browser.app/mods/.

> Note: `theme.json` and `bfah-mod.json` in this repo are for reference / manual import —
> the store bot generates its own `theme.json`, so you don't submit those.
