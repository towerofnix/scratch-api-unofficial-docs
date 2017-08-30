# Limits and Offsets

Many API endpoints only return the first twenty results per request, when often more are wanted. The paramater `limit` can be changed to a number less than or equal to 20 to decrease the number of users returned in the array, and the paramater `offset` can be set to offset the following selection - for example, `/users/foobar/following?offset=3&limit=2` will get the fourth and fifth most recent users the user foobar is following.
