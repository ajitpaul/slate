## Mails

### Mail Object

```json
{
  "id":8,
  "deal":null,
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
id | ID of the mail
deal | deal title, if any
[people](#people-object) | array of contacts connected to the mail(To,CC)
from_str | Name and mail of the sender
subject | subject for the mail
body_html | body content in html format
[created_by](#user-object) | user details of creator
received | date of receiving the mail
is_archived | is the mail archived
is_private | is the mail private
is_read | is the mail read 
act_on | date for the mail activity

#### People Object 

Attribute | Description
---------| -----------
id | ID of the contact
email | email address
first_name | first name of the contact
last_name | last name
phone | phone number of the contact
job_title | desgination of the contact
full_name | full name of the contact
profile_image | image url of the contact
company | company ID
company | company name
tags | tags related to the contact
