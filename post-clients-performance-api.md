## Posting Guidelines

This document provides instructions on sending a lead performance status to FreeRateUpdate.com through our API. 

### Posting

Data is to be sent via the POST method and HTTPS protocol to the following URL:

https://api.freerateupdate.com/post/client_performance

### Testing

Please post all tests to the following URL:

https://staging-api.freerateupdate.com/post/client_performance

### Accepted Fields and Values

Field | Accepted Values | Required | Description
------| --------------- | -------- | -----------
api_key | string | Yes | Assigned API key
status | string | Yes | Performance status ("credit_pull", "setup")
lead_id | number | No | FreeRateUpdate Lead ID
email | string | No | Consumer email address
phone | string | No | Consumer primary phone number

### Response

You will receive a JSON formatted response with the following fields

Field | Value | Description
----- | ----- | -----------
success | boolean | If the lead was accepted or not
errors | array | For each error, an error object with a 'type', 'message', and 'field' property. If applicable, the 'field' property will have a value matching the above fields to which the error is referencing. See below for further detail
data | object | Contains more information about the submission result. 

Example Good Response:
```
{
    "success": true,
    "errors": [],
    "data": []
}
```

Example Bad Response
```
{
    "success": false,
    "errors": [
        {
            "message": "Status is required",
            "type": "validation",
            "field": "status"
        }
    ],
    "data": {}
}
```
### Error Types

Error Type | Description
---------- | ----------
authentication | There was a problem with authenticating API credentials
verification | There was a problem with sent data. i.e. a required field was missing.