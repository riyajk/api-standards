
## Request & Response Examples

### API Resources

  - [GET /todo](#get-todo)
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


### POST /todo

Example: Create todo :  http://localhost:8085/todo

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
  ### PUT /todo

Example: Update todo :  http://localhost:8085/todo/f55fb830-f70c-11e9-b53d-678b84536c25

Response body:

    {"result":"success"}


  ### DELETE /todo

Example: delete todo :  http://localhost:8085/todo/f55fb830-f70c-11e9-b53d-678b84536c25

Response body:

    {
      "result": "success"
    }
  
