## Mails

### Mail Object

```json
{
  "id":8,
  "deal":{
      "title":"Test IPL",
      "ctype":"deal",
      "deal_value":0.0,
      "currency_symbol":"$",
      "owner":{
         "url":"/users/221",
         "image":"",
         "id":221,
         "full_name":"Prasad Vara",
         "email":"prasad@doublespring.com",
         "label_txt":"PV"
      },
      "id":3244,
      "stage":{
         "index":0,
         "total_stage":5,
         "title":"Prospect Lead",
         "rotting_days":null,
         "is_deal_rotting":false,
         "id":529
      }
   },
  "people":[
     {
        "id":1,
        "email":"sachin@doublespring.com",
        "first_name":"Sachin",
        "last_name":"N",
        "phone":"8884546564",
        "job_title":"Designer",
        "full_name":"Sachin N",
        "profile_image":null,
        "company":1,
        "company_name":"Gensis",
        "tags":null
     },
     {
        "id":1910,
        "email":"deal-265@sandbox4ace1c73643542298f3f7cbc08cdc826.mailgun.org",
        "first_name":"deal-265",
        "last_name":"",
        "phone":null,
        "job_title":null,
        "full_name":"deal-265",
        "profile_image":null,
        "company":null,
        "company_name":null,
        "tags":null
     }
  ],
  "from_str":"Sathish Kumar <sathish@doublespring.com>",
  "subject":"test",
  "body_html":"<div dir=\"ltr\">test<br clear=\"all\"><div><br></div
	>-- <br><div class=\"gmail_signature\"><div><font color=\"#333333\">Regards,</font><div><font color=
	\"#333333\">Sathishkumar V</font></div></div><font color=\"#333333\"><a href=\"http://www.doublespring
	.com/\" target=\"_blank\">Double Spring Media India  (P) Ltd</a></font><div><font color=\"#333333\">
	<br></font><div><font color=\"#333333\" face=\"arial, sans-serif\" size=\"3\"><br></font></div></div
	></div>\r\n</div>\r\n",
  "created_by":{
     "url":"/users/1",
     "image":"https://twprofile.s3.amazonaws.com/image.jpg",
     "id":1,
     "full_name":"Sathish Venkat",
     "email":"sathish@doublespring.com",
     "label_txt":"SV"
  },
  "received":"2015-10-30T13:50:31.081463Z",
  "is_archived":false,
  "is_private":true,
  "is_read":true,
  "act_on":"2015-10-30T13:50:31.081463Z"
}
```

Attribute | Description
---------| -----------
id (*integer*)| ID of the mail
[deal](#deals-object) | object with data about deal or company.
[people](#people-object) | array of contacts connected to the mail(To,CC)
from_str (*string*)| Name and mail of the sender
subject (*string*)| subject for the mail
body_html (*string*)| body content in html format
[created_by](#user-object) | user details of creator
received (*string*)| date of receiving the mail
is_archived (*boolean*)| is the mail archived
is_private (*boolean*)| is the mail private
is_read (*boolean*)| is the mail read 
act_on (*string*)| date for the mail activity

#### Deal Object

Attribute | Description
---------| -----------
title (*string*)| title of the deal connected
ctype (*string*)| it will change according to the content it is sending to the frontend. 
deal_value (*integer*)| value of the deal
currency_symbol (*string*)| currency symbol
[owner](#user-object) | owner data 
id (*integer*)| ID for the deal
[stage](#stage-object) | stage info 


#### People Object 

Attribute | Description
---------| -----------
id (*integer*)| ID of the contact
email (*string*)| email address
first_name (*string*)| first name of the contact
last_name (*string*)| last name
phone (*string*)| phone number of the contact
job_title (*string*)| desgination of the contact
full_name (*string*)| full name of the contact
profile_image (*string*)| image url of the contact
company (*string*)| company ID
company (*string*)| company name
tags (*string*)| tags related to the contact


### Connect Deal To Mail

```http
PATCH /api/crm/emails/{mail_id} HTTP/1.1
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
  "deal":3375
 }
```

```
Sample Response
```

```json
{
   "id":2,
   "deal":{
      "title":"Test IPL",
      "ctype":"deal",
      "deal_value":0.0,
      "currency_symbol":"$",
      "owner":{
         "url":"/users/221",
         "image":"",
         "id":221,
         "full_name":"Prasad Vara",
         "email":"prasad@doublespring.com",
         "label_txt":"PV"
      },
      "id":3244,
      "stage":{
         "index":0,
         "total_stage":5,
         "title":"Prospect Lead",
         "rotting_days":null,
         "is_deal_rotting":false,
         "id":529
      }
   },
   "people":[

   ],
   "from_str":"Sathish Kumar <sathish@doublespring.com>",
   "subject":"test",
   "body_html":"<div dir=\"ltr\">test<br clear=\"all\"><div><br></div>-- <br><div class=\"gmail_signature
     \><div><font color=\"#333333\">Regards,</font><div><font color=\"#333333\">Sathishkumar V</font></div
         Media India  (P) Ltd</a></font><div><font color=\"#333333\"><br></font><div><font color=\"#333333\"
      face=\"arial, sans-serif\" size=\"3\"><br></font></div></div></div>\r\n</div>\r\n",
   "created_by":{
      "url":"/users/1",
      "image":"https://twprofile.s3.amazonaws.com/users/image.jpg",
      "id":1,
      "full_name":"Sathish Venkat",
      "email":"sathish@doublespring.com",
      "label_txt":"SV"
   },
   "received":"2015-10-30T13:22:55.528585Z",
   "is_archived":false,
   "is_private":true,
   "is_read":true,
   "act_on":"2015-10-30T13:22:55.528585Z"
}
```

#### Returns
 
 If the call succeeds, it will return the [mail object](#mail-object) with updated deal name.

