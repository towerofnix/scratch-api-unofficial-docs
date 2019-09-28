# `cdn.assets. /internalapi/asset/` API

The assets API returns costumes, sounds and other assets that are used in projects.

### `GET cdn.assets.scratch.mit.edu/internalapi/asset/<asset MD5 file name>/get/`

Retrieves the asset with the corresponding file name. Every asset in every project has a unique MD5 ID that can be used to reference or access it. 

The `<asset MD5 file name>` consists of the MD5 ID, and then the file format e.g. `106798711d0220a08cca12e750468e2b.png`
