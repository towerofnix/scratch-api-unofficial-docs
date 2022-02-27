# `/users/` API

The user API contains utilities for working with user pages.

### `GET /users/<username>`

Gets metadata about the user. Returns a [user object](definitions/user_object.md).

### `GET /users/<username>/projects`

Gets a list of projects that have been shared by the user. Note that it returns oldest projects first; use [`offset`](../etc/limits_and_offsets.md) to find more recent projects.

Returns an array of [project objects](definitions/project_object.md). [Limited](../etc/limits_and_offsets.md) to 40 results per request.

### `GET /users/<username>/projects/<projectID>`

Gets a specific project created by the user, given its unique project ID. Returns a [project object](definitions/project_object.md).

### `GET /users/<username>/studios/curate`

Gets a list of studios that the user curates. Returns an array of [studio objects](definitions/studio_object.md). [Limited](../etc/limits_and_offsets.md) to 40 results per request, but returns 20 by default.

### `GET /users/<username>/favorites`

Gets a list of projects that have recently been favorited by the user. Returns an array of [project objects](definitions/project_object.md). [Limited](../etc/limits_and_offsets.md) to 40 results per request.

### `GET /users/<username>/followers`

Gets the users that are following the user. Returns an array of [user objects](definitions/user_object.md). [Limited](../etc/limits_and_offsets.md) to 40 results per request.

### `GET /users/<username>/following`

Gets the users that the user is following. Returns an array of [user objects](definitions/user_object.md). [Limited](../etc/limits_and_offsets.md) to 40 results per request.

### `GET /users/<username>/following/studios/projects`

Gets a list of projects that have recently been added to studios that the given user is following. Returns an array of [project objects](definitions/project_object.md). [Requires authentication.](../etc/authentication.md)

### `GET /users/<username>/following/users/loves`

Gets a list of projects that have recently been loved by users that the given user is following. Shows up as "Projects Loved by Scratchers I'm Following" on the front page.  Returns an array of [project objects](definitions/project_object.md). [Requires authentication.](../etc/authentication.md)

### `GET /users/<username>/following/users/projects`

Gets a list of projects that have recently been shared by users that the given user is following. Returns an array of [project objects](definitions/project_object.md). [Requires authentication.](../etc/authentication.md)

### `GET /users/<username>/following/users/activity`

Gets events that show up in the "What's Happening" feed on the front page.  Returns an array of [activity event objects](definitions/activity_event_object.md).  [Requires authentication.](../etc/authentication.md)

### `GET /users/<username>/messages`

Gets the content of all messages the user has (including both read and unread ones). Returns an array of [message objects](definitions/message_object.md). [Limited](../etc/limits_and_offsets.md) to 40 results per request. [Requires authentication.](../etc/authentication.md)

### `GET /users/<username>/messages/count`

Gets the number of notifications the user currently has (this is the bubble-number displayed in the navigation bar).

Returns an object in this format:

```
{
    "count": /* Number of messages the user currently has */
}
```

### `GET /users/<username>/projects/<id>/comments`

Gets a list of top-level comments created on the project. Returns an array of [comment objects](definitions/comment_object.md). [Limited](../etc/limits_and_offsets.md) to 40 results per request, but returns 20 by default.

### `GET /users/<username>/projects/<id>/comments/<id>`

Gets a single comment. Returns a [comment object](definitions/comment_object.md).

Note that `reply_count` will always be zero when a comment is requested from this endpoint, even if that comment has replies.

### `GET /user/<username>/projects/<id>/comments/<id>/replies`

Gets a list of replies to the top-level comment. Returns an array of [comment objects](defintiions/comment_object.md). [Limited](../etc/limits_and_offsets.md) to 40 results per request, but returns 20 by default.

### Sending & deleting comments

Comments are sent and deleted through the [/proxy](proxy.md) API:

- [`POST /proxy/comments/project/<id>`](proxy.md#post-proxycommentprojectid)
- [`DELETE /proxy/comments/project/<id>`](proxy.md#post-proxycommentprojectidcommentid)
