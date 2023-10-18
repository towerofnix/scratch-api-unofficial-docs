# `/proxy/` API

The proxy API contains many utilities. The code for each endpoint under the proxy API interacts with the old Scratch API system; essentially, the proxy API is used for parts of the Scratch API which haven't yet been migrated.

### `GET /proxy/featured`

Gets the projects featured on the homepage. Returns an object of which each of its properties' values are arrays of `/proxy`-specific project objects (not [normal project objects](definitions/project_object.md)):

```
{
    "community_featured_projects": /* Featured projects */
    "community_featured_studios": /* Featured studios */
    "community_most_loved_projects": /* What the community is loving / top loved projects */
    "community_most_remixed_projects": /* What the community is remixing / top remixed projects */
    "community_newest_projects": /* Recently shared projects */
    "curator_top_projects": /* Curated projects */
    "scratch_design_studio": /* Projects in the Scratch Design Studio */
}
```

Each item in any of those arrays is a project, and follows this format:

```
{
    "creator": /* Username of the user who created the project */
    "id": /* The project's ID */
    "love_count": /* How many people have clicked the love button on the project's page */
    "remixers_count": /* How many people have remixed the project */
    "thumbnail_url": /* URL to the project's thumbnail */
    "title": /* The project's title */
    "type": "project"
}
```

### `POST /proxy/comments/project/<id>`

Sends a new comment (top-level or reply) on the project. [Requires authentication.](../etc/authentication.md) The request body should be a JSON string following this format:

```
{
    "content": /* Content of the comment */
    "parent_id": /* ID of the comment to reply to, or empty string if top-level */
    "commentee_id": /* ID of the user to mention at the start of the comment, or empty string if none */
}
```

If successful, returns a [comment object](definitions/comment_object.md). If the comment is rejected, returns a [comment rejection object](definitions/comment_rejection_object.md). (Note this response will still be 200 OK.)

*(References: [`views/preview/comment/compose-comment.jsx`](https://github.com/scratchfoundation/scratch-www/blob/1534b8938e97bd5bbe2c5bec965545a24ac3202c/src/views/preview/comment/compose-comment.jsx#L80-L149), [`views/preview/presentation.jsx`](https://github.com/scratchfoundation/scratch-www/blob/1534b8938e97bd5bbe2c5bec965545a24ac3202c/src/views/preview/presentation.jsx#L612))*

### `DELETE /proxy/comments/project/<id>/comment/<id>`

Deletes an existing comment on the project. [Requires authentication.](../etc/authentication.md) Returns an empty object.

*(References: [`redux/project-comment-actions.js`](https://github.com/scratchfoundation/scratch-www/blob/1534b8938e97bd5bbe2c5bec965545a24ac3202c/src/redux/project-comment-actions.js#L117-L135))*

### `POST /proxy/comments/studio/<id>`

Sends a new comment (top-level or reply) on the project. [Requires authentication.](../etc/authentication.md) The request body should be a JSON string following this format:

```
{
    "content": /* Content of the comment */
    "parent_id": /* ID of the comment to reply to, or empty string if top-level */
    "commentee_id": /* ID of the user to mention at the start of the comment, or empty string if none */
}
```

If successful, returns a [comment object](definitions/comment_object.md). If the comment is rejected, returns a [comment rejection object](definitions/comment_rejection_object.md). (Note this response will still be 200 OK.)

*(References: [`views/preview/comment/compose-comment.jsx`](https://github.com/scratchfoundation/scratch-www/blob/1534b8938e97bd5bbe2c5bec965545a24ac3202c/src/views/preview/comment/compose-comment.jsx#L80-L149), [`views/studio/studio-comments.jsx`](https://github.com/scratchfoundation/scratch-www/blob/1534b8938e97bd5bbe2c5bec965545a24ac3202c/src/views/studio/studio-comments.jsx#L216))*

### `DELETE /proxy/comments/studio/<id>/comment/<id>`

Deletes an existing comment on the studio. [Requires authentication.](../etc/authentication.md) Returns an empty object.

*(References: [`redux/studio-comment-actions.js`](https://github.com/scratchfoundation/scratch-www/blob/1534b8938e97bd5bbe2c5bec965545a24ac3202c/src/redux/studio-comment-actions.js#L143-L163))*
