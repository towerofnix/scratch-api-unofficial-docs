# `/projects` API

Returns data related to Scratch projects.

### `GET /projects/<id>`

Gets metadata about the project. Returns a [project object](definitions/project_object.md).

### `GET /projects/<id>/remixes`

Gets a list of remixes of the project. Returns an array of [project objects](definitions/project_object.md). [Limited](../etc/limits_and_offsets.md) to 40 results per request, but returns 20 by default.

### `GET /projects/<id>/studios`

Gets a list of studios the project is added to. Returns an array of [studio objects](definitions/studio_object.md). [Limited](../etc/limits_and_offsets.md) to 40 results per request, but returns 20 by default.

### `GET /projects/count/all`

Gets the total number of projects that have been shared on the Scratch site, in this format:

```
{
    "count": /* Total number of projects shared */
}
```
