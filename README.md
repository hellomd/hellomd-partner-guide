# HelloMD Partner Integration Guide
A guide to integrating with HelloMD as a Partner.

## Pre-requisites
In order to follow this guide you need to be a partner with HelloMD and have your PartnerId, ApiKey, ApiSecret and setup a CallbackURL.
For more information on partnerships feel free to [contact us](mailto:api@hellomd.com).

## Use Cases
HelloMD patients have already provided their personal information, including all necessary items to join a medical marijuana collective or delivery service. In order to provide the best possible user experience, it is possible to use the HelloMD API to request access to this information programatically. In this case, the patient will be asked to confirm that they wish to share their information. Assuming consent, the API can be used to provide the information.


## How request a patient's info
1. Redirect your user to https://www.hellomd.com/collectives/YOUR_PARTNER_ID/association
2. We will ask your user his permission to share with you his HelloMD Information
3. The user will be redirected back to your CallbackURL with his patient number as a query param. e.g.: https://example.com/hellomd-callback?patient_number=THE_PATIENT_NUMBER
4. Connect to our API using one of our clients to get the patient information 

## API clients
1. [NodeJS](https://github.com/hellomd/hellomd-api-nodejs)
