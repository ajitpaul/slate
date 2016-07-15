## Time Off Requests


```http
GET /api/hrm/people/{id}/time-off-request HTTP/1.1
Accept: application/json
Authorization: Token "YOUR ACCESS TOKEN"

HTTP/1.1 200 OK
Content-Type: application/json
```

```json
[
   {
      "id":208,
      "start_date":"2016-06-22",
      "end_date":"2016-06-24",
      "time_off_policy":1,
      "status":"AP",
      "modified_on":"2016-06-22T11:57:19.317340Z",
      "act_on":"2016-06-22T11:57:19.294813Z",
      "comment":"this is a leave application",
      "modified_by":{
         "url":"/users/1",
         "image":"https://pexels.com/image.jpg",
         "id":1,
         "full_name":"Sathish Venkat",
         "email":"sathish@doublespring.com",
         "label_txt":"SV"
      },
      "days_of_leave":3.0,
      "activities":[
         {
            "id":443,
            "act_on":"2016-06-22T11:57:36.295290Z",
            "action_type":"replied",
            "action_field":"comment",
            "verb":"replied",
            "class_name":"replied",
            "organization_id":1,
            "created_on":"2016-06-22T11:57:36.295290Z",
            "is_deleted":false,
            "actor":{
               "url":"/users/1",
               "image":"https://example.com/image.jpg",
               "id":"1",
               "email":"sathish@doublespring.com",
               "full_name":"Sathish Venkat",
               "label_txt":"SV"
            },
            "action_obj":{
               "id":"208",
               "ctype":"employeetimeoff"
            },
            "source_obj":{
               "comment_detail":"hello test",
               "id":"126",
               "ctype":"hrmcomment"
            },
            "target_obj":null
         },
         {
            "id":444,
            "act_on":"2016-06-22T11:57:47.566159Z",
            "action_type":"replied",
            "action_field":"comment",
            "verb":"replied",
            "class_name":"replied",
            "organization_id":1,
            "created_on":"2016-06-22T11:57:47.566159Z",
            "is_deleted":false,
            "actor":{
               "url":"/users/1",
               "image":"https://example.com/image.jpg",
               "id":"1",
               "email":"sathish@doublespring.com",
               "full_name":"Sathish Venkat",
               "label_txt":"SV"
            },
            "action_obj":{
               "id":"208",
               "ctype":"employeetimeoff"
            },
            "source_obj":{
               "comment_detail":"hello test2",
               "id":"127",
               "ctype":"hrmcomment"
            },
            "target_obj":null
         }
      ],
      "can_approve":true,
      "created_by":{ 
         "url":"/users/274",
         "image":"https://example.com/mage.jpg",
         "id":274,
         "full_name":"Ajith Paul",
         "email":"ajith.paul@doublespring.com",
         "label_txt":"AP"
      },
      "created_on":"2016-06-22T11:57:19.296021Z",
      "policy_detail":{
         "is_expired":false,
         "id":1,
         "name":"DoubleSpring"
      },
      "entered_by":{
         "url":"/users/1",
         "image":"https://example.com/image.jpg",
         "id":1,
         "full_name":"Sathish Venkat",
         "email":"sathish@doublespring.com",
         "label_txt":"SV"
      },
      "is_entered":true
   }
]
```
API endpoint for the list of all time-off requests made by the employee.

<aside>GET /api/hrm/people/{id}/time-off-request</aside>

