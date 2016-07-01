---
title: API Reference

language_tabs:
  - HTTP
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the TeamwaveAPI! You can use our API to access Teamwave API endpoints, which can get information on various PM, CRM, and HRMS in our database.

We have language bindings in Python and javascript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/tripit/slate). Feel free to edit it and use it as a base for your own API's documentation.

# PM


# CRM


## Deals

## Mail

## Activities

## Contacts

## Progress

## Statistics

# HRMS

## Time-off Policy
```http
GET /api/hrm/organisation HTTP/1.1
Accept: application/json
Authorization: Token "YOUR ACCESS TOKEN"

HTTP/1.1 200 OK
Content-Type: application/json
```
```json
{
   "name":"Doublespring Media India Pvt ltd",
   "domain":"doublespring",
   "time_zone":"Asia/Kolkata",
   "default_currency":"USD",
   "about":"<div><!--block--><strong>DoubleSpring</strong>&nbsp;is a new&nbsp;<strong>media</strong
>&nbsp;company, specialized in web development. We work to our strengths, and we're strong in many areas
 of the Web from operations&nbsp;</div>",
   "logo":"https://twprofile.s3.amazonaws.com/logos/organization-662f7425-f900-48e7-a265-e4083ce30ae0-image
.jpg",
   "website":"www.rediff.com",
   "location":"Bangalore",
   "markets":null,
   "privacy_mode":false,
   "linkedin":"www.linkedin.com",
   "facebook":"www.facebook.com",
   "twitter":"www.twitter.com",
   "googleplus":"www.google
.com",
   "blog":"blog.doublespring.com"
}
```

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
<aside class="warning">This api endpoint can only viewed by user with Administrator privileges</aside>
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




## Tasks

## Automatic Check-ins

## You


# Organisation


#policy_details

#### timeoffpolicy
<!-- 
# Authentication



> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Kittens

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

 -->