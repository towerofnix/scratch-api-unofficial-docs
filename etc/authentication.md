# Authentication

Some API endpoints require you to authenticate that you are a specific person; for example, typically accessing private information (like the content of notifications) requires authentication.

Authentication is done by giving a token to the endpoint URL of the API you're using. This token can be accessed from the URL https://scratch.mit.edu/session/ as long as a `X-Requested-With` header is present with a value of `XMLHttpRequest` (note this is on scratch.mit.edu, not the API site). The easiest way to do this is to go to the Scratch home page in a browser, open developer tools, and locate this request in the "Network" tab. The token is given by appending the query `x-token=<token>`; for example `https://api.scratch.mit.edu/users/<username>/messages?x-token=<token>`.
