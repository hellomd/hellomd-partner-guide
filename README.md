# HelloMD Partner Guide
A guide to integrating to HelloMD as a Partner

## Pre-requisites
In order to follow this guide you need to be a partner with HelloMD and have your PartnerId, ApiKey, ApiSecret and setup a CallbackURL.
For more information on partnerships feel free to [contact us](mailto:info@hellomd.com).

## How request a patient's info
1. Redirect your user to https://www.hellomd.com/collectives/YOUR_PARTNER_ID/association
2. We will ask your user his permission to share with you his HelloMD Information
3. The user will be redirected back to your CallbackURL with his patient number as a query param. e.g.: https://example.com/hellomd-callback?patient_number=THE_PATIENT_NUMBER
4. Connect to our API using one of our clients to get the patient information 

## API clients
1. [NodeJS](https://github.com/hellomd/hellomd-nodejs-api)
