## Contacts 

### People Object

```json
{
   "id":7499,
   "email":"bonnie@positivelyentertainment.com",
   "first_name":"",
   "last_name":"",
   "phone":null,
   "full_name":"bonnie@positivelyentertainment.com",
   "job_title":null,
   "owner":{
      "url":"/users/1",
      "image":"https://twprofile.s3.amazonaws.com/image.jpg",
      "id":1,
      "full_name":"Sathish
 Venkat",
      "email":"sathish@doublespring.com",
      "label_txt":"SV"
   },
   "company":{
      "domain":null,
      "name":"Doublespring",
      "image":null,
      "ctype":"company",
      "phone":null,
      "address":null,
      "id":10116
   },
   "created_by":{
      "url":"/users/1",
      "image":"https://twprofile.s3.amazonaws.com/image.jpg",
      "id":1,
      "full_name":"Sathish Venkat",
      "email":"sathish@doublespring.com",
      "label_txt":"SV"
   },
   "created_on":"2015-12-23T07:51:45.948099Z",
   "tags":null,
   "custom_fields":null
}
``` 

Attribute | Description
----------| -----------
id (*integer*)| Contact ID
email (*string*)| email address
first_name (*string*)| first name of the contact
last_name (*string*)| last name of the contact
phone (*string*)| phone number of the contact
full_name (*string*)| full name of the contact
job_title (*string*)| Designation 
[owner](#user-object) | owner info
[company](#company-object) | company details
[created_by](#user-object) | creator of the contact
created_on (*string*)| datetime of the creation 
tags (*string*)| tag names given for the contact
[custom_fields](#custom-fields-object) | all custom fields for the CRM contacts


### Create People

```http
POST api/contacts/people HTTP/1.1
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
   "custom_fields":{
      "25":{
         "field_type":"text",
         "name":"Deal",
         "key":"deal",
         "options":[
         ],
         "value":"Test"
      },
      "26":{
         "field_type":"date",
         "name":"Date",
         "key":"date",
         "options":null,
         "value":"2016-07-08"
      }
   },
   "owner":1,
   "first_name":"Ajith",
   "last_name":"Paul",
   "email":"ajithpaul@doublespring.com",
   "phone":"9995584542",
   "job_title":"SW",
   "companyName":"Doublespring"
}
```

```
Sample Response
```

```json
{
   "id":17784,
   "email":"ajithp@doublespring.com",
   "first_name":"Ajith",
   "last_name":"Paul",
   "phone":"8452145555",
   "full_name":"Ajith Paul",
   "job_title":"SW",
   "owner":{
      "url":"/users/1",
      "image":"https://twprofile.s3.amazonaws.com/image.jpg",
      "id":1,
      "full_name":"Sathish Venkat",
      "email":"sathish@doublespring.com",
      "label_txt":"SV"
   },
   "company":{
      "domain":"sdfzsdfdsf.com",
      "name":"doublespring",
      "image":null,
      "ctype":"company",
      "phone":"894fd646",
      "address":"sdfsdfsdf",
      "id":10207
   },
   "created_by":{
      "url":"/users/1",
      "image":"https://twprofile.s3.amazonaws.com/image.jpg",
      "id":1,
      "full_name":"Sathish Venkat",
      "email":"sathish@doublespring.com",
      "label_txt":"SV"
   },
   "created_on":"2016-07-18T12:40:48.810179Z",
   "tags":null,
   "custom_fields":{
      "25":{
         "field_type":"text",
         "name":"Deal",
         "value":"Test Deal",
         "key":"deal",
         "options":[

         ],
         "is_add_field":true
      },
      "26":{
         "field_type":"date",
         "name":"Date",
         "value":"2016-07-06",
         "key":"date",
         "options":null,
         "is_add_field":true
      }
   }
}
```
<aside>POST api/contacts/people</aside>

#### Returns

If call succeeds, it will send the [contacts object](#contacts-object) back. 

### Update People

```http
PUT api/contacts/people/{contact_id} HTTP/1.1
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
   "id":17782,
   "email":"ajithpaul@doublespring.com",
   "first_name":"Ajith",
   "last_name":"Paul M",
   "phone":"4568595442",
   "full_name":"Ajith Paul",
   "job_title":"SW",
   "owner":1,
   "company":10224,
   "created_by":{
      "url":"/users/1",
      "image":"https://twprofile.s3.amazonaws.com/image.jpg",
      "id":1,
      "full_name":"Sathish Venkat",
      "email":"sathish@doublespring.com",
      "label_txt":"SV"
   },
   "created_on":"2016-07-18T12:28:02.165162Z",
   "tags":null,
   "custom_fields":{
      "25":{
         "field_type":"text",
         "name":"Deal",
         "value":"Test",
         "key":"deal",
         "options":[

         ],
         "is_add_field":true
      },
      "26":{
         "field_type":"date",
         "name":"Date",
         "value":"2016-07-07T18:30:00.000Z",
         "key":"date",
         "options":null,
         "is_add_field":true
      }
   }
}
```

```
Sample Response
```

```json
{
   "id":17782,
   "email":"ajithpaul@doublespring.com",
   "first_name":"Ajith",
   "last_name":"Paul M",
   "phone":"4568595442",
   "full_name":"Ajith Paul M",
   "job_title":"SW",
   "owner":{
      "url":"/users/1",
      "image":"https://twprofile.s3.amazonaws.com/image.jpg",
      "id":1,
      "full_name":"SathishVenkat",
      "email":"sathish@doublespring.com",
      "label_txt":"SV"
   },
   "company":{
      "domain":null,
      "name":"Doublespring",
      "image":null,
      "ctype":"company",
      "phone":null,
      "address":null,
      "id":10224
   },
   "created_by":{
      "url":"/users/1",
      "image":"https://twprofile.s3.amazonaws.com/image.jpg",
      "id":1,
      "full_name":"Sathish Venkat",
      "email":"sathish@doublespring.com",
      "label_txt":"SV"
   },
   "created_on":"2016-07-18T12:28:02.165162Z",
   "tags":null,
   "custom_fields":{
      "25":{
         "field_type":"text",
         "name":"Deal",
         "value":"Test",
         "key":"deal",
         "options":[

         ],
         "is_add_field":true
      },
      "26":{
         "field_type":"date",
         "name":"Date",
         "value":"2016-07-07T18:30:00.000Z",
         "key":"date",
         "options":null,
         "is_add_field":true
      }
   }
}
```
<aside>PUT api/contacts/people/{contact_id}</aside>

#### Returns 

If call succeeds, it will return the [contacts object](#contacts-object).


### Delete People

```http
DELETE api/contacts/people/{contact_id} HTTP/1.1
Accept: application/json
Authorization: Token "YOUR ACCESS TOKEN"

HTTP/1.1 200 OK
Content-Type: application/json
```

<aside>DELETE api/contacts/people/{contact_id}</aside>

#### Returns 

If the call succeeds, the contact will be removed from the list.