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

### Employee Object


```http
GET /api/hrm/people/{profile_id} HTTP/1.1
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

<aside>GET   /api/hrm/people/{profile_id}</aside>


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
[organisation](#organisation-object) (*object*)| Company Data 
about (*String*)| Short description of the employee 
employee_id (*integer*)| Employee ID Number 
emp_status (*String*)| employee status (Active,Resigned,..) 
emp_type (*String*)| Employee Type (Fulltime,Parttime,..)

#### Organisation object 
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

### Retrieve an Employee

<aside> GET api/hrm/people/{profile_id} </aside>

Retrieve an employee using the unique id of the employee.

#### Returns

[Employee](#employee-object) object

### Create Employee
Creates an employee object

```http
GET /api/users HTTP/1.1
Accept: application/json
Authorization: Token "YOUR ACCESS TOKEN"

HTTP/1.1 200 OK
Content-Type: application/json
```

```
Sample Request
```

```json
{
   "first_name":"Himesh",
   "last_name":"khan",
   "verified":true,
   "verifying":true,
   "error":false,
   "msg":"",
   "email":"himesh@doublespring.com",
   "job_title":"SW",
   "time_zone":"Europe/Kaliningrad"
}
```

```
Sample Response
```

```json
{
   "id":282,
   "first_name":"Himesh",
   "last_name":"khan",
   "email":"himesh@doublespring.com",
   "job_title":"SW",
   "last_login":null,
   "organization":1,
   "is_admin":false,
   "company":"Doublespring Media India Pvt ltd",
   "image":null,
   "first_letter":"H",
   "full_name":"Himesh khan",
   "google_token":{
      "g_refresh_token":null,
      "g_acces_token":null
   },
   "is_hrm_admin":false,
   "project_access":[

   ],
   "is_owner":false,
   "label_txt":"Hk",
   "is_active":true,
   "time_zone":"Europe/Kaliningrad"
}
```
<aside>POST   /api/users</aside>

Attribute | Description 
--------- | ----------- 
first_name (*string*)| first name of the new employee
last_name (*string*)| last name of the new employee
is_admin (*boolean*)| the new employee to have admin privileges
email (*string*)| email address of the employee
job_title (*string*)| designation of the employee
time_zone (*string*)| Time Zone of the employee

#### Returns

The employee object will be returned if the call succeeded. If any of the above attributes are invalid, the call will throw an error.

### Update Employee

```http
PATCH /api/hrm/{profile_id}/profile HTTP/1.1
Accept: application/json
Authorization: Token "YOUR ACCESS TOKEN"

HTTP/1.1 200 OK
Content-Type: application/json
```

```
Sample Request
```

```json
{
   "id":224,
   "user":{
      "id":274,
      "first_name":"Ajith",
      "last_name":"Paul M",
      "is_active":true,
      "job_title":"Developer",
      "time_zone":"Asia/Kolkata",
      "about":null,
      "full_name":"Ajith Paul",
      "label_txt":"AP",
      "email":"ajith.paul@doublespring.com",
      "is_owner":false,
      "is_admin":false,
      "is_crm_admin":false,
      "is_hrm_admin":true,
      "report_to":11,
      "owner":{
         "url":"/users/1",
         "image":"https://pixels.com/e.jpg",
         "id":1,
         "full_name":"Sathish Venkat",
         "email":"sathish@doublespring.com",
         "label_txt":"SV"
      },
      "account_status":"AV"
   },
   "emp_type":"FT",
   "start_date":"2016-05-13",
   "accuracy":20,
   "emp_status":"AV",
   "last_date":null,
   "job_description":null,
   "policy":false,
   "emp_id":"do10048"
}
```

```
Sample Response
```

```json
{
   "id":224,
   "user":{
      "id":274,
      "first_name":"Ajith",
      "image":"https://pixels.com/image.jpg",
      "last_name":"Paul M",
      "is_active":true,
      "job_title":"Developer",
      "time_zone":"Asia/Kolkata",
      "about":null,
      "full_name":"Ajith Paul M",
      "label_txt":"AP",
      "email":"ajith.paul@doublespring.com",
      "is_owner":false,
      "is_admin":false,
      "is_crm_admin":false,
      "is_hrm_admin":true,
      "report_to":{
         "url":"/users/11",
         "image":"http://pixels.com/image.jpg",
         "id":11,
         "full_name":"Aravind dsSpring",
         "email":"aravind@doublespring.com",
         "label_txt":"AD"
      },
      "owner":{
         "url":"/users/1",
         "image":"https://pixels.com/image.jpg",
         "id":1,
         "full_name":"Sathish Venkat",
         "email":"sathish@doublespring.com",
         "label_txt":"SV"
      },
      "account_status":"AV"
   },
   "emp_type":"FT",
   "start_date":"2016-05-13",
   "accuracy":20,
   "emp_status":"AV",
   "last_date":null,
   "job_description":null,
   "policy":false,
   "emp_id":"do10048"
}
```
<aside>PATCH   /api/hrm/{profile_id}/profile </aside>

Attribute | Description 
--------- | ----------- 
id (*integer*)| ID for the employee
emp_id (*integer*)|  employee ID card number 
emp_status (*String*)| employee status (Active,Resigned,..) 
emp_type (*String*)| Employee Type (Fulltime,Parttime,..)
policy (*boolean*) | is policy is activated for the specific employee
start_date (*string*) | joining date of the employee
last_date (*string*) | date on which employee left the company
accuracy (*integer*)| the value for displaying profile completion
job_description (*string*)| short description of employee's job.
[user](#user-object) (*object*) | user data

#### user object
Attribute | Description 
--------- | ----------- 
id (*integer*) | Employee Profile ID 
about (*string*) | short description about the employee (comes under Bio)
email (*string*) | email address of the employee
account_status (*string*)| current status of the account (Active, Suspended, Terminated ..)
first_name (*string*) | Employee first name 
last_name (*string*) | Employee Last name 
is_admin (*boolean*)| Employee is Administrator or not
is_hrm_admin (*boolean*)| Employee is HRM Administrator or not
is_active (*boolean*)| Employee is Active or not 
is_crm_admin (*boolean*)| Employee is CRM admin or not
is_owner (*boolean*)| user is owner of the company 
label_txt (*string*)| Label text for profile avatar 
job_title (*String*)| Job Title/Designation 
[owner](#user-object) (*object*)| owner info

#### Returns

If the call succeeds, it will return the employee object. Else it will return error for invalid attribute values.


