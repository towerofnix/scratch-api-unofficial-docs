# Message Object

A message object looks like this:

```
{
    "id": /* Message ID */
    "datetime_created": /* The date of the notification */
    "actor_username": /* The username of whoever acted (e.g. who loved your project) */
    "actor_id": /* The ID of whoever acted */
    "type": /* A message type */
    /* ..And then type-specific properties; see below. */
}
```

## Event Types

* `followuser`: Somebody followed the user

* `loveproject`: Somebody loved one of the user's projects

  ```
  {
      "project_id": /* The ID of the project which was loved */
      "title": /* The name of the project which was loved */
  }
  ```

* `favoriteproject`: Somebody favorited one of the user's projects

  ```
  {
      "project_id": /* The ID of the project which was favorited */
      "title": /* The name of the project which was favorited */
  }
  ```

* `remixproject`: Somebody remixed one of the user's projects

  ```
  {
      "project_id": /* The ID of the remix */
      "title": /* The name of the remix */
      "parent_id": /* The ID of the project which was remixed */
      "parent_title": /* The name of the project which was remixed */
  }
  ```

* `addcomment`: Somebody made a comment

  ```
  {
      "comment_type": /* A number referring to the type of place where the comment was posted (either 0, 1, or 2) */
      "comment_obj_id": /* The ID of the place where the comment was posted */
      "comment_obj_title": /* The name of where the comment was posted */
      "comment_id": /* The ID of the comment */
      "comment_fragment": /* The text content of the comment */
      "commentee": /* The username of the person which the user replied to (or undefined, if nobody) */
  }
  ```

  The `comment_type` can have one of three values:

  * `0`: the comment was made on a project
  * `1`: the comment was made on a profile page
  * `2`: the comment was made in a studio's comment section

  `comment_obj_id` is just the ID that shows up in a URL; for example, if `comment_type` is 0, then the full URL for the comment is `https://scratch.mit.edu/projects/<comment_obj_id>/#comments-<comment_id>`.

* `curatorinvite`: Somebody invited the user to a studio
* `becomeownerstudio`: Somebody promoted the user to a manager in a studio
* `studioactivity`: There was activity in a studio that the user is following

  All studio message types (`curatorinvite`, `becomeownerstudio`, and `studioactivity`) have this data:

  ```
  {
      "gallery_id": /* The ID of the studio */
      "title": /* The name of the studio */
  }
  ```

* `forumpost`: Somebody made a new post in a forum thread that the user is following

  ```
  {
      "topic_id": /* The ID of the topic */
      "topic_title": /* The name of the topic */
  }
  ```

* `userjoin` - The user joined Scratch (and was given this welcome notification)

