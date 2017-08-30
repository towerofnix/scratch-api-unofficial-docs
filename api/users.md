# `/users/` API

The user API contains utilities for working with user pages.

### [`GET /users/<username>`](id:users-username)

Gets metadata about the user. Returns a [user object](definitions/user_object.md).

### [`GET /users/<username>/following`](id:users-username-following)

Gets the users that the user is following. Returns an array of [user objects](definitions/user_object.md). [Limited](../etc/limits_and_offsets.md) to 20 results per request.

### [`GET /users/<username>/followers`](id:users-username-followers)

Gets the users that are following the user. Returns an array of [user objects](definitions/user_object.md). [Limited](../etc/limits_and_offsets.md) to 20 results per request.
