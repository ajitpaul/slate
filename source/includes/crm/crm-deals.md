## CRM Deal Object

```json
{
 "id":3374,
 "created_by":{
    "url":"/users/1",
    "image":"https://twprofile.s3.amazonaws.com/image.jpg",
    "id":1,
    "full_name":"Sathish Venkat",
    "email":"sathish@doublespring.com",
    "label_txt":"SV"
 },
 "owner":{
    "url":"/users/1",
    "image":"https://twprofile.s3.amazonaws.com/image.jpg",
    "id":1,
    "full_name":"Sathish Venkat",
    "email":"sathish@doublespring.com",
    "label_txt":"SV"
 },
 "title":"d3",
 "index":0,
 "stage":{
    "index":0,
    "total_stage":5,
    "title":"Prospect Lead",
    "rotting_days":null,
    "is_deal_rotting":false,
    "id":529
 },
 "deal_value":"0.00",
 "currency":{
    "is_custom":false,
    "symbol":"$",
    "code":"USD",
    "id":191
 },
 "expected_close":null,
 "last_activity_on":"2016-07-13",
 "next_activity_on":null,
 "is_trashed":false,
 "status":"open",
 "people":[
    {
       "id":17591,
       "email":"sathishv@dsss.com",
       "first_name":"sathish",
       "last_name":"v",
       "phone":"212121",
       "job_title":"wqwqwqw",
       "full_name":"sathish v",
       "profile_image":null,
       "company":10150,
       "company_name":"DSSS",
       "tags":null
    },
    {
       "id":5664,
       "email":"",
       "first_name":"sathisgg",
       "last_name":"",
       "phone":"",
       "job_title":"",
       "full_name":"sathisgg",
       "profile_image":null,
       "company":null,
       "company_name":null,
       "tags":null
    }
 ],
 "company":{
    "domain":"",
    "name":"satsss",
    "image":null,
    "ctype":"company",
    "phone":"",
    "address":"",
    "id":10206
 },
 "created_on":"2016-07-13T10:04:51.246672Z",
 "tags":'Cloud',
 "custom_fields":{
    "77":{
       "field_type":"checkbox",
       "name":"wedwd",
       "value":{
          "wedwd":false
       },
       "key":"wedwd",
       "options":[
          "wedwd"
       ],
       "is_add_field":true
    }
 },
 "won_on":null,
 "lost_on":null,
 "closed_on":null
}
```
Attribute | Description
--------- | -----------
id (*integer*)| ID of the deal
[created_by](#user-object) | info about the creator of the deal
[owner](#user-object) | info about the owner of the deal, can be changed(default owner is creator)
title (*string*)| title of the deal
index (*integer*)| order of the deal to show
[stage](#stage-object) | stage details
deal_value (*integer*)| Value set for the deal
[currency](#currency-object) | Currency set for the deal
expected_close (*string*)| expected closing date for the deal
last_activity_on (*string*)| date of the last activity done on the deal
next_activity_on (*string*)| date of the next activity on the deal
is_trashed (*boolean*)| is the deal removed
[people](#people-object) | contacts involved in the deal
[company](#company-object) | company info
created_on (*string*)| date of creation of the deal
tags (*string*)| tags added to the deal
[custom_fields](#custom_fields-object) | objects of custom fields
won_on (*string*)| date of winning the deal
lost_on (*string*)| date of losing the deal
closed_on (*string*)| date of closing the deal

#### stage Object

Attribute | Description
--------- | -----------
index (*integer*)| order of the stage
total_stage (*integer*)| total number of stages
rotting_days (*integer*)| number of set days for rotting
is_deal_rotting (*boolean*)| is the deal rotten or not
id (*integer*)| ID of the deal in the stage

#### currency Object 

Attribute | Description
--------- | -----------
is_custom (*boolean*)| if currency is customized
symbol (*string*)| symbol used to represent the currency
code (*string*)|  code for the currency
id (*integer*)| currency ID 


#### people Object
Attribute | Description
--------- | -----------
id (*integer*)| ID of the contact
email (*string*)| email address
first_name (*string*)| first name of the contact
last_name (*string*)| last name of the contact
phone (*string*)| phone number of the contact
job_title (*string*)| Desgination of the contact
full_name (*string*)| full name of the contact
profile_image (*string*)| image url for the contact
company (*string*)| company ID of the contact
company_name (*string*)| company name of the contact
tags (*string*)| tags for the contact


#### custom_fields Object 

Attribute | Description
--------- | -----------
field_type (*string*)| type of field added
name (*string*)| label of the field
value (*string*)| default value for the field
key (*string*)| key value for the field
options (*string*)| options for the checkbox
is_add_field (*boolean*)| if the field should appear in the add deal form


### Create Deal

{
   "stage":{
      "id":529,
      "title":"Prospect Lead",
      "is_trashed":false,
      "index":0,
      "is_deal_rotting":false,
      "rotting_days":null,
      "no_of_deals":136
   },
   "custom_fields":{
      "73":{
         "field_type":"text",
         "name":"sdsd",
         "key":"sdsd",
         "options":null
      },
      "74":{
         "field_type":"select",
         "name":"ed",
         "key":"ed",
         "options":[
            "ewded"
         ]
      },
      "75":{
         "field_type":"textarea",
         "name":"wedwed",
         "key":"wedwed",
         "options":null
      },
      "76":{
         "field_type":"radio",
         "name":"sdwd",
         "key":"sdwd",
         "options":[
            "dwdw"
         ],
         "value":"dwdw"
      },
      "77":{
         "field_type":"checkbox",
         "name":"wedwd",
         "key":"wedwd",
         "options":{
            "wedwd":false
         },
         "value":{
            "wedwd":false
         }
      },
      "78":{
         "field_type":"date",
         "name":"wedwdwqdw",
         "key":"wedwdwqdw",
         "options":null,
         "value":"2016-07-02"
      }
   },
   "currency":194,
   "pipeline":39,
   "title":"Test Deal",
   "deal_value":"25000",
   "expected_close":"2016-07-29"
}