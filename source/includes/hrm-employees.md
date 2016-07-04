## Employees


Returns a list of all **Employees** associated with a specific **Organization**.


***HTTP Request***

<aside> 
GET   /api/hrm/people
</aside>

The list contains only employees who are **ACTIVE** `emp_status='AV'`.

<!-- Attribute | Value | Description 
--------- | ----- | -----------------------------------------
emp_type  | 'FT'  | Full Time 
          | 'IN'  | Internship
          | 'PT'  | Part Time 
          | 'CR'  | Contractor
          | null  | Uncategorized
emp_status| 'AV'  | Active/Employed
          | 'RS'  | Resigned
          | 'TR'  | Terminated
 -->

### Employee Profile
```http
GET /api/hrm/people/{id} HTTP/1.1
Accept: application/json
Authorization: Token "YOUR ACCESS TOKEN"

HTTP/1.1 200 OK
Content-Type: application/json
```
```json
{
    "id": 11,
    "first_name": "aravind",
    "last_name": "dsSpring",
    "is_owner": false,
    "label_txt": "ad",
    "is_admin": false,
    "is_hrm_admin": false,
    "is_active": true,
    "last_login": "2016-06-22T08:26:52.555870Z",
    "company": "Dsqqqqqqq",
    "full_name": "aravind dsSpring",
    "image": null,
    "job_title": "Developer",
    "organization": {
        "id": 1,
        "name": "Dsqqqqqqq",
        "domain": "doublespring",
        "logo": "http://pexels.com/img.png",
        "email": "geo.jacob@doublespring.com",
        "tenant_domain": "doublespring.com",
        "created_on": "2015-03-10",
        "default_currency": "USD",
        "default_currency_symbol": "$",
        "label_txt": null,
        "orgkey": "Dsq"
    },
    "about": null,
    "employee_id": 42,
    "emp_status": "AV",
    "emp_type": null
}
```
<aside class="warning">This api endpoint can only be viewed by a user with Administrator privileges</aside>
***HTTP Request***

<aside>GET   /api/hrm/people/{id}</aside>


