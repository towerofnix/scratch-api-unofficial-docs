# Authentication

Some API endpoints require you to authenticate that you are a specific person (for example, when you're trying to access private information, like notifications).

## From devtools
Authentication is done by giving a token to the endpoint URL of the API you're using. This token can be accessed from the URL https://scratch.mit.edu/session/ (note this is on scratch.mit.edu, not the API site) as long as an `X-Requested-With` header is present with a value of `XMLHttpRequest`. The easiest way to fetch the token manually is to go to the Scratch home page in a browser, open developer tools, and locate the request to `/session` in the "Network" tab. The token is given to API endpoints by appending the query `x-token=<token>`; for example `https://api.scratch.mit.edu/users/<username>/messages?x-token=<token>`.

## With username and password

> ⚠️ Logging in with a username and password in public applications is _highly_ discouraged since it puts the responsibility on you to prevent man-in-the-middle attacks.  Asking for a username and password may also make your app seem suspicious for phishing.

To log in with a username and password, you need to make a `POST` request to `https://scratch.mit.edu/accounts/login/` and a JSON body containing the `username` and `password` as well as a boolean called [`useMessages`](#what-is-usemessages).  The `Referer` and `Origin` headers must be set to `https://scratch.mit.edu`, and a cookie must be passed with containing a [CSRF token](https://en.wikipedia.org/wiki/Cross-site_request_forgery) and a language.  This can be a little confusing - below is an example request made with [`node-fetch`](https://npmjs.com/node-fetch) (a common request library for Node.js):

```javascript
fetch("https://scratch.mit.edu/accounts/login/", {
      credentials: "include", // this ensures that cookies are sent
      method: "POST",
      headers: {
        "Cookie": "scratchcsrftoken=a; scratchlanguage=en",
        //                         ^ this can be anything, as long as it matches the X-CSRFToken header below
        "Origin": "https://scratch.mit.edu",
        "Referer": "https://scratch.mit.edu/",
        "X-CSRFToken": "a",
        "X-Requested-With": "XMLHttpRequest",
        "Content-Type": "application/json",
      },
      body: '{
        "useMessages": true,
        "username": "myCoolUsername",
        "password": "myPassword",
      }',
    });
```

The various implementations of this request will vary based on your chosen language and request library.  However, note that credentials (cookies) must be included and you must make the request from a server or native app due to [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) restrictions.

### What is `useMessages`?
We don't know for sure what `useMessages` is for since the login API is part of the older [scratchr2](https://scratch.mit.edu/discuss/topic/6865/) version of the Scratch website which is not open-source.  However, it's been seen that [requests can fail](https://ocular.jeffalo.net/post/4924768) if the request body doesn't contain it.  
