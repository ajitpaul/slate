## Activities 

### Activity Object 

```json
 {
      "id":409,
      "act_type":{
         "icon":"icon-send",
         "id":463,
         "title":"Email"
      },
      "assigned_to":{
         "url":"/users/272",
         "image":"",
         "id":272,
         "full_name":"Rajdeep Sharma",
         "email":"rajdeep@doublespring.com",
         "label_txt":"RS"
      },
      "person":{
         "phone":null,
         "name":"testContsct",
         "full_name":"testContsct",
         "image":null,
         "job_title":null,
         "id":15435,
         "ctype":"person",
         "email":null
      },
      "company":{
         "domain":null,
         "name":"Doublespring",
         "image":null,
         "ctype":"company",
         "phone":"96633",
         "address":"15/1",
         "id":8452
      },
      "deal":{
         "id":2757,
         "ctype":"deal",
         "dealname":"Segment Deal"
      },
      "activity_due_on":"2016-07-13T08:15:00",
      "due_time":"08:15 AM",
      "act_on":"2016-07-13T08:15:00",
      "add_next":false,
      "title":"Email",
      "note":"Please fill in your Folio No., Name, PAN & Bank Account
 		details in Section 2 & 3, and then proceed to Section 5",
      "due_date":"2016-07-13",
      "duration":"00:30",
      "is_completed":false,
      "completed_on":null,
      "is_trashed":false
   }
```

<aside>GET api/crm/activities/{activity_id}</aside>

Attribute | Description
----------| -----------
id (*integer*)| Activity ID
[act_type](#act_type-object) | activity type
[assigned_to](#user-object) | list of people assigned to the activity
[person](#person-object) | contact person details
[company](#company-object) | organisation details
[deal](#deals-object) | deals info
activity_due_on | due date-time for the activity
due_time | due time of the activity
due_date | due date of the activity
add_next | if the activity added next
title | title of the activity
note | description of the activity
duration | duration of the activity
is_completed | is the activity completed
completed_on | date of complete
is_trashed | is the activity deleted

#### Activity Type Object(act_type)

Attribute | Description 
----------| -----------
icon | icon name for the activity type
id | ID of the activity type
title | title of the activity type

#### Person Object

Attribute | Description
----------| -----------
phone | phone number of the contact person
name | name of the contact person
full_name | full name of the contact person
image | image url for the contact
job_title | Desgination
id | ID of the contact person
ctype | content type ('person')
email | email address

#### Company Object

Attribute | Description
----------| -----------
domain | domain name for the company
name | name of the company
image | image url for the company logo
ctype | content type ('company')
phone | phone number
address | Company address
id | Company ID

#### Deals object 

Attribute | Description
----------| -----------
id | ID of the deal
ctype | content type ('deal')
dealname | Deal name

### Create Activity 

```http
POST api/crm/activities HTTP/1.1
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
   "due_date":"2016-07-18",
   "title":"Email",
   "act_type":{
      "id":463,
      "title":"Email",
      "icon":"icon-send",
      "is_trashed":false
   },
   "assigned_to":{
      "id":1,
      "full_name":"Sathish Venkat"
   },
   "person":1,
   "company":10141,
   "deal":3376,
   "note":"This is a test deadline activity",
   "due_time":"08:00 AM",
   "duration":"01:00"
}
```

``` 
Sample Response
```

```json
{
   "id":424,
   "act_type":{
      "icon":"icon-send",
      "id":463,
      "title":"Email"
   },
   "assigned_to":{
      "url":"/users/1",
      "image":"https://twprofile.s3.amazonaws.com/users/user-8011f79c-007c-4943-a968-1d13dd13b1d9-image.jpg",
      "id":1,
      "full_name":"Sathish Venkat",
      "email":"sathish@doublespring.com",
      "label_txt":"SV"
   },
   "person":{
      "phone":"8884546564",
      "name":"Sachin N",
      "full_name":"Sachin N",
      "image":null,
      "job_title":"Designer",
      "id":1,
      "ctype":"person",
      "email":"sachin@doublespring.com"
   },
   "company":{
      "domain":"www.google.com",
      "name":"DoubleSpring
 Media India pvt Ltd",
      "image":null,
      "ctype":"company",
      "phone":"080-41250414",
      "address":"Frazer Town",
      "id":10141
   },
   "deal":{
      "id":3376,
      "ctype":"deal",
      "dealname":"Test Deal"
   },
   "activity_due_on":"2016-07-18T08:00
:00",
   "due_time":"08:00 AM",
   "act_on":"2016-07-18T08:00:00",
   "add_next":false,
   "title":"Email",
   "note":"This
 is a test deadline activity",
   "due_date":"2016-07-18",
   "duration":"01:00",
   "is_completed":false,
   "completed_on":null,
   "is_trashed":false
}
```

<aside>POST api/crm/activities</aside>

#### Returns

If the call succeeds, it will return the activity object with [given data](#activity-object).

### Update Activity

```http
PUT api/crm/activities/{activity_id} HTTP/1.1
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
   "id":389,
   "act_type":{
      "icon":"icon-send",
      "id":463,
      "title":"Email"
   },
   "assigned_to":{
      "id":221,
      "full_name":"Prasad Vara"
   },
   "person":17561,
   "company":10121,
   "deal":3207,
   "activity_due_on":"2016-05-27",
   "due_time":null,
   "act_on":"2016-05-27T00:00:00",
   "add_next":false,
   "title":"Email",
   "note":null,
   "due_date":"2016-05-28",
   "duration":null,
   "is_completed":false,
   "completed_on":null,
   "is_trashed":false
}
```

```
Sample Response
```

```json
{
   "id":389,
   "act_type":{
      "icon":"icon-send",
      "id":463,
      "title":"Email"
   },
   "assigned_to":{
      "url":"/users/221",
      "image":"",
      "id":221,
      "full_name":"Prasad Vara",
      "email":"prasad@doublespring.com",
      "label_txt":"PV"
   },
   "person":{
      "phone":"9663078168",
      "name":"Akenani Nagarujina",
      "full_name":"Akenani Nagarujina",
      "image":null,
      "job_title":null,
      "id":17561,
      "ctype":"person",
      "email":"contactprasad1983@gmail.com"
   },
   "company":{
      "domain":null,
      "name":"Operi productions",
      "image":null,
      "ctype":"company",
      "phone":null,
      "address":null,
      "id":10121
   },
   "deal":{
      "id":3207,
      "ctype":"deal",
      "dealname":"Operi"
   },
   "activity_due_on":"2016-05-28",
   "due_time":null,
   "act_on":"2016-05-28T00
:00:00",
   "add_next":false,
   "title":"Email",
   "note":null,
   "due_date":"2016-05-28",
   "duration":null,
   "is_completed":false,
   "completed_on":null,
   "is_trashed":false
}
```
<aside>PUT api/crm/activities/{activity_id}</aside>

#### Returns

If the call succeeds, it will return the [activity object](#activity-object) with  updated data.

### Delete Activity

```http
DELETE api/crm/activities/{activity_id} HTTP/1.1
Accept: application/json
Authorization: Token "YOUR ACCESS TOKEN"

HTTP/1.1 200 OK
Content-Type: application/json
```

<aside>DELETE api/crm/activities/{activity_id} </aside>