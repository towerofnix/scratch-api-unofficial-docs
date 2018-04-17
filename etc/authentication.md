# Authentication

Some API endpoints require you to authenticate that you are a specific person; for example, typically accessing private information (like the content of notifications) requires authentication.

Authentication is done by giving a token to the endpoint URL of the API you're using. This token can be accessed from the URL https://scratch.mit.edu/session/ (note this is on scratch.mit.edu, not the API site) as long as an `X-Requested-With` header is present with a value of `XMLHttpRequest`. The easiest way to fetch the token manually is to go to the Scratch home page in a browser, open developer tools, and locate the request to `/session` in the "Network" tab. The token is given to API endpoints by appending the query `x-token=<token>`; for example `https://api.scratch.mit.edu/users/<username>/messages?x-token=<token>`.
