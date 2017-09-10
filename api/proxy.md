# `/proxy/` API

The proxy API contains many utilities, generally returning content likely to be modified frequently.

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

Each item in that array is a project, and follows this format:

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

## `/proxy/users`

### `GET /proxy/users/<name>/activity`

Gets activity events that appear in the user's activity feed. Returns an array of [activity event objects](definitions/activity_event_object.md).

### `GET /proxy/users/<name>/activity/count`

Gets the number of messages the user has, in this format:

```
{
    "msg_count": /* Messages the user currently has */
}
```

### `GET /proxy/users/<id>/featured`

Gets projects on the homepage that are featured to user personally. Returns an object of which each of its properties' values are arrays of project objects:

```
{
    "custom_projects_by_following": /* Projeted by users the user is following */
    "custom_projects_loved_by_following": /* Projects loved by users the user is following */
}
```
