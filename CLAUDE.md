# action-potential

An LLM-curated digest of NeuroAI and Brain–Computer Interfaces.

## Task: Refresh source digests

When asked to refresh, update, or run the digest:

1. **Read `sources.md`** — it lists each source company and its blog/newsroom URL.
2. **Check each source.** Find every post published **on or after 2026-01-01**:
   - **Try the RSS/Atom feed first** (`/feed/`, `/rss`, `/blog/feed/`, `/news/feed/`, or a `<link rel="alternate">` in the page head). A feed returns dates, titles, and URLs compactly in one fetch — far cheaper than rendering HTML.
   - If there's no feed, fetch the blog index once and read dates/titles from the listing. Only open an individual post page when the date isn't on the listing.
   - Use `WebSearch` only as a fallback for JS-rendered sites that don't render in `WebFetch`.
3. **Write one file per source** in the `sources/` directory:
   - Filename = company name, lowercase, kebab-case, `.md` (e.g. `neuralink.md`, `blackrock-neurotech.md`, `precision-neuroscience.md`).
   - Start the file with an `# <Company>` heading.
   - List posts **newest first**, one per line, as:
     `- YYYY-MM-DD — [Post title](https://full-post-url)`
4. **Rules for entries:**
   - Use the real publication date in ISO `YYYY-MM-DD`. If only month/year is known, use the first of that month and append ` _(month approx.)_`.
   - Include only posts dated **2026-01-01 or later** (today is the upper bound).
   - Deduplicate; sort by date descending.
   - Link the title to the full canonical post URL, not the blog index.
   - If a source has no qualifying posts, still create the file with: `_No posts published since 2026-01-01._`

Keep the work source-by-source so a partial run still produces valid per-source files.

## Cost notes

Refreshing is mechanical fetch-and-extract — keep it cheap:

- **Use a cheaper model** for the scraping work (Haiku/Sonnet sub-agents), not the top-tier model.
- **Cap effort per source:** prefer one feed fetch; do not enumerate sitemaps or open every post page to verify dates.
- **Filter for relevance** on broad publishers (e.g. Google DeepMind, Allen Institute): include only NeuroAI / brain / BCI posts, not general AI or unrelated science.
- For a fully automated refresh, a small feed-parsing script (curl/Python + feedparser) that regenerates `sources/` costs ~no model tokens — prefer it for sources that expose clean feeds.
