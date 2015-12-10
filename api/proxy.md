The proxy API contains many utilities, generally returning content likely to be modified frequently.

## `/proxy/users`

### `GET /proxy/users/<name>/activity`

```
[
    { /* An activity event */
        "actor": {
            "admin": /* Is the user an admin? */
            "pk": /* User's ID */
            "thumbnail_url": /* URL to the user's thumbnail */
            "username": /* User's username */
        }
        "datetime_created": /* Date of the event */
        "extra_data": /* Data object specific to the type of event - see below */
        "message": /* HTML display message */
        "obj_id": /* Message ID */
        "pk": /* ??? */
        "type": /* Numeric type of event - see below */
    } ...
]
```
