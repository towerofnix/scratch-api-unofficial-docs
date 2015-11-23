# Scratch API Unofficial Docs
Unoficial documentation for the Scratch API

> `/`
>
> Static page with the following:
>
>     {
>         "website": "scratch.mit.edu"
>         "api": "api.scratch.mit.edu"
>         "help": "help@scratch.mit.edu"
>     }
>
>> `/users`
>>
>>> `/users/<username>`
>>>
>>> Gets metadata about user `<user>`. Returns the following:
>>>
>>>     {
>>>         "id": /* User ID */
>>>         "username": /* Username */
>>>         "history": {
>>>             "joined": /* Date joined */
>>>             "login": /* Last login date? */
>>>         }
>>>         "profile": {
>>>             "id": /* Profile ID? */
>>>             "avatar": /* Part of a path to avatar? */
>>>             "status": /* What I'm working on */
>>>             "bio": /* About me */
>>>         }
>>>     }
>>
>> `/projects/`
>>>
>>> `/projects/count/`
>>>
>>>> `/projects/count/all`
>>>>
>>>> Gets the total number of projects created. Returns the following:
>>>>
>>>>     {
>>>>         "count": /* Total project count */
>>>>     }
