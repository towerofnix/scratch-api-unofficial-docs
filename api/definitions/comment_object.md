# Comment Object

A comment object looks like this:

```
{
    "id": /* The comment's ID */
    "author": {
        "id": /* The author's user ID */
        "username": /* The author's username */
        "image": /* The URL of the author's profile picure */
    }
    "parent_id": /* The parent comment's ID, or null if a top-level comment */
    "commentee_id": /* The ID of the user replied to, or null if a top-level comment */
    "content": /* The text content of the comment */
    "datetime_created": /* The timestamp when the comment was sent */
    "datetime_modified": /* The timestamp when the comment was last modified */
    "reply_count": /* How many replies the comment has, or 0 for a reply */
}
```
