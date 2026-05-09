# haditheque-com

Static build of [Haditheque](https://github.com/) deployed to GitHub Pages at
<https://USERNAME.github.io/haditheque-com/>.

## What's in here

This repository **only** contains the built static assets produced by Vite from
the `Haditheque-web2` source repository — there is no source code here. Every
file (HTML, JS, CSS, images, the `corpus/Corpus.zip` data archive, fonts, etc.)
is checked in directly so that GitHub Pages can serve it as-is, with no build
step on GitHub's side.

## Hosting setup

1. Repository settings → **Pages** → *Source: Deploy from a branch*, branch:
   `main`, folder: `/ (root)`.
2. The presence of `.nojekyll` disables Jekyll's filtering (so files / paths
   starting with `_` are served).
3. `404.html` is a copy of `index.html`. GitHub Pages serves it for any
   unknown path, which lets the React SPA take over and render the requested
   route (e.g. `/haditheque-com/SB1` deep-links work on first load).

## Updating the site

From the source repository:

```bash
# In Haditheque-web2:
npm run build
# Then copy the contents of dist/ into this repo (overwrite), recreate 404.html
# from index.html, and commit + push.
```

The build is configured with `base: '/haditheque-com/'` so all asset URLs are
prefixed correctly for the project-site URL scheme.
