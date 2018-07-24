# `/comments` API

The comments API returns data related to comments made throughout the Scratch website.

### `GET /comments/project/<id>`

Gets a list of top-level comments created on the project. Returns an array of [comment objects](definitions/comment_object.md). [Limited](../etc/limits_and_offsets.md) to 40 results per request, but returns 20 by default.

### `GET /comments/project/<project id>/<comment id>`

Gets a list of replies to the comment created on the project. Returns an array of [comment objects](definitions/comment_object.md). [Limited](../etc/limits_and_offsets.md) to 40 results per request, but returns 20 by default.
