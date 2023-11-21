# `/news` API

The news API returns data given to the "Scratch News" box on the homepage.

### `GET /news`

Gets news items. Returns an array of [news objects](definitions/news_object.md). [Limited](../etc/limits_and_offsets.md) to 40 results per request, but returns 20 by default.
