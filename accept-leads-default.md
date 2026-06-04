# Posting Guidelines

This document provides instructions on implementing a feed that may be used to immediately notify your CRM system of a lead. Values are sent under the POST method. The following outlines the format of the data that will be sent to you.

You may receive more fields than listed below in a POST;

### Possible Attributes and Values

| Field                | Possible Values                                                                                | Lead Type | Description                                                                                    |
| -------------------- | ---------------------------------------------------------------------------------------------- | --------- | ---------------------------------------------------------------------------------------------- |
| RequestId            | numeric                                                                                        | Both      | The lead's unique identifier                                                                   |
| UniversalLeadid      | 36 character unique string                                                                     | Both      | Jornaya LeadiD token for the consumer's submission                                             |
| TCPA                 | 40 character unique string                                                                     | Both      | Trusted form certificate                                                                       |
| LoanPurpose          | refinance & home equity<br />purchase                                                          | Both      | The type of lead                                                                               |
| CreditRating         | Excellent<br />Good<br />Fair<br />Poor                                                        | Both      | User's self-assessed credit                                                                    |
| DesiredRateType      | 30-Yr Fixed                                                                                    | Both      | Desired rate type                                                                              |
| PropertyType         | Single<br />Multi<br />Condo<br />Town House<br />Cooperative<br /> Mobile <br /> Manufactured | Both      | Type of home                                                                                   |
| PropertyUse          | primary<br />secondary<br />investment                                                         | Both      | How the property is used                                                                       |
| PropertyValue        | A number ranging from 60000 - 2000001                                                          | Refinance | Estimated home value                                                                           |
| CashOut              | A number ranging from 5000 - 500000, OR the text "500000 or more"                              | Refinance | Requested cash out amount                                                                      |
| MortgageBalance      | A number ranging from 60000-1200000, OR the text of "Over 1200000"                             | Refinance | Current mortgage balance                                                                       |
| CashOutReason        | reduce-debt<br />home-improvement<br />emergency<br />other                                    | Refinance | Consumer's stated reason for requesting cash out. Only present when CashOut is greater than 0. |
| CurrentFHALoan       | yes<br />no                                                                                    | Refinance | If consumer is currently in an FHA loan                                                        |
| CurrentVALoan        | yes<br />no                                                                                    | Both      | If consumer is currently in a VA loan                                                          |
| HomeEquity           | yes <br />no                                                                                   | Refinance | If consumer is requesting a home equity loan                                                   |
| VeteranMilitary      | yes<br />no                                                                                    | Both      | If consumer is a veteran or active military                                                    |
| FoundHome            | yes<br />no                                                                                    | Purchase  | If consumer has found a home                                                                   |
| PurchaseAgreement    | yes<br />no                                                                                    | Purchase  | If consumer has signed a purchase agreement                                                    |
| DaysFromBuying       | Buying within 90<br />Researching Options                                                      | Purchase  | If consumer plans to purchase within 90 days or just researching                               |
| FirstTimeBuyer       | yes <br />no                                                                                   | Purchase  | If consumer is a first time home buyer                                                         |
| NewHomeValue         | A number ranging from 60000 - 3000000                                                          | Purchase  | Purchase price of new home                                                                     |
| EstimatedDownPayment | numeric percentage (e.g. 3.5, 5, 10, 20, 25)                                                   | Purchase  | Estimated down payment as a percentage of the purchase price                                   |
| DesiredLoanAmount    | numeric                                                                                        | Both      | Loan amount                                                                                    |
| ltv                  | numeric                                                                                        | Both      | Loan to value (total mortgage * 100 / property value)                                          |
| FirstName            | text                                                                                           | Both      | Consumer's first name                                                                          |
| LastName             | text                                                                                           | Both      | Consumer's last name                                                                           |
| Email                | text                                                                                           | Both      | Consumer's email                                                                               |
| CellPhone            | 10 digit numeric                                                                               | Both      | Consumer's primary phone number                                                                |
| HomePhone            | 10 digit numeric (may be blank)                                                                | Both      | Consumer's secondary phone, if provided                                                        |
| StreetAddress        | text                                                                                           | Both      | Consumer's street address                                                                      |
| PropertyCity         | text                                                                                           | Both      | Property city                                                                                  |
| PropertyState        | 2 letter state abbreviation                                                                    | Both      | Property state                                                                                 |
| Zip                  | 5 digit zip code                                                                               | Both      | Property zip code                                                                              |
| Price                | numeric                                                                                        | Both      | Lead price for the receiving client                                                            |

### Notes

* All `yes`/`no` fields are lowercase.
* `PropertyUse` values are lowercase (`primary`, `secondary`, `investment`).
* If consent for a co-applicant or additional contact data was collected, it is not part of this feed.

### Deprecated fields

The following keys may still appear in the POST body for backwards compatibility with legacy integrations. New integrations should ignore them in favor of the fields above.

| Deprecated key | Replaced by |
| -------------- | ----------- |
| rid | RequestId |
| leads_property_value | DesiredLoanAmount |
| Desired_Loan_Amount | DesiredLoanAmount |
| Street_Address | StreetAddress |
| RateType1 | DesiredRateType |
