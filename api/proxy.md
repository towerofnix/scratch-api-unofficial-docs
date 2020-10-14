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

## `GET /proxy/users`

All of the `/proxy/users` endpoints have been replaced by new endpoints in [/users](users.md).  
