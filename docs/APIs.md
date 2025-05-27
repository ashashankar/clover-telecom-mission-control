# API documentation 

**Register devices**
- POST /devices
  - Request Body:
    ``` json
    {
    "imei": "123456789",
    "userId": "user-1",
    "carrierId": "att",
    "osType": "iOS"
    }
Response - 200 OK

**Get device metadata**
- GET /devices/{id}


**Register Towers**
- GET /Towers/{id}
- POST /Towers/sync (to update towers information from carriers)

**Policies**
- POST /policies 
- ``` json
  {
      "enterpriseId": "ent-123",
      "roleId": "admin",
      "rules": [
      {
      "appId": "google-meet",
      "actionType": "screenShare",
      "effect": "deny"
      }
      ]}

**PolicyEngine validation**
- POST /validate
- ```json
    {
        "deviceId" : "2323",
        "userId" : "user-12",
        "appId" : "google-meet",
        "actionType": "screen-share" 

    }

- Response
- ```json
    {
        "decision" : "allow | deny | remediate",
        "policyid" : "policy-12"

    }
  
**Monitoring**
- GET  /dashboard/rejections?enterpriseid={}&deviceId={}&time>{}
- Reponse
- ```json
    {
        "deviceId" : "2323",
        "userId" : "user-12",
        "appId" : "google-meet",
        "actionType": "screen-share" 

    }
  
- GET /dashboard/stats?enterpriseid={}&timerange
- Respnse
-  ```json
    {
        "denied" : "10",
        "remediated" : "3",
        "allow" : "30",
       

    }