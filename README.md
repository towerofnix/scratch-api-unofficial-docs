*(Quick links to: [/api/ API reference](https://towerofnix.github.io/https://towerofnix.github.io/scratch-api-unofficial-docs/api/), [/etc/ additional documentation](https://towerofnix.github.io/scratch-api-unofficial-docs/etc/).)*

Welcome to the Scratch API Unofficial Documentation! This wiki is an organized place to put all the information the community has gathered about the new Scratch API.

## Things for you to do:

**If you have a bunch of information about an API:** Feel free to fork, write documentation, and make a pull request to here!

**If you know of an API but not a lot about it:** A good idea would be to [make an issue](https://github.com/towerofnix/scratch-api-unofficial-docs/issues/new) about it. Please give us sources of where you got the information about it, and/or any information you have about it.

**If you're just looking around:** Keep on reading to learn a little bit more about the APIs! You can find the documentation in [/api/](api/) and you can find other API-related things in [/etc/](etc/) (or use the links at the top of this page).

## What is the Scratch API?

The Scratch API is an online API for using information from [Scratch](https://scratch.mit.edu/). It's steadily being developed by the [Scratch Team](https://scratch.mit.edu/info/credits/), and is part of their [upgrade](https://scratch.mit.edu/discuss/topic/163894/) to the Scratch site. There used to be an old API that was fairly well documented, but [it was deprecated](https://scratch.mit.edu/discuss/post/1552554/) on October 26<sup>th</sup> 2015, and with the new, fresh API coming with the upgrade to the site we (the folk on [the Advanced Topics](http://scratch.mit.edu/discuss/31/) and [everyone who's contributed to this repo!](https://github.com/towerofnix/scratch-api-unofficial-docs/graphs/contributors)) decided to write more up-to-date documentation.

## How can you use the Scratch API?

Simple enough - say you want to get the number of projects currently made. You'd just send a `GET` request to the API page `/projects/count/all`. This can be as simple as opening the API page in your browser: [`https://api.scratch.mit.edu/projects/count/all`](https://api.scratch.mit.edu/projects/count/all).

Many of the things on the API are going to be more useful to software developers, but it can be fun for anybody just to look around and experiment, too.

The output of a request is generally (supposed to be) a JSON object. Most programming languages have functions such as [`JSON.parse`](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse) to use the data.

You can also use a built-by-the-community programming library like [scratch-api (Node.js)](https://www.npmjs.com/package/scratch-api) or [scratchapi (Python)](https://github.com/PolyEdge/scratchapi) to connect to the API.
