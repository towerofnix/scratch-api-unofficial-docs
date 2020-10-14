# `/accounts` API

The accounts API deals with authentication and username-related operations.  Unlike most of the other endpoints, all `/accounts` endpoints are made to `https://scratch.mit.edu` and not `https://api.scratch.mit.edu`.

## `GET /accounts/check_username/<username>`

Gets the status of a _username_, not to be confused with a _user_.  Returns a [username object](definitions/username_object.md).  
