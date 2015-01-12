## Posting Guidelines

This document provides instructions on implementing a feed that may be used to immediately notify your CRM system of a lead. These values are sent under the POST method. The following information outlines the format of the data that will be sent to you.

### Possible Attributes and Values

Field   | Possible Values   | Lead Type   | Description     
------- | ----------------- | ----------- | --------------- 
LoanPurpose | Refinance<br>Purchase | -- | The type of lead 
CreditRating | Excellent<br />Good<br />Fair<br />Poor | All | User's self-assessed credit
DesiredRateType | 30-Yr Fixed<br />15-Yr Fixed<br />ARM<br />Don’t Know | All | Desired rate type
RateType1 |  30-Yr Fixed<br />15-Yr Fixed<br />ARM<br />Don’t Know | Refinance | Existing rate type
PropertyType | Single<br />Multi<br />Condo<br />Town House<br />Cooperative | All | Type of home
CashOut | A number ranging from 2500 - 95000, OR the text: "100000 or more" | Refinance | Cash out
PropertyValue | A number ranging from 97500 - 2000001 | Refinance | Estimated home value
FirstMortgageBalance | A number ranging from 77500 - 2000001 | Refinance | Total mortgage balance
FirstMortgageRate | A number ranging from 2.4 - 11 | Refinance | 1st mortgage interest rate
CurrentFHALoan | Yes<br />No | Refinance | If consumer is currently in a FHA loan
OriginatedBefore | Yes<br />No | Refinance | If loan originated before June 2009
FoundHome | Yes<br />No | Purchase | If consumer has found a home
NewHomeValue | A number ranging from 110000 - 2500000 OR the text: "3000000 or more" | Purchase | Purchase price of new home
PurchaseAgreement | Yes<br />No | Purchase | If consumer has signed a purchase agreement
EstimatedDownPayment | 3.5% down<br />5% down<br />10% down<br />…<br />other | Purchase | Estimated down payment
VeteranMilitary | Yes<br />No | All | If consumer is veteran or active military
FirstName | text | All | Consumer's first name
LastName | text | All | Consumer's last name
Email | text | All | Consumer's email
CellPhone | text | All | Consumer's primary phone number
HomePhone | text | All | Consumer's alternate phone number
Street_Address | text | All | Consumer's street address
PropertyCity | text | All | Consumer's city
PropertyState | 2 letter state abbreviation | All | Consumer's state
Zip | 5 digit zip code | All | Consumer's zip code
rid | numeric | All | The lead's unique identifier
ltv | numeric | All | total mortgage * (100 / property value)
