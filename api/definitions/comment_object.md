# Comment Object

A comment object looks like this:

```
{
    "author": {
        "id": /* The author's user ID */
        "username": /* The author's username */
        "image": /* The URL of the author's profile picure */
    }
    "id": /* The comment's ID */
    "parent_id": /* The parent comment's ID, or null if a top-level comment */
    "content": /* The text content of the comment */
    "datetime_created": /* The timestamp when the comment was sent */
    "datetime_modified": /* The timestamp when the comment was last modified */
    "reply_count": /* How many replies the comment has, or 0 for a reply */
}
```
