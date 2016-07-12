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