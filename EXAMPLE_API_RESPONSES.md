``` javascript
// Recommendation active
{  
   "user":{  
      "id":"55d28c2d6d61636fa90a0000",
      "first_name":"Gabriel",
      "last_name":"Henriques",
      "birthdate":"1989-06-24T00:00:00.000-07:00",
      "phone":"1-999-999-9999",
      "email":"gabriel@hellomd.com",
      "address":{  
         "address_1":"50 8th St",
         "address_2":"",
         "zipcode":"94101",
         "city":"San Francisco",
         "state":"California"
      },
      "document_url":"https://hellomd-local.s3-us-west-2.amazonaws.com/drivers_license/55d28c2d6d61636fa90a0000/drivers_license.jpg?X-Amz-Expires=600\\u0026X-Amz-Date=20150818T181012Z\\u0026X-Amz-Algorithm=AWS4-HMAC-SHA256\\u0026X-Amz-Credential=AKIAJ2ZQND3P2XLATVTQ/20150818/us-west-2/s3/aws4_request\\u0026X-Amz-SignedHeaders=host\\u0026X-Amz-Signature=b6686ccbfd7186aefea598d740fd64e9bfa87e72561655cbff2f9cc8be5b7835",
      "recommendation":{  
         "status":"Active",
         "expires_at":"2016-08-18T10:28:55.191-07:00",
         "published_at":"2015-08-18T10:28:55.191-07:00",
         "url":""
      },
      "doctor":{  
         "first_name":"Sharon",
         "last_name":"Olson",
         "doctor_license":"942348"
      }
   }
}

// Recommendation expired
{  
   "user":{  
      "id":"55d28c2d6d61636fa90a0000",
      "first_name":"Gabriel",
      "last_name":"Henriques",
      "birthdate":"1989-06-24T00:00:00.000-07:00",
      "phone":"1-999-999-9999",
      "email":"gabriel@hellomd.com",
      "address":{  
         "address_1":"50 8th St",
         "address_2":"",
         "zipcode":"94101",
         "city":"San Francisco",
         "state":"California"
      },
      "document_url":"https://hellomd-local.s3-us-west-2.amazonaws.com/drivers_license/55d28c2d6d61636fa90a0000/drivers_license.jpg?X-Amz-Expires=600\\u0026X-Amz-Date=20150818T181012Z\\u0026X-Amz-Algorithm=AWS4-HMAC-SHA256\\u0026X-Amz-Credential=AKIAJ2ZQND3P2XLATVTQ/20150818/us-west-2/s3/aws4_request\\u0026X-Amz-SignedHeaders=host\\u0026X-Amz-Signature=b6686ccbfd7186aefea598d740fd64e9bfa87e72561655cbff2f9cc8be5b7835",
      "recommendation":{  
         "status":"Expired",
         "expires_at":"2014-08-18T10:28:55.191-07:00",
         "published_at":"2013-08-18T10:28:55.191-07:00",
         "url":""
      },
      "doctor":{  
         "first_name":"Sharon",
         "last_name":"Olson",
         "doctor_license":"942348"
      }
   }
}

// Doctor is still writing the recommendation
{  
   "user":{  
      "id":"55d28c2d6d61636fa90a0000",
      "first_name":"Gabriel",
      "last_name":"Henriques",
      "birthdate":"1989-06-24T00:00:00.000-07:00",
      "phone":"1-999-999-9999",
      "email":"gabriel@hellomd.com",
      "address":{  
         "address_1":"50 8th St",
         "address_2":"",
         "zipcode":"94101",
         "city":"San Francisco",
         "state":"California"
      },
      "document_url":"https://hellomd-local.s3-us-west-2.amazonaws.com/drivers_license/55d28c2d6d61636fa90a0000/drivers_license.jpg?X-Amz-Expires=600\\u0026X-Amz-Date=20150818T181012Z\\u0026X-Amz-Algorithm=AWS4-HMAC-SHA256\\u0026X-Amz-Credential=AKIAJ2ZQND3P2XLATVTQ/20150818/us-west-2/s3/aws4_request\\u0026X-Amz-SignedHeaders=host\\u0026X-Amz-Signature=b6686ccbfd7186aefea598d740fd64e9bfa87e72561655cbff2f9cc8be5b7835",
      "recommendation":{  
         "status":"Pending"
      },
      "doctor":{  
         "first_name":"Sharon",
         "last_name":"Olson",
         "doctor_license":"942348"
      }
   }
}


// Doctor did not recommend the use of medical marijuana
{  
   "user":{  
      "id":"55d28c2d6d61636fa90a0000",
      "first_name":"Gabriel",
      "last_name":"Henriques",
      "birthdate":"1989-06-24T00:00:00.000-07:00",
      "phone":"1-999-999-9999",
      "email":"gabriel@hellomd.com",
      "address":{  
         "address_1":"50 8th St",
         "address_2":"",
         "zipcode":"94101",
         "city":"San Francisco",
         "state":"California"
      },
      "document_url":"https://hellomd-local.s3-us-west-2.amazonaws.com/drivers_license/55d28c2d6d61636fa90a0000/drivers_license.jpg?X-Amz-Expires=600\\u0026X-Amz-Date=20150818T181012Z\\u0026X-Amz-Algorithm=AWS4-HMAC-SHA256\\u0026X-Amz-Credential=AKIAJ2ZQND3P2XLATVTQ/20150818/us-west-2/s3/aws4_request\\u0026X-Amz-SignedHeaders=host\\u0026X-Amz-Signature=b6686ccbfd7186aefea598d740fd64e9bfa87e72561655cbff2f9cc8be5b7835",
      "recommendation":{  
         "status":"Not Recommended"
      },
      "doctor":{  
         "first_name":"Sharon",
         "last_name":"Olson",
         "doctor_license":"942348"
      }
   }
}


// Did not agree to shared with partner yet
{  
   "user":{  
      "id":"55d28c2d6d61636fa90a0000",
   }
}
```
