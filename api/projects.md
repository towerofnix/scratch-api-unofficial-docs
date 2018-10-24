# `/projects` API

Returns data related to Scratch projects.

### `GET /projects/<id>`

Gets metadata about the project. Returns a [project object](definitions/project_object.md). If the project has not been shared, this endpoint [requires authentication](../etc/authentication.md).

### `GET /projects/<id>/remixes`

Gets a list of remixes of the project. Returns an array of [project objects](definitions/project_object.md). [Limited](../etc/limits_and_offsets.md) to 40 results per request, but returns 20 by default.

### `GET /projects/<id>/studios`

Gets a list of studios the project is added to. Returns an array of [studio objects](definitions/studio_object.md). [Limited](../etc/limits_and_offsets.md) to 40 results per request, but returns 20 by default.

### `GET /projects/<id>/favorites/user/<username>`

Gets whether or not the project has been loved by the user. [Requires authentication.](../etc/authentication.md) Returns an object that looks like this:

```
{
    "projectId": /* The ID of the project */
    "userFavorite": /* True or false */
}
```

### `GET /projects/<id>/loves/user/<username>`

Gets whether or not the project has been loved by the user. [Requires authentication.](../etc/authentication.md) Returns an object that looks like this:

```
{
    "projectId": /* The ID of the project */
    "userLove": /* True or false */
}
```

### `GET /projects/count/all`

Gets the total number of projects that have been shared on the Scratch site, in this format:

```
{
    "count": /* Total number of projects shared */
}
```
