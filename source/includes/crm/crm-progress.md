## Progress

### Progress Object

```json
{
   "id":3538,
   "act_on":"2016-07-19T07:32:57.106018Z",
   "action_type":"updated",
   "action_field":"many",
   "verb":"updated company details",
   "class_name":"updated",
   "organization_id":1,
   "created_on":"2016-07-19T07:32:57.106018Z",
   "is_deleted":false,
   "actor":{
      "url":"/users/1",
      "image":"https://twprofile.s3.amazonaws.com/image.jpg",
      "id":"1",
      "email":"sathish@doublespring.com",
      "full_name":"Sathish Venkat",
      "label_txt":"SV"
   },
   "action_obj":{
      "domain":"twitter.com",
      "name":"Twitter",
      "image":"None",
      "ctype":"company",
      "phone":"245112212454",
      "address":"1502/22 Twitter Inc",
      "id":"10231"
   },
   "source_obj":null,
   "target_obj":null
}
```

### Create Progress

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