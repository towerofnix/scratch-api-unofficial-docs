# `projects.scratch.mit.edu` unofficial documentation

The domain https://projects.scratch.mit.edu is used for downloading, uploading, and updating Scratch projects.

As a rule of thumb, the official source code file [scratch-storage/src/WebHelper.js](https://github.com/LLK/scratch-storage/blob/develop/src/WebHelper.js) can be used as a reference in accessing the projects API.

### Download a project

A project can be downloaded by accessing `https://projects.scratch.mit.edu/<id>`, where `<id>` is the ID of the project. This will return a binary file which is an SB, SB2, or SB3, according to the version the project was shared/last updated in.

The URL `https://projects.scratch.mit.edu/internalapi/project/<id>/get/` also works.

### Upload a project

A binary project file can be uploaded to the Scratch website by sending a `POST` request to the URL `https://projects.scratch.mit.edu/`, where the body of the request is the Scratch binary file.
