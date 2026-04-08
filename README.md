# GrayKrow Monolith

A Vue 3 + Vite + SCSS single-page site for **GrayKrow**.

This starter is built as a monolithic page with four core sections:

- Hero
- About
- Projects
- Contact

It is intentionally structured to be easy to reshape as the identity sharpens.

## Stack

- Vue 3
- Vite
- SCSS via `sass-embedded`

## Run locally

```bash
npm install
npm run dev
```

## Build

```bash
npm run build
```

## Main places to edit

### Content
- `src/data/inProfileData.js`
- `src/data/inProjectsData.js`

### Layout + section logic
- `src/App.vue`
- `src/components/`

### Theme styling
- `src/assets/styles/_tokens.scss`
- `src/assets/styles/_base.scss`
- component-level scoped SCSS

## Background image

The site background lives here:

- `public/assets/images/graykrowForest.png`

## Notes

- No `package-lock.json` included
- No `dist` folder included
- Links and contact handles are left intentionally easy to swap
