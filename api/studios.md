# `/studios/` API

### `GET /studios/<id>/comments`

Gets a list of top-level comments created on the studio. Returns an array of [comment objects](definitions/comment_object.md). [Limited](../etc/limits_and_offsets.md) to 40 results per request, but returns 20 by default.

*(References: [`redux/studio-comment-actions.js`](https://github.com/scratchfoundation/scratch-www/blob/1534b8938e97bd5bbe2c5bec965545a24ac3202c/src/redux/studio-comment-actions.js#L70-L106), [`views/studio/studio-comments.jsx`](https://github.com/scratchfoundation/scratch-www/blob/1534b8938e97bd5bbe2c5bec965545a24ac3202c/src/views/studio/studio-comments.jsx#L54-L60))*

### `GET /studios/<id>/comments/<id>`

Gets a single comment. Returns a [comment object](definitions/comment_object.md).

*(References: [`redux/studio-comment-actions.js`](https://github.com/scratchfoundation/scratch-www/blob/1534b8938e97bd5bbe2c5bec965545a24ac3202c/src/redux/studio-comment-actions.js#L108-L141), [`views/studio/studio-comments.jsx`](https://github.com/scratchfoundation/scratch-www/blob/1534b8938e97bd5bbe2c5bec965545a24ac3202c/src/views/studio/studio-comments.jsx#L54-L60))*

### `GET /studios/<id>/comments/<id>/replies`

Gets a list of replies to a top-level comment on the studio. Returns an array of [comment objects](defintiions/comment_object.md). [Limited](../etc/limits_and_offsets.md) to 40 results per request, but returns 20 by default.

*(References: [`redux/project-comment-actions.js` #1](https://github.com/scratchfoundation/scratch-www/blob/1534b8938e97bd5bbe2c5bec965545a24ac3202c/src/redux/studio-comment-actions.js#L35-L68), [`redux/project-comment-actions.js` #2](https://github.com/scratchfoundation/scratch-www/blob/1534b8938e97bd5bbe2c5bec965545a24ac3202c/src/redux/studio-comment-actions.js#L94-L97), [`redux/project-comment-actions.js` #3](https://github.com/scratchfoundation/scratch-www/blob/1534b8938e97bd5bbe2c5bec965545a24ac3202c/src/redux/studio-comment-actions.js#L134-L139), [`views/studio/studio-comments.jsx`](https://github.com/scratchfoundation/scratch-www/blob/1534b8938e97bd5bbe2c5bec965545a24ac3202c/src/views/studio/studio-comments.jsx#L160-L167))*

### Sending & deleting comments

Comments are sent and deleted through the [/proxy](proxy.md) API:

- [`POST /proxy/comments/studio/<id>`](proxy.md#post-proxycommentstudioid)
- [`DELETE /proxy/comments/studio/<id>/comment/<id>`](proxy.md#post-proxycommentstudioidcommentid)
