# `/explore` and `/search` APIs

The explore API returns data regarding projects and studios according to a given sort order and optionally a search query.

The search API returns the results of a search.

### `GET /explore/projects`

Fetches projects according to a tag. Takes [typical `explore` and `search` options](#typical-explore-and-search-options).

### `GET /explore/studios`

Fetches studios according to name. Takes [typical `explore` and `search` options](#typical-explore-and-search-options).

### `GET /search/projects`

Searches for projects. Takes [typical `explore` and `search` options](#typical-explore-and-search-options).

### `GET /search/studios`

Searches for studios. Takes [typical `explore` and `search` options](#typical-explore-and-search-options).

### Typical `explore` and `search` options

All `explore` and `search` endpoints are [limited](../etc/limits_and_offsets.md) to 40 results per request, but return 20 by default. They all take the following options:

* `?q`: Optional search query, to filter only results which match the query. Usually this means a matching name, but under `/explore/projects` it means a matching project tag.
* `?mode`: "Search mode": how to sort results. Can be one of the following: `popular`, `trending`, `recent`. Defaults to `popular`.
