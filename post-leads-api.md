## Posting Guidelines

This document provides instructions on sending leads to FreeRateUpdate.com through our API. 

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
api_key | string | Yes | Assigned API key
