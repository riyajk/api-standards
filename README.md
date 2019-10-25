
## Request & Response Examples

### API Resources

  - [GET /todo](#get all todo's)
  - [GET /todo/:todoId](#get single todo)
  - [POST /todo](#create single todo )
  - [PUT /todo/:todoId](#update single todo )
  - [DELETE /todo/:todoId](#delete single todo )

### GET /todo

Example: http://localhost:8085/todo

Response body:

    {
    "result": "success",
    "data": [
        {
            "todo_id": "f55fb830-f70c-11e9-b53d-678b84536c25",
            "title": "test todo",
            "created_at": "2019-10-25 09:51:03",
            "updated_at": "2019-10-25 15:21:03"
        },
        {
            "todo_id": "05cb8410-f70d-11e9-be1e-7b4541555989",
            "title": "test todo",
            "created_at": "2019-10-25 09:51:31",
            "updated_at": "2019-10-25 15:21:31"
        },
        {
            "todo_id": "3a67b400-f72b-11e9-b841-331448b2d116",
            "title": "third todo ",
            "created_at": "2019-10-25 13:27:44",
            "updated_at": "2019-10-25 18:57:44"
        }
    ]
}

### GET /todo/:todoId

Example: http://localhost:8085/todo/f55fb830-f70c-11e9-b53d-678b84536c25

Response body:

    {
    "result": "success",
    "data": {
        "title": "test todo",
        "created_at": "2019-10-25 09:51:03",
        "updated_at": "2019-10-25 15:21:03"
      }
    }


### POST /magazines/[id]/articles

Example: Create – POST  http://localhost:8085/todo

Request body:

    {
	   "title" : "third todo "
    }
Response body:

    {
    "result": "success",
    "data": {
        "todo_id": "3a67b400-f72b-11e9-b841-331448b2d116"
       }
   }


## Mock Responses
It is suggested that each resource accept a 'mock' parameter on the testing server. Passing this parameter should return a mock data response (bypassing the backend).

Implementing this feature early in development ensures that the API will exhibit consistent behavior, supporting a test driven development methodology.

Note: If the mock parameter is included in a request to the production environment, an error should be raised.


## JSONP

JSONP is easiest explained with an example. Here's one from [StackOverflow](http://stackoverflow.com/questions/2067472/what-is-jsonp-all-about?answertab=votes#tab-top):

> Say you're on domain abc.com, and you want to make a request to domain xyz.com. To do so, you need to cross domain boundaries, a no-no in most of browserland.

> The one item that bypasses this limitation is `<script>` tags. When you use a script tag, the domain limitation is ignored, but under normal circumstances, you can't really DO anything with the results, the script just gets evaluated.

> Enter JSONP. When you make your request to a server that is JSONP enabled, you pass a special parameter that tells the server a little bit about your page. That way, the server is able to nicely wrap up its response in a way that your page can handle.

> For example, say the server expects a parameter called "callback" to enable its JSONP capabilities. Then your request would look like:

>         http://www.xyz.com/sample.aspx?callback=mycallback

> Without JSONP, this might return some basic javascript object, like so:

>         { foo: 'bar' }

> However, with JSONP, when the server receives the "callback" parameter, it wraps up the result a little differently, returning something like this:

>         mycallback({ foo: 'bar' });

> As you can see, it will now invoke the method you specified. So, in your page, you define the callback function:

>         mycallback = function(data){
>             alert(data.foo);
>         };

http://stackoverflow.com/questions/2067472/what-is-jsonp-all-about?answertab=votes#tab-top
