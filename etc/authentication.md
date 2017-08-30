# Authentication

Some API endpoints require you to authenticate that you are a specific person; for example, typically accessing private information (like the content of notifications) requires authentication.

Authentication is done by giving a token to the endpoint URL of the API you're using. This token can be gotten from the URL https://scratch.mit.edu/session/ (note this is on scratch.mit.edu, not the API site). The token is given by appending the query `x-token=<token>`; for example `https://api.scratch.mit.edu/users/<username>/messages?x-token=<token>`.
