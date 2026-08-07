# photos

Image host for [jaredlincenberg.github.io](https://jaredlincenberg.github.io). Not a site of its own — just storage, served over GitHub Pages so photos can be linked into posts and pages without living in the main site repo or on any local machine.

## Adding a photo

1. On github.com (works fine from a phone browser), open this repo and use **Add file → Upload files**.
2. Drop the image into the `images/` folder. Keep the filename lowercase-with-dashes (e.g. `2026-08-trailhead.jpg`) so URLs stay predictable.
3. Commit directly to `main` — GitHub Pages rebuilds automatically.

## Linking to a photo

Once uploaded, the live URL is:

```
https://jaredlincenberg.github.io/photos/images/<filename>
```

Use that URL in the main site (e.g. `![alt text](https://jaredlincenberg.github.io/photos/images/2026-08-trailhead.jpg)`). Don't link via `raw.githubusercontent.com` — GitHub rate-limits that domain; the `github.io` Pages URL isn't subject to the same limit.

## Why a separate repo

Keeps the [jaredlincenberg.github.io](https://github.com/JaredLincenberg/jaredlincenberg.github.io) repo (and any local clones of it) free of hundreds of image files, while still keeping everything inside GitHub — no third-party hosting account needed.
