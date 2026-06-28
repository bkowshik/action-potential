# action-potential

An LLM-curated digest of NeuroAI and Brain–Computer Interfaces.

## Task: Refresh source digests

`sources.md` has two groups, each refreshed into its own subfolder of `sources/`:

| Group in `sources.md`     | Output folder           | What each file lists          |
| ------------------------- | ----------------------- | ----------------------------- |
| `## Companies`            | `sources/companies/`    | Blog/newsroom posts           |
| `## GitHub repositories`  | `sources/repositories/` | Tagged releases (no PRs/issues) |

When asked to refresh, update, or run the digest, do both tracks. Keep the work source-by-source so a partial run still produces valid per-source files.

**Shared rules for every entry (both tracks):**
- Use the real date in ISO `YYYY-MM-DD`. If only month/year is known, use the first of that month and append ` _(month approx.)_`.
- Include only entries dated **2026-01-01 or later** (today is the upper bound).
- Deduplicate; sort by date descending (newest first).
- If a source has no qualifying entries, still create the file with a `_No … since 2026-01-01._` line.

### A. Companies → `sources/companies/`

1. For each source under `## Companies`, find every post published **on or after 2026-01-01**:
   - **Use the `Feed:` URL recorded in `sources.md`.** When it's a feed URL, fetch it directly — it returns dates, titles, and URLs compactly in one request (far cheaper than rendering HTML). Don't re-discover feeds that are already recorded.
   - When the recorded feed is `none`, fetch the blog index once and read dates/titles from the listing; only open an individual post page when the date isn't on the listing. Use `WebSearch` as a fallback for JS-rendered sites that don't render in `WebFetch`.
   - Only discover a feed (`/feed/`, `/rss`, `/blog/feed/`, `?format=rss`, or `<link rel="alternate">` in the page head) when adding a new source or when a recorded feed has broken — then update `sources.md` with the result and the verification date.
2. Write one file per company at `sources/companies/<name>.md` (lowercase kebab-case, e.g. `neuralink.md`, `precision-neuroscience.md`):
   - Start with an `# <Company>` heading.
   - One post per line: `- YYYY-MM-DD — [Post title](https://full-post-url)` (canonical post URL, not the blog index).
   - Empty fallback: `_No posts published since 2026-01-01._`

### B. GitHub repositories → `sources/repositories/`

1. For each repo under `## GitHub repositories`, list every **release** published on or after 2026-01-01. The recorded `Feed:` is the repo's `…/releases.atom` (releases only — no pull-request or issue noise).
   - Cheapest path is a script, not the model: `gh api "repos/<owner>/<repo>/releases?per_page=100" --paginate` and filter `published_at >= "2026-01-01"`. (Or parse the `releases.atom` feed.) Don't enumerate tags or commits.
2. Write one file per repo at `sources/repositories/<project>.md` (lowercase kebab-case, e.g. `mne-python.md`, `liblsl.md`, `openbci-gui.md`):
   - Start with a `# <Project>` heading.
   - One release per line: `- YYYY-MM-DD — [tag](https://github.com/<owner>/<repo>/releases/tag/<tag>)` (use the release's `published_at` date and `tag_name`).
   - Empty fallback: `_No releases published since 2026-01-01._`

## Cost notes

Refreshing is mechanical fetch-and-extract — keep it cheap:

- **Use a cheaper model** for the scraping work (Haiku/Sonnet sub-agents), not the top-tier model.
- **Cap effort per source:** prefer one feed fetch; do not enumerate sitemaps or open every post page to verify dates.
- **Filter for relevance** on broad publishers (e.g. Google DeepMind, Allen Institute): include only NeuroAI / brain / BCI posts, not general AI or unrelated science.
- For a fully automated refresh, a small feed-parsing script (curl/Python + feedparser) that regenerates `sources/` costs ~no model tokens — prefer it for sources that expose clean feeds.
- The GitHub repositories track is almost entirely scriptable: a `gh api .../releases --paginate` loop (or `releases.atom` parse) regenerates `sources/repositories/` with no model tokens at all — keep it as a script, not sub-agent work.