Attribute | Description 
--------- | ----------- 
id (*integer*)       | Employee Profile ID 
first_name (*string*) | Employee first name 
last_name (*string*) | Employee Last name 
is_owner (*boolean*) | If user is Owner of the company 
label_txt (*string*) | Label text for profile avatar 
is_admin (*boolean*)| if Employee is Administrator
is_hrm_admin (*boolean*)| if Employee is HRM Administrator 
is_active (*boolean*)| if Employee is Active or not 
last_login (*datefield*)| last time logged in time 
company (*String*)| Organisation Name 
full_name (*String*)| Employee full name 
image (*String*)| url of the profile image 
job_title (*String*)| Job Title/Designation 
[organisation](#organisation_object) (*object*)| Company Data 
about (*String*)| Short description of the employee 
employee_id (*integer*)| Employee ID Number 
emp_status (*String*)| employee status (Active,Resigned,..) 
emp_type (*String*)| Employee Type (Fulltime,Parttime,..)

#### organisation_object 
Attribute | Description 
--------- | ----------- 
id (*integer*)| ID for the organisation
name (*string*)| Name of the organisation
domain (*string*)| domain of the organisation
logo (*string*)| url for the company logo
email (*string*)| Email address of the organisation
tenant_domain (*string*)| tenant domain address
created_on (*string*)| date on which organisation was created
default_currency (*string*)| currency used by the organisation
default_currency_symbol (*string*)| Symbol used for currency
label_txt (*string*)| label text for profile default avatar
orgkey (*string*)| organisation key

### Time-off
```http
GET /api/hrm/people/{id}/timeoff HTTP/1.1
Accept: application/json
Authorization: Token "YOUR ACCESS TOKEN"

HTTP/1.1 200 OK
Content-Type: application/json
```
```json
 {
    "used_timeoff": 0,
    "availabale_timeoff": 13.0,
    "policy_status": "AV",
    "policy_details": {
        "working_hours": {
            "id": 130,
            "created_on": "2016-06-20T12:47:22.427736Z",
            "modified_on": "2016-06-20T12:47:58.514672Z",
            "notes": null,
            "mon_start": "09:00 AM",
            "mon_end": "05:00 PM",
            "tue_start": "09:00 AM",
            "tue_end": "05:00 PM",
            "wed_start": "09:00 AM",
            "wed_end": "05:00 PM",
            "thu_start": "09:00 AM",
            "thu_end": "05:00 PM",
            "fri_start": "09:00 AM",
            "fri_end": "05:00 PM",
            "sat_start": null,
            "sat_end": null,
            "sun_start": null,
            "sun_end": null,
            "status": "P",
            "created_by": 1,
            "modified_by": 1
        },
        "total_timeoff": 20,
        "name": "DoubleSpring",
        "policy_renew_type": "YF",
        "renew_date": "2017-01-01",
        "carry_over": false,
        "id": 123,
        "timeoff_interval": 1
    },
    "policy_emp_timeoff": 20.0,
    "policy": true,
    "pending_timeoff": 7.0,
    "approved_timeoff": 0,
    "id": 123
    }
```
<aside>GET /api/hrm/people/{id}/timeoff </aside>

Attribute | Description 
--------- | ----------- 
used_timeoff (*integer*) | Number of used timeoff days
available_timeoff (*integer*) | Number of available timeoff days
policy_status (*boolean*)| Policy active or not
[policy_details](#policy_details_object) (*object*) | Details about the policy
policy_emp_timeoff (*integer*) | total number of timeoff days
policy (*boolean*) | is policy is activated for the specific employee
pending_timeoff (*integer*)| Number of timeoff days left
approved_timeoff (*integer*)| Number of timeoff days approved
id | ID of the Timeoff policy


#### policy_details_object

Attribute | Description 
--------- | ----------- 
[working_hours](#working_hours_object) (*object*)| details about the working hours
total_timeoff (*integer*)| total number of timeoff days
name (*string*) | name of the policy
policy_renew_type (*string*)| Policy renewal type- first of every year or half year
renew_date (*string*)| next renewal date
carry_over (*boolean*)| is timeoff balance can be carried over to next year
id (*integer*) | ID of the timeoff policy
timeoff_interval (*integer*) | 

#### working_hours_object

Attribute | Description 
--------- | ----------- 
id (*integer*) | id of the object
created_on (*datefield*) | working hours creation date
modified_on | date on which modified the working hours
notes | description of the working hours
mon_start (*string*)| work start time on monday
mon_end (*string*)| work end time on monday
tue_start (*string*)| work start time on tuesday
tue_end (*string*)| work end time on tuesday 
wed_start (*string*)| work start time on wednesday
wed_end (*string*)| work end time on wednesday
thu_start (*string*)| work start time on thursday
thu_end (*string*)| work end time on thursday 
fri_start (*string*)| work start time on friday
fri_end (*string*)| work end time on friday
sat_start (*string*)| work start time on saturday
sat_end (*string*)| work end time on saturday
sun_start (*string*)| work start time on sunday
sun_end (*string*)| work end time on sunday
status (*string*)|
created_by (*integer*)| ID of user who created the working hours
modified_by (*integer*)| ID of user who modified the working hours


#### Time-off-request



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
id | request ID number
start_date (*string*) | timeoff starting date
end_date (*string*) | timeoff ending date
time_off_policy | policy ID number
status (*string*)| status of the timeoff(approved) 
modified_on (*string*)| datetime on which modified
act_on (*string*) | datetime of Action to timeoff(approve or reject)
comment (*string*)| comment on the timeoff
[modified_by] (#user-object)| details of the person who modified the timeoff request
days_of_leave | number of days of leave applied
[activities](#activities-object) | array of all activities of the request
can_approve | possible to approve or not
[created_by] (#user-object) | Details about the creator of the request
created_on (*string*) | datetime of the creation
policy_detail | Info on the policy (id,name ..)
[entered_by](#user-object) (object) | details about the user who entered the timeoff
is_entered | is the timeoff entered (timeoff entered by admin or owner)

#### user object
Attribute | Description 
--------- | ----------- 
url | url of the profile
image | url of the profile image
id | ID of the employee
full_name | full name of the user
email | email address of the user
label_txt | label text for profile default avatar

#### policy_detail
Attribute | Description 
--------- | ----------- 
is_expired | is the policy expired
id | ID number of the policy
name | name of the policy

#### activities object
Attribute | Description 
--------- | ----------- 
id | ID of the activity
act_on | datetime of the activity
action_type | type of activity
action_field | field type of the activity
verb | verb text for displaying of the activity
class_name | class name for the acitivity
organization_id | Organization ID number
created_on | datetime of the creation of the activity
is_deleted | whether the activity is deleted
[actor](#user-object) | user who added the activity(comment,..)
[action_obj](#action_obj) | object to understand context of activity
[source_obj](#source_obj)_ | activity data (comment details)
[target_obj](#target_obj) | Target object

#### action_obj
Attribute | Description 
--------- | ----------- 
id | ID of the activity
ctype | type of the activity applying to

#### source _obj
Atribute | Description
-------- | -----------
comment_detail | comment text
id | comment ID number
ctype | type of comment

#### target_obj
Atribute | Description
-------- | -----------

