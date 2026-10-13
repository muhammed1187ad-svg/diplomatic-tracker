# Diplomatik Temas Haritası — Ekim 2026

This repository is a static diplomatic-activity map based on the user-supplied September design.

## Structure

- `index.html`: map interface, September legacy archive, initial verified October dataset.
- `data/weeks/YYYY-MM-DD.json`: independently dated weekly additions. The filename is the **Monday** beginning that week, e.g. `2026-10-19.json` for 19–25 October.
- `data/legacy_september_2026.json`: preservation copy of the 152 September records from the earlier scan (not re-audited).

## Updating each Monday (no approvals or rebuilding)

1. Research completed meetings for the prior Monday–Sunday (Monday 00:00 to next Monday 00:00, Europe/Istanbul). Include only Presidents, Prime Ministers, Foreign Ministers or Defence Ministers. At least one side must belong to your original country list. Separate bilateral and multilateral; omit telephone conversations, announced but not completed events, and unsubstantiated claims.
2. Save records in an array in a JSON file named for the *Monday on which those meetings happened*: `data/weeks/2026-10-19.json`, for example, for 19–25 October.
3. On GitHub, open the repository, select **Add file > Upload files**, then upload the new weekly JSON (into `data/weeks/`). Commit to `main`.
4. GitHub Pages automatically republishes files. `index.html` automatically requests expected weekly filenames for all weeks beginning 28 September 2026, including future weeks as their dates arrive. **No index.html changes are required.** Missing weeks are skipped as 404 and other retrieval failures display an error notice.
5. The month and week selectors always filter across all available records, preserving old weeks.

### Important: GitHub upload path

In the GitHub web UI navigate into `data/weeks/` *before* selecting **Add file > Upload files**. Uploading from the repository root would put JSON in the wrong directory. For a correction to an existing week, edit the JSON file directly in GitHub (pencil icon), or replace the file through your Git client. Do not create duplicate records with new IDs.

### JSON example

```json
[
  {
    "id": "2026-10-19-001",
    "city": "Ankara",
    "date": "19 Ekim 2026",
    "start_date": "2026-10-19",
    "end_date": "2026-10-19",
    "parties": "Türkiye–Ülke | Ad–Ad",
    "topic": "Kısa görüşme özeti",
    "kind": "İkili",
    "source": "https://official-government-source.example/article",
    "lat": 39.9334,
    "lon": 32.8597
  }
]
```

`kind` must be exactly `İkili` or `Çok taraflı`. For **new cities** not already on the map, include numeric `lat` and `lon` properties in the weekly JSON entry so the map can pin the city automatically; existing cities use the built-in coordinate table. This avoids changing `index.html` every week. Prefer city-center coordinates rather than inventing a street address.

## Publishing initial October update

Upload `index.html` at the **repository root**, and upload three files in `data/weeks/`:
- `2026-09-28.json` (October 4 records)
- `2026-10-05.json` (October 5–11)
- `2026-10-12.json` (October 12, current partial week)
The initial October records are already embedded in `index.html` as a fallback; the weekly files are authoritative and can override those records by their IDs.

## Scope and data quality

September: 152 legacy records have not been independently audited, retained without approval workflow because requested.
October: selected source-confirmed meetings through 12 October 2026, not a claim of exhaustive coverage. Phone calls, future visit announcements and meetings involving only other ranks are excluded.

## Hosting

GitHub Pages: Settings → Pages → Deploy from branch → main / (root).
Expected URL: https://muhammed1187ad-svg.github.io/diplomatic-tracker/

Website is public even with `noindex` meta; `noindex` only discourages search indexing.