Attribute | Description 
--------- | ----------- 
id (*integer*)| request ID number
start_date (*string*) | timeoff starting date
end_date (*string*) | timeoff ending date
time_off_policy (*integer*)| policy ID number
status (*string*)| status of the timeoff(approved) 
modified_on (*string*)| datetime on which modified
act_on (*string*) | datetime of Action to timeoff(approve or reject)
comment (*string*)| comment on the timeoff
[modified_by] (#user-object)| details of the person who modified the timeoff request
days_of_leave (*integer*)| number of days of leave applied
[activities](#activities-object) | array of all activities of the request
can_approve (*boolean*)| possible to approve or not
[created_by] (#user-object) | Details about the creator of the request
created_on (*string*) | datetime of the creation
[policy_detail](#policy-detail) | Info on the policy (id,name ..)
[entered_by](#user-object) (object) | details about the user who entered the timeoff
is_entered (*boolean*)| is the timeoff entered (timeoff entered by admin or owner)

#### User Object
Attribute | Description 
--------- | ----------- 
url (*string*)| url of the profile
image (*string*)| url of the profile image
id (*integer*)| ID of the employee
full_name (*string*)| full name of the user
email (*string*)| email address of the user
label_txt (*string*)| label text for profile default avatar

#### Policy Detail Object
Attribute | Description 
--------- | ----------- 
is_expired (*boolean*)| is the policy expired
id (*integer*)| ID number of the policy
name (*string*)| name of the policy

#### Activities Object
Attribute | Description 
--------- | ----------- 
id (*integer*)| ID of the activity
act_on (*string*)| datetime of the activity
action_type (*string*)| type of activity
action_field (*string*)| field type of the activity
verb (*string*)| verb text for displaying of the activity
class_name (*string*)| class name for the acitivity
organization_id | Organization ID number
created_on (*string*)| datetime of the creation of the activity
is_deleted (*boolean*)| whether the activity is deleted
[actor](#user-object) | user who added the activity(comment,..)
[action_obj](#action-obj) | object to understand context of activity
[source_obj](#source-obj)_ | activity data (comment details)

#### Action Object
Attribute | Description 
--------- | ----------- 
id (*integer*)| ID of the activity
ctype (*string*)| type of the activity applying to

#### Source Object
Atribute | Description
-------- | -----------
comment_detail (*string*)| comment text
id (*integer*)| comment ID number
ctype (*string*)| type of comment



#### Returns

Returns the object with all the information about the employee time off.

### Create Time Off Request

```
Sample Request
```

```http
POST /api/hrm/people/{id}/time-off-request HTTP/1.1
Accept: application/json
Authorization: Token "YOUR ACCESS TOKEN"

HTTP/1.1 200 OK
Content-Type: application/json
```

```json 
{
   "start_date":"2016-07-12",
   "end_date":"2016-07-12",
   "time_off_policy":1,
   "comment":"test timeoff"
}
```

```
Sample Response
```

```json
{
   "id":208,
   "start_date":"2016-06-22",
   "end_date":"2016-06-24",
   "time_off_policy":1,
   "status":"AP",
   "modified_on":"2016-06-22T11:57:19.317340Z",
   "act_on":"2016-06-22T11:57:19.294813Z",
   "comment":"this is a leave application",
   "modified_by":{
      "url":"/users/1",
      "image":"https://pexels.com/image.jpg",
      "id":1,
      "full_name":"Sathish Venkat",
      "email":"sathish@doublespring.com",
      "label_txt":"SV"
   },
   "days_of_leave":3.0,
   "activities":[
      {
         "id":443,
         "act_on":"2016-06-22T11:57:36.295290Z",
         "action_type":"replied",
         "action_field":"comment",
         "verb":"replied",
         "class_name":"replied",
         "organization_id":1,
         "created_on":"2016-06-22T11:57:36.295290Z",
         "is_deleted":false,
         "actor":{
            "url":"/users/1",
            "image":"https://example.com/image.jpg",
            "id":"1",
            "email":"sathish@doublespring.com",
            "full_name":"Sathish Venkat",
            "label_txt":"SV"
         },
         "action_obj":{
            "id":"208",
            "ctype":"employeetimeoff"
         },
         "source_obj":{
            "comment_detail":"hello test",
            "id":"126",
            "ctype":"hrmcomment"
         },
         "target_obj":null
      },
      {
         "id":444,
         "act_on":"2016-06-22T11:57:47.566159Z",
         "action_type":"replied",
         "action_field":"comment",
         "verb":"replied",
         "class_name":"replied",
         "organization_id":1,
         "created_on":"2016-06-22T11:57:47.566159Z",
         "is_deleted":false,
         "actor":{
            "url":"/users/1",
            "image":"https://example.com/image.jpg",
            "id":"1",
            "email":"sathish@doublespring.com",
            "full_name":"Sathish Venkat",
            "label_txt":"SV"
         },
         "action_obj":{
            "id":"208",
            "ctype":"employeetimeoff"
         },
         "source_obj":{
            "comment_detail":"hello test2",
            "id":"127",
            "ctype":"hrmcomment"
         },
         "target_obj":null
      }
   ],
   "can_approve":true,
   "created_by":{
      "url":"/users/274",
      "image":"https://example.com/mage.jpg",
      "id":274,
      "full_name":"Ajith Paul",
      "email":"ajith.paul@doublespring.com",
      "label_txt":"AP"
   },
   "created_on":"2016-06-22T11:57:19.296021Z",
   "policy_detail":{
      "is_expired":false,
      "id":1,
      "name":"DoubleSpring"
   },
   "entered_by":{
      "url":"/users/1",
      "image":"https://example.com/image.jpg",
      "id":1,
      "full_name":"Sathish Venkat",
      "email":"sathish@doublespring.com",
      "label_txt":"SV"
   },
   "is_entered":true
}
```

<aside>POST /api/hrm/people/{id}/time-off-request</aside>

Create a new request for applying for timeoff. 

#### Returns

This call, if succeeded will return the [timeoff request](#time-off-requests) object. 

### Update Time Off Request

```
Sample Request
```

```http
PATCH /api/hrm/people/{id}/time-off-request/{id}(requestID) HTTP/1.1
Accept: application/json
Authorization: Token "YOUR ACCESS TOKEN"

HTTP/1.1 200 OK
Content-Type: application/json
```

```json
{
   "id":219,
   "start_date":"2016-07-13",
   "end_date":"2016-07-13",
   "time_off_policy":1,
   "status":"AP",
   "modified_on":"2016-07-12T09:42:45.324789Z",
   "act_on":"2016-07-12T09:42:45.301599Z",
   "comment":"test 123",
   "modified_by":{
      "url":"/users/1",
      "image":"https://twprofile.s3.amazonaws.com/users/user-77abb729-773e-41f5-9244-4a5fd337bdba-image
.jpg",
      "id":1,
      "full_name":"Sathish Venkat",
      "email":"sathish@doublespring.com",
      "label_txt":"SV"
   },
   "days_of_leave":1,
   "activities":[

   ],
   "can_approve":true,
   "created_by":{
      "url":"/users/1",
      "image":"https://twprofile.s3.amazonaws
.com/users/user-77abb729-773e-41f5-9244-4a5fd337bdba-image.jpg",
      "id":1,
      "full_name":"Sathish Venkat",
      "email":"sathish@doublespring.com",
      "label_txt":"SV"
   },
   "created_on":"2016-07-12T09:42:45.303024Z",
   "policy_detail":{
      "is_expired":false,
      "id":1,
      "name":"DoubleSpring"
   },
   "entered_by":{
      "url":"/users/1",
      "image":"https://twprofile
.s3.amazonaws.com/users/user-77abb729-773e-41f5-9244-4a5fd337bdba-image.jpg",
      "id":1,
      "full_name":"Sathish
 Venkat",
      "email":"sathish@doublespring.com",
      "label_txt":"SV"
   },
   "is_entered":true,
   "statusLabel":"Approved",
   "editMode":true
}
```
<aside>PATCH /api/hrm/people/{id}(profileID)/time-off-request/{id}(timeoffrequestID)</aside>

#### Returns

If the call succeeds, it will return an [time off request](#time-off-requests)  with two extra fields, 'statusLabel' and 'editMode' and without [activities](#activities-object) object.

Attribute | Description
-----------| -----------
statusLabel (*string*)| if the request is approved it will show "approved" 
editMode (*boolean*)| if the request has been edited, it will be true.


### Cancel Time Off Request

```
Sample Request 
```

```http
PUT /api/hrm/people/{id}/time-off-request/cancel HTTP/1.1
Accept: application/json
Authorization: Token "YOUR ACCESS TOKEN"

HTTP/1.1 200 OK
Content-Type: application/json
```

<aside>PUT /api/hrm/people/{id}/time-off-request/cancel</aside>