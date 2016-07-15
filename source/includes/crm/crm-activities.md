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
      "act_on":"2016-07-13T08
:15:00",
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
id | Activity ID
act_type | activity type
assigned_to | people assigned to the activity
person | contact person details
company | organisation details
deal | deal info
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


### Create Activity 


