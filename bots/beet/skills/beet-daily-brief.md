# Beet daily brief

Use this to compile and deliver a morning or afternoon briefing, from a routine or on demand.

## Gather
- Read `brief_sections`, `brief_sources`, and your feedback memory. If `brief_sources` is empty, run the "Beet getting started" skill instead and stop.
- "What's trending" comes from the public X trends and news tools plus web search.
- For each other section, use its sources: posts from the user's X handle and the accounts they engage with, followed X accounts and topics (public X tools), RSS or Atom feeds (fetch each feed URL and read items newer than the last briefing), and sites or topics (web search). For an X list source, read its current members with the X plugin's get_lists_members (or its posts with get_lists_posts) each time, so new members are picked up. Read web pages, such as the Grok Bot changelog, with web fetch rather than curl, since some sites block plain downloads.
- Follow each section's standing rules from memory, such as what gets top billing.
- About 15 to 18 items at most, each with a real source link. No calendar or tasks.
- Skip items from earlier briefings (for the afternoon, including this morning's) and empty sections. If nothing is new, stay quiet.

## Deliver as a Page
Read the canvas skill first. Make a new Page titled like "Morning brief, Thu Oct 22" or "Afternoon brief, Thu Oct 22", styled like an RSS reader:
- Category tabs across the top: one tab per non-empty section, plus an "All" tab.
- Items are grouped under a visible heading for each category. In the All tab every category gets its own heading above its items, and a single-category tab shows that category's heading too.
- Each item is a card, and the whole card is clickable and opens the source (no separate small link line; a subtle site name label inside the card is fine). The card holds a headline, a 2-3 sentence summary, and a thumbnail image on the side when the source has one.
- Build custom components as needed.

## Thumbnails
The canvas blocks remote image URLs, so never hotlink. Get each source's og:image (for X posts, the media via get_posts_by_ids with expansions=attachments.media_keys), and skip generic site images. Convert them with `python3 /workspace/beet/make_thumbs.py URL...`, which prints one small data:image/webp;base64 string per URL to embed as each item's img src (style width 140, height 96, objectFit cover, borderRadius 10). Never invent images; omit when none.

If `/workspace/beet/make_thumbs.py` doesn't exist, create it with exactly this (it needs Pillow; install it with pip if it's missing):

```python
# usage: python3 make_thumbs.py URL [URL...]  -> prints data URIs (96x64 WebP q30, ~0.3-2KB each)
import sys, io, base64, urllib.request
from PIL import Image, ImageOps
for u in sys.argv[1:]:
    raw = urllib.request.urlopen(urllib.request.Request(u, headers={"User-Agent":"Mozilla/5.0"}), timeout=20).read()
    im = ImageOps.fit(Image.open(io.BytesIO(raw)).convert("RGB"), (96, 64))
    b = io.BytesIO(); im.save(b, "WEBP", quality=30, method=6)
    print("data:image/webp;base64," + base64.b64encode(b.getvalue()).decode())
```

## Then
Send the user a one-line chat note with the Page link.
