# `/comments` API

There aren't any endpoints under `/comments` at the time of writing, but you may be looking for these endpoints instead:

- Getting comments on a project:
    - [`GET /users/<username>/projects/<id>/comments`](users.md#get-usersusernameprojectsidcomments): comments on a project
    - [`GET /users/<username>/projects/<id>/comments/<id>`](users.md#get-usersusernameprojectsidcommentsid):
    - [`GET /users/<username>/projects/<id>/comments/<id>/replies`](users.md#get-usersusernameprojectsidcommentsidreplies): replies to a comment on a project
- Sending & deleting comments on a project:
    - [`POST /proxy/comments/project/<id>`](proxy.md#post-proxycommentprojectid)
    - [`DELETE /proxy/comments/project/<id>/comment/<id>`](proxy.md#post-proxycommentprojectidcommentid)
- Getting comments on a studio:
    - [`GET /studios/<id>/comments`](studios.md#get-studiosidcomments): comments on a studio
    - [`GET /studios/<id>/comments/<id>`](studios.md#get-studiosidcommentsid):
    - [`GET /studios/<id>/comments/<id>/replies`](studios.md#get-studiosidcommentsidreplies): replies to a comment on a studio
- Sending & deleting comments on a studio:
    - [`POST /proxy/comments/studio/<id>`](proxy.md#post-proxycommentsstudioid)
    - [`DELETE /proxy/comments/studio/<id>/comment/<id>`](proxy.md#post-proxycommentsstudioidcommentid)
