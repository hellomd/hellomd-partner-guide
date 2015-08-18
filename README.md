# HelloMD Partner Integration Guide
A guide to integrating with HelloMD as a Partner.

## Pre-requisites
In order to follow this guide you need to be a partner with HelloMD and have your PartnerId, ApiKey, ApiSecret and setup a CallbackURL.
For more information on partnerships feel free to [contact us](mailto:api@hellomd.com).

## Use Cases
You have patients that don't yet have a medical marijuana card and want to adquire one.

## How to process a patient
1. Redirect your user to https://YOUR_PARTNER_URL.hellomd.com
2. We will process the patient and emit the recommendation
3. The user will be asked to share his/her information with you.
4. After agreeing to share, the user will be asked to go back to your website with a link to a predefined callback URL to your website. Example: https://example.com/hellomd-callback?user_id=USER_ID
5. Use our API endpoint to recover that patient's information

## User API Endpoint
```
GET /api/v1/users/:id
```
This endpoint returns the user recommendation information, if the users has consent to share it with you.

### Example Request
```
GET /api/v1/users/55d28c2d6d61636fa90a0000
```
```javascript
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
```
