The user API contains utilities for working with user pages.

### [`GET /users/<username>`](id:users-username)

Gets metadata about <u>username</u>. Returns a [user object](definitions/user_object.md).

### [`GET /users/<username>/following`](id:users-username-following)

Gets the users that <u>username</u> is following. Returns an array of user objects.

It gets only the last 20 users that the target user is following. The paramater **`limit`** can be changed to a number less than or equal to 20 to decrease the number of users returned in the array, and the paramater **`offset`** can be set to offset the following selection - for example, `?offset=3&limit=2` will get the fourth and fifth most recent users the target user is following.