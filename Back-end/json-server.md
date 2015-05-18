# JSON Server

* [https://github.com/typicode/json-server](https://github.com/typicode/json-server)

```
# Insert this block
vi db.json
{
  "posts": [
    { "id": 1, "title": "json-server", "author": "typicode" }
  ],
  "comments": [
    { "id": 1, "body": "some comment", "postId": 1 }
  ]
}

# Install & Run Server
npm install -g json-server
json-server --watch db.json
```