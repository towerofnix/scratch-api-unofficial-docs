# Studio Object

A studio object looks like htis:

```
{
    "id": /* The studio's ID */
    "title": /* The title of the studio */
    "host": /* The user ID of the studio's current host */
    "description": /* The studio's complete description */
    "visibility": /* The studio's visibility. */
    "public": /* Whether or not the studio is public */
    "open_to_all": /* Whether or not anyone can add projects to the studio */
    "comments_allowed": /* Whether or not comments are allowed */
    "image": /* The URL of the studio's thumbnail image */
    "history": {
        "created": /* The timestamp of when the studio was created */
        "modified": /* The timestamp of when the studio was last updated */
    }
    "stats": {
        "comments": /* The number of comments on the studio */
        "followers": /* The number of users who are following the studio */
        "managers": /* The number of managers for the studio */
        "projects": /* The number of projects in the studio */
    }
}
```
