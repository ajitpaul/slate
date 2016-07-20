### Organization Object

```json
  {
     "id":18,
     "domain":null,
     "name":"",
     "address":null,
     "phone":null,
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
     "created_on":"2015-08-29T14:49:13.838853Z",
     "people":0,
     "deals":1,
     "tags":null,
     "custom_fields":null
  }
```

Attribute | Description
----------| -----------
id (*integer*)| Organization ID
domain (*string*)| domain used by the organization
name (*string*)| name of organization
address (*string*)| address of organization
phone (*string*)| phone number
[created_by](#user-object) | organization added-by user details
[owner](#user-object) | owner details
created_on (*string*)| creation date 
people (*integer*)(*integer*)| total people added to the organization
deals (*integer*)| total deals added
tags (*string*)| tags related to organization
[custom_fields](#custom_fields-object) | custom fields added to the organization add-form


### Create Organization


```http
POST api/contacts/companies HTTP/1.1
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
         "name":"Test",
         "key":"test",
         "options":null,
         "value":"Custom
 field"
      },
      "26":{
         "field_type":"text",
         "name":"Test 123",
         "key":"test-123",
         "options":null,
         "value":"Custom
 field2"
      }
   },
   "owner":274,
   "name":"Twitter",
   "domain":"twitter.com",
   "address":"1502/22 Twitter Inc",
   "phone":"245112212454"
}
```

```
Sample Response
```

```json
{
   "id":10231,
   "domain":"twitter.com",
   "name":"Twitter",
   "address":"1502/22 Twitter Inc",
   "phone":"245112212454",
   "created_by":{
      "url":"/users/1",
      "image":"https://twprofile.s3.amazonaws.com/image.jpg",
      "id":1,
      "full_name":"Sathish Venkat",
      "email":"sathish@doublespring.com",
      "label_txt":"SV"
   },
   "owner":{
      "url":"/users/274",
      "image":"https://twprofile.s3.amazonaws.com/image.jpg",
      "id":274,
      "full_name":"Ajith Paul",
      "email":"ajith.paul@doublespring.com",
      "label_txt":"AP"
   },
   "created_on":"2016-07-19T07:26:57.157037Z",
   "people":0,
   "deals":0,
   "tags":null,
   "custom_fields":{
      "25":{
         "field_type":"text",
         "name":"Test",
         "value":"Custom field",
         "key":"test",
         "options":null,
         "is_add_field":true
      },
      "26":{
         "field_type":"text",
         "name":"Test 123",
         "value":"Custom field2",
         "key":"test-123",
         "options":null,
         "is_add_field":true
      }
   }
}
```

<aside>POST api/contacts/companies</aside>

### Update Organization

```http
PUT api/contacts/companies/{organization_id} HTTP/1.1
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
   "id":10231,
   "domain":"twitter.com",
   "name":"Twitter",
   "address":"1502/22 Twitter Inc",
   "phone":"40015222542323",
   "created_by":{
      "url":"/users/1",
      "image":"https://twprofile.s3.amazonaws.com/image.jpg",
      "id":1,
      "full_name":"Sathish Venkat",
      "email":"sathish@doublespring.com",
      "label_txt":"SV"
   },
   "owner":274,
   "created_on":"2016-07-19T07:26:57.157037Z",
   "people":0,
   "deals":0,
   "tags":null,
   "custom_fields":{
      "25":{
         "field_type":"text",
         "name":"Test",
         "value":"Custom field1",
         "key":"test",
         "options":null,
         "is_add_field":true
      },
      "26":{
         "field_type":"text",
         "name":"Test 123",
         "value":"Custom field2",
         "key":"test-123",
         "options":null,
         "is_add_field":true
      }
   }
}

```
Sample Response
```

```json
{
   "id":10231,
   "domain":"twitter.com",
   "name":"Twitter",
   "address":"1502/22 Twitter Inc",
   "phone":"40015222542323",
   "created_by":{
      "url":"/users/1",
      "image":"https://twprofile.s3.amazonaws.com/image.jpg",
      "id":1,
      "full_name":"Sathish Venkat",
      "email":"sathish@doublespring.com",
      "label_txt":"SV"
   },
   "owner":{
      "url":"/users/274",
      "image":"https://twprofile.s3.amazonaws.com/image.jpg",
      "id":274,
      "full_name":"Ajith Paul",
      "email":"ajith.paul@doublespring.com",
      "label_txt":"AP"
   },
   "created_on":"2016-07-19T07:26:57.157037Z",
   "people":0,
   "deals":0,
   "tags":null,
   "custom_fields":{
      "25":{
         "field_type":"text",
         "name":"Test",
         "value":"Custom field1",
         "key":"test",
         "options":null,
         "is_add_field":true
      },
      "26":{
         "field_type":"text",
         "name":"Test 123",
         "value":"Custom field2",
         "key":"test-123",
         "options":null,
         "is_add_field":true
      }
   }
}
```

<aside>PUT api/contacts/companies/{organization_id}</aside>

### Delete Organisation

```http
DELETE api/contacts/companies/{organization_id} HTTP/1.1
Accept: application/json
Authorization: Token "YOUR ACCESS TOKEN"

HTTP/1.1 200 OK
Content-Type: application/json
```

<aside>DELETE api/contacts/companies/{organization_id}</aside>