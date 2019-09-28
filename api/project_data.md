# `projects.` and `assets.` APIs

These retrieve all of the data and files needed for a scratch project/file.

### `GET cdn.projects.scratch.mit.edu/<project id>/`

Retrieves the projects JSON data, which is where all of the code for a scratch project is stored.

### `GET cdn.assets.scratch.mit.edu/internalapi/asset/<md5 file>/get/`

Retrieves the asset with the given file name. An asset is a costume, sound or other file used in a project.  Each asset in each project has a unique md5 id, which is used for referencing and retrieving it. 

The `<md5 file>` is a combination of this `md5 id`, and the file's format. For example: `106798711d0220a08cca12e750468e2b.png`
