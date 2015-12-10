The user API contains utilities for working with user pages.

### User Object

A user object looks like this:

```
{
    "id": /* User ID */
    "username": /* Username */
    "history": {
        "joined": /* Date joined */
        "login": /* Last login date? */
    }
    "profile": {
        "id": /* Profile ID? */
        "avatar": /* Part of a path to avatar? */
        "status": /* What I'm working on */
        "bio": /* About me */
    }
}
```

### `GET /users/<username>`

Gets metadata about <u>username</u>. Returns a [user object](#user-object).

### `GET /users/<username>/following`

Gets the users that <u>username</u> is following. Returns an array of [user objects](#user-object):

```
[
    user_object
    user_object
    user_object
    ...
]
```

It gets only the last 20 users that the target user is following. The paramater **`limit`** can be changed to a number less than or equal to 20 to decrease the number of users returned in the array, and the paramater **`offset`** can be set to offset the following selection - for example, `?offset=3&limit=2` will get the fourth and fifth most recent users the target user is following.