## Posting Guidelines

This document provides instructions on sending leads to FreeRateUpdate.com through our API. 

### Posting

Data is to be sent via the POST method and HTTPS protocol to:

https://api.freerateupdate.com/post/lead

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
current_fha | yes<br>no | Refinance | If the consumer is currently in a FHA loan
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
source | string | Yes | The source this lead came from. i.e. Paid Advertising, Email, Search, etc.
campaign | string | No | The name of the campaign used for the source
api_key | string | Yes | Assigned API key

### Response

You will receive a JSON formatted response with the following fields

Field | Value | Description
----- | ----- | -----------
success | boolean | If the lead was accepted or not
errors | array | For each error, an error object with a 'type' and 'message' property
lead_id | integer | The unique identifier for the lead on success. 0 if not. 

Example Good Response:
```
{
    "success": true,
    "errors": [],
    "lead_id": 12345
}
```

Example Bad Response
```
{
	"success": false,
    "errors": [
        {
            "message": "First Name is required",
            "type": "validation"
        },
        {
            "message": "Primary Phone is required",
            "type": "validation"
        }
    ],
    "lead_id": 0
}
```
