# Canadian licensed cannabis store counts (by province and city)

Aggregate counts of licensed, open retail cannabis stores in Canada, compiled from provincial and territorial registries. As of **2026-11-20**: **4,030** stores in 13 provinces and territories, across **1,027** cities.

This is an extract of the statistics at <https://wherestheweedat.ca/stats> (live, with methodology). The directory itself is at <https://wherestheweedat.ca>.

Maintained by Where's The Weed At (London, Ontario). Contact: hello@wherestheweedat.ca

## Files

| File | Contents |
|---|---|
| `data/stores-by-province.csv` | One row per province/territory |
| `data/stores-by-city.csv` | One row per city with at least one store |

### `stores-by-province.csv`
- `province`: province or territory name
- `code`: two-letter code (AB, BC, MB, NB, NL, NS, NT, NU, ON, PE, QC, SK, YT)
- `licensed_stores_open`: number of licensed retail stores listed as open
- `source_registry`: the registry or list the stores were read from
- `source_url`: URL of that registry
- `registry_retrieved_on`: most recent date a store record from that source was retrieved (ISO 8601)
- `as_of`: date of the count (ISO 8601)

### `stores-by-city.csv`
- `province`, `code`: as above
- `city`: city or municipality name as shown in the registry (spelling variants merged)
- `licensed_stores_open`: count in that city
- `as_of`: date of the count

## How counts are built
Store records are read from each regulator's or authorized retailer's public register (see `source_url`), matched against earlier records, and checked by hand where entries change. A store is counted when it is listed as open and is not marked closed or removed in our database. Test records and stores that have asked to be unlisted are excluded. Only counts are published here: no store names, addresses, licence numbers, coordinates or licence-holder names.

Caveats:
- Registries refresh on their own schedules; `registry_retrieved_on` shows when each was last read. Counts can differ from a registry's current state.
- 9 of the 4,030 stores (British Columbia) are marked "licensed, not yet open" by their registry and are included in the counts on <https://wherestheweedat.ca/stats> as published.
- Quebec counts the government-run SQDC branches; New Brunswick, Nova Scotia, PEI and the territories combine government-run and private stores as each registry lists them. Definitions of a "store" differ by province.
- The count is a registry-based tally, not a market estimate.

## Source registries and terms
The source registries keep their own terms. We have not confirmed an open-data licence for each one, so we do not claim one. This repository publishes only aggregate counts (facts), not the registry records. Check each source's terms before reusing its records. If you need store-level data, go to the registries linked in `stores-by-province.csv` and read their terms.

## Licence
Our compilation is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). See `LICENSE`. No endorsement by any regulator or government is implied.

## Cite
> Where's The Weed At. (2026). *Canadian Licensed Cannabis Store Counts by Province and City (from official registries)* (version 2026-11-20) [Data set]. https://wherestheweedat.ca/stats

Machine-readable: `CITATION.cff`.
