# `/accounts` API

The accounts API deals with authentication and username-related operations.

## `GET /accounts/checkusername/<username>`

Gets the status of a _username_, not to be confused with a _user_.  Returns:
 
```json
{
  "username": String,
  "msg": String
}
```

The value of the `msg` property can be "username exists", "valid username", or "bad username".