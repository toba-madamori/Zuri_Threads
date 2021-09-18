# Zuri Chat Pluggin Endpoints( Channel Threads)

#### Made by team Coelho
Developer Contact: team-coelho@zuri.chat

Getting started with the thread endpoint is easy, all you need to do is to first get authenticated and then arrange your url parameters and lastly your request payload in proper order as shown below. You can then make the various allowed requests and your request should be successful.

Contact Support: Email:team-coelho@zuri.chat
### Authentication:
Method : Basic Authentication;
Username: <String>
Password: <pa$$word>

Note that this authorization method will be used for every request in this collection. You can override this by specifying one in the request.
#### Base Url:
```sh
[ Base URL: channels.zuri.chat/api ]
```
#### Creating a Channel Message Thread
Note: Starred request variables are required else 4xx errors will be raised.
Request Method: Post
Request Url:
```sh
{{baseUrl}}/v1/:org_id/messages/:channelmessage_id/threads/?channel_id=<string>
```
#### Url Parameters:
Channelmessage_id= <string>
Channel_id= <string>
Org_id= <string>

## Request Headers
Content-Type: application/json
Authorization: Basic Auth credentials

## Request Body
Format type : raw(json)
```sh
{
    "user_id*:"string"
    "content": "string",
    "files*":[
        "string"
    ]
    
}
```

##### Response for a successful request:
Status Code: 201 Created
```sh
{
    "_id": "string",
    "user_id": "string",
    "channelmessage_id": "string",
    "channel_id": "string",
    "content": "message string"
    "files": [
        "file string"
    ],
    "has_files": "yes"
    "emojis": [
        "string(emoji)"
    ],
    "edited": false,
    "timestamp": "2001-12-27T17:28:25.261Z"
}
```

#### Response for an error:
Status Code: 404 Not Found
```sh
{
 "status": "404",
 "message": "there was an unexpected error",
}
```

#### Reading a Channel Message Thread
Request Method: Get
Request Url:
```sh
{{baseUrl}}/v1/:org_id/messages/:channelmessage_id/threads/
```
#### Url Parameters:
Channelmessage_id= <string>
Org_id= <string>

## Request Headers
Content-Type: application/json
Authorization: Basic Auth credentials

##### Response for a successful request:
Status Code: 200 Ok
```sh
{
    "_id": "string",
    "user_id": "string",
    "channelmessage_id": "string",
    "channel_id": "string",
    "content": "string",
    "files": [
      "string"
    ],
    "has_files": "yes",
    "emojis": [
      "string"
    ],
    "edited": true,
    "timestamp": "2021-09-18T11:21:07.952Z"
  }
```

#### Response for an error:
Status Code: 404 Not Found
```sh
{
  "error": {
    "message": "string",
    "status": 404
  }
}
```

#### Updating A Channel Message Thread
Request Method: Put
Request Url:
```sh
{{baseUrl}}/v1/:org_id/threads/:thread_id/?user_id=<string>&channel_id=<string>
```
#### Url Parameters:
User_id= <string>
Channel_id= <string>
Org_id= <string>
Thread_id= <string>


## Request Headers
Content-Type: application/json
Authorization: Basic Auth credentials

## Request Body
Format type : raw(json)
```sh
{
  "content": "string"
}
```

##### Response for a successful request:
Status Code: 200 Ok
```sh
{
  "_id": "string",
  "user_id": "string",
  "channelmessage_id": "string",
  "channel_id": "string",
  "content": "string",
  "files": [
    "string"
  ],
  "has_files": "yes",
  "emojis": [
    "string"
  ],
  "edited": true,
  "timestamp": "2021-09-18T11:28:56.827Z"
}
```

#### Response for an error:
Status Code: 404 Not Found
```sh
{
  "error": {
    "message": "string",
    "status": 404
  }
}
```

#### Deleting A Channel Thread
Request Method: Delete
Request Url:
```sh
{{baseUrl}}/v1/:org_id/threads/:thread_id/?user_id=<string>&channel_id=<string>
```
#### Url Parameters:
User_id= <string>
Channel_id= <string>
Org_id= <string>
Thread_id= <string>


## Request Headers
Content-Type: application/json
Authorization: Basic Auth credentials

##### Response for a successful request:
Status Code: 204 No Content

 ##### Things to note:
- There are parameters in the url, everything required is going to part of the payload.
- Only valid id's and payload's will be accepted. If not provided 4xx status errors will be raised.
- If a 5xx error is raised then the problem is from the server

#### List of Most Likely 4xx Errors
- 400 Bad Request
- 401 Unauthorized
- 403 Forbidden
- 404 Not Found
#### List of Most Likely 5xx Errors
- 500 Internal Server Error
- 502 Bad Gateway
- 503 Service Unavailable


