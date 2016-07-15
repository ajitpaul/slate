## Tasks

Lists all the tasks assigned to the employee

### Task Object

```http
GET api/hrm/people/{id}/tasks HTTP/1.1
Accept: application/json
Authorization: Token "YOUR ACCESS TOKEN"

HTTP/1.1 200 OK
Content-Type: application/json
```

```json
{
  "id":141,
  "title":"Task to aravind",
  "description":"Finish it",
  "created_on":"2016-01-14T12:21:47.924548Z",
  "due_date":null,
  "assigned_to":{
     "user_id":11,
     "id":32,
     "full_name":"Aravind dsSpring"
  },
  "related_to":null,
  "task_type":"G",
  "timeoff_id":"None",
  "can_edit":true,
  "created_by":{
     "url":"/users/1",
     "image":"https://twprofile.s3
.amazonaws.com/users/user-77abb729-773e-41f5-9244-4a5fd337bdba-image.jpg",
     "id":1,
     "full_name":"Sathish
Venkat",
     "email":"sathish@doublespring.com",
     "label_txt":"SV"
  },
  "task_url":"tasks/11",
  "default_policy_id":null
}
```

<aside>GET api/hrm/people/{id}/tasks </aside>

Attribute   | Description
--------- | ------------
id	| ID of the task
title (*string*)| task title
description (*string*)| Description of the task to be completed
created_on (*string*)| creation date
due_date (*string*)| Date before task needs to be completed
[assigned_to](#asigned_to-object) | task assigned to employee details
task_type (*string*)| Type of task ('G' for general task,..)
timeoff_id | timeoff id for timeoff task
can_edit | if task can be edited
[created_by](#created_by-object) | info about the creator of the task
task_url (*string*)| url of the task
default_policy_id (*integer*)| default policy ID

### Create Task

```
Sample Request
```

```http
POST api/hrm/people/{id}/tasks HTTP/1.1
Accept: application/json
Authorization: Token "YOUR ACCESS TOKEN"

HTTP/1.1 200 OK
Content-Type: application/json
```

```json 
{
   "title":"Test task",
   "assigned_to":224,
   "due_date":"2016-07-01",
   "description":"This is a test task."
}
```

```
Sample Response
```

```json
{
   "id":297,
   "title":"Test task",
   "description":"This is a test task.",
   "created_on":"2016-07-13T06:11:24.679141Z",
   "due_date":"2016-07-01",
   "assigned_to":{
      "user_id":274,
      "id":224,
      "full_name":"Ajith Paul M"
   },
   "related_to":null,
   "task_type":"G",
   "timeoff_id":"None",
   "can_edit":true,
   "created_by":{
      "url":"/users/1",
      "image":"https://twprofile.s3.amazonaws.com/image.jpg",
      "id":1,
      "full_name":"Sathish Venkat",
      "email":"sathish@doublespring.com",
      "label_txt":"SV"
   },
   "task_url":"tasks/274",
   "default_policy_id":null
}
```

<aside>POST api/hrm/people/{id}/tasks</aside>

### Update Task

```
Sample Request
```

```http
PUT api/hrm/people/{profile_id}/tasks/{task_id} HTTP/1.1
Accept: application/json
Authorization: Token "YOUR ACCESS TOKEN"

HTTP/1.1 200 OK
Content-Type: application/json
```

```json
{
   "id":297,
   "title":"Test tasks",
   "description":"This is a test task.",
   "created_on":"2016-07-13T06:11:24.679141Z",
   "due_date":"2016-07-06",
   "assigned_to":8,
   "related_to":null,
   "task_type":"G",
   "timeoff_id":"None",
   "can_edit":true,
   "created_by":{
      "url":"/users/1",
      "image":"https://twprofile.s3.amazonaws.com/image.jpg",
      "id":1,
      "full_name":"Sathish Venkat",
      "email":"sathish@doublespring.com",
      "label_txt":"SV"
   },
   "task_url":"tasks/274",
   "default_policy_id":null
}
```

```
Sample Response
```

```json
{
   "id":297,
   "title":"Test tasks",
   "description":"This is a test task.",
   "created_on":"2016-07-13T06:11:24.679141Z",
   "due_date":"2016-07-06",
   "assigned_to":{
      "user_id":96,
      "id":8,
      "full_name":"alok vats"
   },
   "related_to":null,
   "task_type":"G",
   "timeoff_id":"None",
   "can_edit":true,
   "created_by":{
      "url":"/users/1",
      "image":"https://twprofile.s3.amazonaws.com/image.jpg",
      "id":1,
      "full_name":"Sathish Venkat",
      "email":"sathish@doublespring.com",
      "label_txt":"SV"
   },
   "task_url":"tasks/96",
   "default_policy_id":null
}
```
<aside>POST api/hrm/people/{id}/tasks</aside>


#### Returns

If the call succeeds, it will return the task object. If any of the fields have invalid values, it will throw an error.


### Delete Task

```
Sample Request
```

```http
DELETE api/hrm/people/{profile_id}/tasks/{task_id} HTTP/1.1
Accept: application/json
Authorization: Token "YOUR ACCESS TOKEN"

HTTP/1.1 200 OK
Content-Type: application/json
```
<aside>DELETE api/hrm/people/{profile_id}/tasks/{task_id}</aside>

