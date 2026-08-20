# San Marino Administrative Divisions / San Marino



## Overview

| Item | Details |
|------|---------|
| Municipality | 9 |
| Locality | 20 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-20 |
| Website | [openadmindata.org/sm](https://openadmindata.org/sm/) |
| API | [openadmindata.org/api/sm](https://openadmindata.org/api/sm/) |
| Flag | [PNG](https://onlygames.me/flags-png/sm/) · [SVG](https://onlygames.me/flags-svg/sm/) · [PDF](https://onlygames.me/flags-pdf/sm/) |
| National Anthem | [🎵 Listen & Download San Marino National Anthem MP3](https://onlygames.me/national-anthems/sm/) |

## Browse by Municipality

| # | Municipality | Localitys | Link |
|---|----|----|------|
| 1 | Borgo Maggiore | 5 | [Browse](divisions/borgo-maggiore-sm01/) |
| 2 | San Marino | 1 | [Browse](divisions/san-marino-sm02/) |
| 3 | Acquaviva | 3 | [Browse](divisions/acquaviva-sm03/) |
| 4 | Serravalle | 2 | [Browse](divisions/serravalle-sm04/) |
| 5 | Domagnano | 4 | [Browse](divisions/domagnano-sm05/) |
| 6 | Faetano | 2 | [Browse](divisions/faetano-sm06/) |
| 7 | Montegiardino | 0 | [Browse](divisions/montegiardino-sm07/) |
| 8 | Fiorentino | 2 | [Browse](divisions/fiorentino-sm08/) |
| 9 | Chiesanuova | 1 | [Browse](divisions/chiesanuova-sm09/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-castello.json](data/all-castello.json) | JSON | All 9 municipality records |
| [all-locality.json](data/all-locality.json) | JSON | All 20 locality records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-castello.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['locality']} localitys")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-castello.json", "utf-8"));
console.log(`Total: ${data.length} municipalitys`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=municipality, 2=locality |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{castello-slug}/
```

Localitys are listed inline in each municipality's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-municipality links
- [Per-municipality data](docs/llms-full/) — Full data by municipality

## Citation

```
San Marino Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/san-marino-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
