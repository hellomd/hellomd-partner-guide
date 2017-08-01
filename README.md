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
5. Use our API endpoint to recover that patient's information, at `https://www.hellomd.com`

> Be sure to set the `accept` header to expect `application/json` otherwise you will receive a `406` error.

## API Authentication
Use basic http auth over ssl. ApiKey as username and ApiSecret as password.

## User API Endpoint
```
GET https://www.hellomd.com/api/v1/users/:id
```
This endpoint returns the user recommendation information, if the users has consent to share it with you.

### Example Request
```
GET https://www.hellomd.com/api/v1/users/55d28c2d6d61636fa90a0000
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

## How to prepopulate the patient's registration form
If you already have some of the patient's information. You can use it the prepopulate your HelloMD registration form with the data, by passing us a urlsafe base64 encoded  json in a parameter called "preset". For example, using the `Ruby` language:

``` ruby
user_data = {
   "first_name": "John",
   "last_name": "Smith",
   "email": "jsmith@example.com",
   "phone": "1-999-999-9999",
   "address_1": "100 8th Street",
   "address_2": "Apt210",
   "zipcode": 94101,
   "gender": "Male"
}
user_data_json = JSON.dump(user_data)
preset = Base64.urlsafe_encode64(user_data_json)
p preset
# outputs: eyJmaXJzdF9uYW1lIjoiSm9obiIsImxhc3RfbmFtZSI6IlNtaXRoIiwiZW1haWwiOiJqc21pdGhAZXhhbXBsZS5jb20iLCJwaG9uZSI6IjEtOTk5LTk5OS05OTk5IiwiYWRkcmVzc18xIjoiMTAwIDh0aCBTdHJlZXQiLCJhZGRyZXNzXzIiOiJBcHQyMTAiLCJ6aXBjb2RlIjo5NDEwMSwiZ2VuZGVyIjoiTWFsZSJ9
```

Then when redirecting the patient include the preset on the URL, as follows:

https://YOUR_PARTNER_URL.hellomd.com/signup?preset=eyJmaXJzdF9uYW1lIjoiSm9obiIsImxhc3RfbmFtZSI6IlNtaXRoIiwiZW1haWwiOiJqc21pdGhAZXhhbXBsZS5jb20iLCJwaG9uZSI6IjEtOTk5LTk5OS05OTk5IiwiYWRkcmVzc18xIjoiMTAwIDh0aCBTdHJlZXQiLCJhZGRyZXNzXzIiOiJBcHQyMTAiLCJ6aXBjb2RlIjo5NDEwMSwiZ2VuZGVyIjoiTWFsZSJ9

## How to obtain patient registration information from Hello MD via the API
Once you receive the `user_id` for a patient, use an HTTP request like the following to obtain all the information given during the patient's registration. For example, using the `Ruby` language and the [http.rb](https://github.com/httprb/http) gem:

```ruby
require 'http'

def get_patient_registration(user_id, key=HELLOMD_KEY, secret=HELLOMD_SECRET)
  HTTP.basic_auth( user: key, pass: secret )
    .headers(:accept => "application/json")
    .get("https://www.hellomd.com/api/v1/users/#{id}")
end
```
