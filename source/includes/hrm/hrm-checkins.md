## Automatic Check-ins

### Automatic Check-ins Object 

```
Samle Object
```

```json
{
   "id":34,
   "question":"This  is a checkin question",
   "is_active":true,
   "is_public":true,
   "created_by":1,
   "schedule_day":"EFR",
   "schedule_time":"ED",
   "people_count":2,
   "assigned_to":[
      {
         "id":30,
         "emp_type":null,
         "start_date":"2015-10-26",
         "job_description":null,
         "emp_status":"AV",
         "job_title":"dev",
         "user":{
            "url":"/users/201",
            "image":"",
            "id":201,
            "full_name":"Geo Jacob",
            "email":"geo.jacob11@doublespring.com",
            "label_txt":"GJ"
         }
      },
      {
         "id":224,
         "emp_type":"FT",
         "start_date":"2016-05-13",
         "job_description":null,
         "emp_status":"AV",
         "job_title":"Developer",
         "user":{
            "url":"/users/274",
            "image":"https://twprofile.s3.amazonaws.com/image.jpg",
            "id":274,
            "full_name":"Ajith Paul",
            "email":"ajith.paul@doublespring.com",
            "label_txt":"AP"
         }
      }
   ],
   "created_on":"2016-07-13T09:59:44.840079Z",
   "scheduled_on":null,
   "is_responded":true
}
```
<aside>GET   /api/hrm/checkins/questions</aside>

Attribute | Description 
--------- | ----------- 
id (*integer*)| ID for the checkin
question (*string*)| question text
is_active (*boolean*)| if the checkin is active
is_public (*boolean*)| the checkin is public or private
created_by (*integer*)| ID of the creator of the checkin
schedule_day (*string*)| day on which checkin mail will be sent
schedule_time (*string*)| time of the day, to send the mail
people_count (*integer*)| number of people assigned
[assigned_to](#assigned_to-object) | info about people assigned to the checkin
created_on (*string*)| date of creation of checkin
schedule_on (*string*)| date of next schedule the checkin
is_responded (*boolean*)| if user has responded to the scheduled checkin

#### Assigned To Object 

Attribute | Description 
--------- | -----------
id (*integer*)| ID of the employee
emp_type (*string*)| employment type
start_date (*string*)| employee joining date
job_description (*string*)| description of the job	
emp_status (*string*)| active or resigned or terminated
job_title (*string*)| Designation
[user](#user-object) | employee info details

### Create Check-in

```http
POST api/hrm/checkins/questions HTTP/1.1
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
   "question":"Test Check-in ?",
   "assigned_to":[
      145,
      224
   ],
   "schedule_day":"EFR",
   "schedule_time":"ED",
   "is_public":true
}
```

```
Sample Response
```

```json
{
   "id":33,
   "question":"Test Check-in ?",
   "is_active":true,
   "is_public":true,
   "created_by":1,
   "schedule_day":"EFR",
   "schedule_time":"ED",
   "people_count":2,
   "assigned_to":[
      {
         "id":145,
         "emp_type":null,
         "start_date":"2015-09-12",
         "job_description":null,
         "emp_status":"AV",
         "job_title":"Designr1",
         "user":{
            "url":"/users/186",
            "image":"",
            "id":186,
            "full_name":"sachin n",
            "email":"sachin@doublespring.com",
            "label_txt":"SN"
         }
      },
      {
         "id":224,
         "emp_type":"FT",
         "start_date":"2016-05-13",
         "job_description":null,
         "emp_status":"AV",
         "job_title":"Developer",
         "user":{
            "url":"/users/274",
            "image":"https://twprofile.s3.amazonaws.com/image.jpg",
            "id":274,
            "full_name":"Ajith Paul",
            "email":"ajith.paul@doublespring.com",
            "label_txt":"AP"
         }
      }
   ],
   "created_on":"2016-07-13T07:23:06.225149Z",
   "scheduled_on":null,
   "is_responded":false
}
```

<aside>POST api/hrm/checkins/questions</aside>

#### Returns

If this call succeeds, the checkin object will be returned, else , if the request has got invalid data, it throws an error.

### Update Check-in



```http
PUT api/hrm/checkins/questions/{checkin_id} HTTP/1.1
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
   "question":"Test Check-ins ?",
   "assigned_to":[
      45,
      145,
      224
   ],
   "schedule_day":"EFR",
   "schedule_time":"ED",
   "is_public":true
}
```

```
Sample Response
```

```json
{
   "id":33,
   "question":"Test Check-ins ?",
   "is_active":true,
   "is_public":true,
   "created_by":1,
   "schedule_day":"EFR",
   "schedule_time":"ED",
   "people_count":3,
   "assigned_to":[
        {
         "id":45,
         "emp_type":null,
         "start_date":"2015-04-02",
         "job_description":null,
         "emp_status":"AV",
         "job_title":"Admin",
         "user":{
            "url":"/users/17",
            "image":"",
            "id":17,
            "full_name":"Jerrin Tom",
            "email":"jerry@doublespring.com",
            "label_txt":"JT"
         }
      },
      {
         "id":145,
         "emp_type":null,
         "start_date":"2015-09-12",
         "job_description":null,
         "emp_status":"AV",
         "job_title":"Designr1",
         "user":{
            "url":"/users/186",
            "image":"",
            "id":186,
            "full_name":"sachin n",
            "email":"sachin@doublespring.com",
            "label_txt":"SN"
         }
      },
      {
         "id":224,
         "emp_type":"FT",
         "start_date":"2016-05-13",
         "job_description":null,
         "emp_status":"AV",
         "job_title":"Developer",
         "user":{
            "url":"/users/274",
            "image":"https://twprofile.s3.amazonaws.com/users
/user-ad08f561-54a1-4623-975e-c996ddca7416-image.jpg",
            "id":274,
            "full_name":"Ajith Paul",
            "email":"ajith
.paul@doublespring.com",
            "label_txt":"AP"
         }
      }
   ],
   "created_on":"2016-07-13T07:23:06.225149Z",
   "scheduled_on":null,
   "is_responded":false
}
```

<aside>PUT api/hrm/checkins/questions</aside>

#### Returns

If the call succeeds, it will return the Checkin object. If the call fails, it will throw an error.


### Delete Check-in

```http
DELETE api/hrm/checkins/questions/{checkin_id} HTTP/1.1
Accept: application/json
Authorization: Token "YOUR ACCESS TOKEN"

HTTP/1.1 200 OK
Content-Type: application/json
```

<aside>DELETE api/hrm/checkins/questions/{id}(checkinID)</aside>

### 