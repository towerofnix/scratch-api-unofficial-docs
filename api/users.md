# `/users/` API

The user API contains utilities for working with user pages.

### [`GET /users/<username>`](id:users-username)

Gets metadata about the user. Returns a [user object](definitions/user_object.md).

### [`GET /users/<username>/following`](id:users-username-following)

Gets the users that the user is following. Returns an array of [user objects](definitions/user_object.md).

It gets only the last 20 users that the target user is following. The paramater `limit` can be changed to a number less than or equal to 20 to decrease the number of users returned in the array, and the paramater `offset` can be set to offset the following selection - for example, `?offset=3&limit=2` will get the fourth and fifth most recent users the target user is following.

### [`GET /users/<username>/followers`](id:users-username-followers)

Gets the users that are following the user. Returns an array of [user objects](definitions/user_object.md).
