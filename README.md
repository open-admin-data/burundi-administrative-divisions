# Burundi Administrative Divisions / Burundi



## Overview

| Item | Details |
|------|---------|
| Province | 18 |
| Commune | 119 |
| Colline | 2,917 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-05-27 |
| Website | [openadmindata.org/bi](https://openadmindata.org/bi/) |
| API | [openadmindata.org/api/bi](https://openadmindata.org/api/bi/) |

## Browse by Province

| # | Province | Communes | Collines | Link |
|---|----|----|----|------|
| 1 | Bubanza | 5 | 88 | [Browse](divisions/bubanza-bdi001/) |
| 2 | Bujumbura Mairie | 3 | 103 | [Browse](divisions/bujumbura-mairie-bdi017/) |
| 3 | Bujumbura Rural | 9 | 160 | [Browse](divisions/bujumbura-rural-bdi002/) |
| 4 | Bururi | 6 | 130 | [Browse](divisions/bururi-bdi003/) |
| 5 | Cankuzo | 5 | 87 | [Browse](divisions/cankuzo-bdi004/) |
| 6 | Cibitoke | 6 | 129 | [Browse](divisions/cibitoke-bdi005/) |
| 7 | Gitega | 11 | 268 | [Browse](divisions/gitega-bdi006/) |
| 8 | Karuzi | 7 | 146 | [Browse](divisions/karuzi-bdi007/) |
| 9 | Kayanza | 9 | 301 | [Browse](divisions/kayanza-bdi008/) |
| 10 | Kirundo | 7 | 198 | [Browse](divisions/kirundo-bdi009/) |
| 11 | Makamba | 6 | 142 | [Browse](divisions/makamba-bdi010/) |
| 12 | Muramvya | 5 | 100 | [Browse](divisions/muramvya-bdi011/) |
| 13 | Muyinga | 7 | 230 | [Browse](divisions/muyinga-bdi012/) |
| 14 | Mwaro | 6 | 134 | [Browse](divisions/mwaro-bdi013/) |
| 15 | Ngozi | 9 | 305 | [Browse](divisions/ngozi-bdi014/) |
| 16 | Rumonge | 5 | 108 | [Browse](divisions/rumonge-bdi018/) |
| 17 | Rutana | 6 | 148 | [Browse](divisions/rutana-bdi015/) |
| 18 | Ruyigi | 7 | 140 | [Browse](divisions/ruyigi-bdi016/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-province.json](data/all-province.json) | JSON | All 18 province records |
| [all-commune.json](data/all-commune.json) | JSON | All 119 commune records |
| [all-colline.json](data/all-colline.json) | JSON | All 2,917 colline records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-province.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['commune']} communes")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-province.json", "utf-8"));
console.log(`Total: ${data.length} provinces`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=province, 2=commune, 3=colline |
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
divisions/{province-slug}/
divisions/{province-slug}/{commune-slug}/
```

Collines are listed inline in each commune's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-province links
- [Per-province data](docs/llms-full/) — Full data by province

## Citation

```
Burundi Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/burundi-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
