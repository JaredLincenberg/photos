# photos

Image host for [jaredlincenberg.github.io](https://jaredlincenberg.github.io). Not a site of its own — just storage, served over GitHub Pages so photos can be linked into posts and pages without living in the main site repo or on any local machine.

## Layout

Photos are filed one folder per county, using the county the photo was taken in:

```
<county-slug>/YYYY-MM-DD-location-description.jpeg
```

- `county-slug` — the county, lowercased and hyphenated (e.g. `denver-county`, `jefferson-county`). Current folders: `adams-county`, `arapahoe-county`, `broomfield-county`, `denver-county`, `jefferson-county`.
- `location` — short recognizable place name, e.g. `bar-lake`, `washington-park`.
- `description` — short common name of the subject, e.g. `bee`, `dragonfly`, `bumble-bee`.

## Adding a photo

New uploads land at the repo root under whatever name the camera gave them (e.g. `IMG_8321.jpeg`). On github.com (works fine from a phone browser): open this repo → **Add file → Upload files** → commit to `main`.

From there, renaming into the convention above, filing into the right county folder, and writing the matching metadata is handled by the [`rename-images`](https://github.com/JaredLincenberg/jaredlincenberg.github.io/blob/main/.claude/skills/rename-images/SKILL.md) Claude Code skill in the site repo — it pulls EXIF date/GPS, reverse-geocodes the county and location, and matches the photo to an iNaturalist observation.

## Linking to a photo

Once filed, the live URL is:

```
https://jaredlincenberg.github.io/photos/<county-slug>/<filename>
```

Use that URL in the main site. Don't link via `raw.githubusercontent.com` — GitHub rate-limits that domain; the `github.io` Pages URL isn't subject to the same limit.

## Metadata

Every photo here has a matching entry in the site repo's [`_data/photos.yml`](https://github.com/JaredLincenberg/jaredlincenberg.github.io/blob/main/_data/photos.yml) — that's what actually drives the photo grid, captions, and iNaturalist links on the site. Example entry:

```yaml
2026-08-09-crown-hill-park-leafhopper.jpeg:
  location: Crown Hill Park
  county: Jefferson County
  width: 2048
  height: 1536
  description: Leafhopper
  datetime: "2026-08-09 19:53:16"
  lat: 39.7555917
  lon: -105.1027139
  alt: A leafhopper at Crown Hill Park
  caption: ""
  observation: https://www.inaturalist.org/observations/389876396
  # optional fields:
  # tags: [yellowstone-trip]
  # highlight: true
  # related_observations:
  #   - https://www.inaturalist.org/observations/...
```

`county` must be spelled so Jekyll's `slugify` filter matches the actual folder name above (e.g. `Denver County` → `denver-county`).

## Why a separate repo

Keeps the [jaredlincenberg.github.io](https://github.com/JaredLincenberg/jaredlincenberg.github.io) repo (and any local clones of it) free of hundreds of image files, while still keeping everything inside GitHub — no third-party hosting account needed.
