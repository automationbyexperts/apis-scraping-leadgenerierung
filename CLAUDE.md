# CLAUDE.md

German translation of `lead-generation-scraping-apis`, published as `github.com/automationbyexperts/apis-scraping-leadgenerierung`
(local folder `all_public_actors/APIFY_GITHUB/apis-scraping-leadgenerierung`). Same affiliate model: every Apify link
carries `?fpr=youssef`. Read `lead-generation-scraping-apis/CLAUDE.md` for how the build works; everything there applies here.

This folder is **not an actor**. Never run `apify push` here.

## What differs from the English catalog

- `scripts/config.json` carries the translation: `title`, `tagline`, `intro`, `faq`, every group
  `title` and `blurb`, and the `ui` block, which overrides every sentence in `build.py`'s `UI_EN`.
  Group keywords stay English because they match English Store text.
- A regional group sits **first** in `groups` (`dach`: Deutschland, Österreich und Schweiz), so a local tool is
  filed under its country instead of a generic topic.
- `extraSearches` runs Store searches for local sources that never reach the category's popularity
  top. A hit is kept only when its **title or slug** names a keyword of the regional group, because
  Store search also matches descriptions. Keywords are prefix matches (`\bkeyword`), so a short one
  over-matches: `gemi` pulled in Gemini AI tools and `11880` a German directory before they were cut.
  Country names were removed from the shop catalogs because they dragged in real estate and job tools.
- Actor titles and descriptions stay in the Store's language (mostly English); the README says so.
- `languages` links every language version of the catalog; add a new one to every sibling config.

`build.py` is byte-identical across all category catalogs in `APIFY_GITHUB/`. Change it in one,
copy it to all of them.
