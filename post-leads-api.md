## Posting Guidelines

This document provides instructions on sending leads to FreeRateUpdate.com through our API. 

### Posting

Data is to be sent via the POST method and HTTPS protocol to the following URL:

https://api.freerateupdate.com/post/lead

### Testing

Please post all tests to the following URL:

https://staging-api.freerateupdate.com/post/lead

### Accepted Fields and Values

Field | Accepted Values | Required | Description
------| --------------- | -------- | -----------
type | refinance<br>purchase | Yes | If the lead is purchase or refinance
credit_rating | excellent<br>good<br>fair<br>poor | Yes | Self assessed credit rating
property_type | single<br>multi<br>condo<br>town_house<br>cooperative | Yes | Type of property
existing_rate_type | 30_yr_fixed<br>15_yr_fixed<br>ARM<br>unknown | Refinance | Existing rate type
desired_rate_type | 30_yr_fixed<br>15_yr_fixed<br>ARM<br>unknown | Yes | Desired rate type
cash_out | integer | Refinance | Amount cash out for a refinance
property_value | integer | Refinance | Value of property
first_mortgage_balance | integer | Refinance | First mortgage balance
first_mortgage_rate | decimal | Refinance | First mortgage rate
current_fha | yes<br>no | Yes | If the consumer is currently in a FHA loan
current_va | yes<br>no | No | If the consumer is currently in a VA loan
originated_before | yes<br>no | No | If the consumer's FHA loan has originated before June 2009
found_home | yes<br>no | Purchase | If the consumer has found a home
new_home_value | integer | Purchase | The value of the home
purchase_agreement | yes<br>no | No | If the consumer has already signed a purchase agreement
estimated_down_payment | decimal | Yes | Estimated percent down payment
veteran_military | yes<br>no | Yes | If the user is a veteran or active military
desired_laon_amount | integer | No | Total loan amount desired
first_name | string | Yes | Consumer first name
last_name | string | Yes | Consumer last name
email | string | Yes | Consumer email address
primary_phone | string | Yes | Consumer primary phone number
secondary_phone | string | No | Consumer secondary phone number
property_address | string | No | Street address of the property
property_city | string | No | City of the property
property_state | string | Yes | State of the property
property_zip | string | Yes | Zip code of property
medium | string | Yes | The source this lead came from. i.e. Paid Advertising, Email, Search, etc.
campaign | string | No | The name of the campaign used for the source
ip | string | No | ipv4 or ipv6 address
universal_leadid | string | Yes | The ID acquired from LeadID
api_key | string | Yes | Assigned API key

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
    "data": [
        {
            "lead_id": 1880436
        },
        {
            "lenders": [
                {
                    "address": "",
                    "city": "",
                    "contact_name": "",
                    "email": "",
                    "lender_name": "Lending King",
                    "phone": "555-983-3735",
                    "state": "",
                    "website": "www.lendingking.com",
                    "zip": ""
                },
                {
                    "address": "1050 Williams",
                    "city": "Detroit",
                    "contact_name": "Roger Lender",
                    "email": "super@loans.com",
                    "lender_name": "Super Loans",
                    "phone": "555-251-9080",
                    "state": "MI",
                    "website": "http://www.superloans.com",
                    "zip": "48124"
                },
            ]
        }
    ]
}
```

Example Bad Response
```
{
	"success": false,
    "errors": [
        {
            "message": "First Name is required",
            "type": "validation",
            "field": "first_name"
        },
        {
            "message": "Primary Phone is required",
            "type": "validation",
            "field": "primary_phone"
        }
    ],
    "data": {}
}
```
### Error Types

Error Type | Description
---------- | ----------
authentication | There was a problem with authenticating API credentials
validation | There was a problem with sent data. i.e. a required field was missing.
verification | Something about the lead itself was invalid. i.e. Loan amount was too low
