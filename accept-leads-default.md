# Posting Guidelines

This document provides instructions on implementing a feed that may be used to immediately notify your CRM system of a lead. Values are sent under the POST method. The following outlines the format of the data that will be sent to you.

You may receive more fields than listed below in a POST;

### Possible Attributes and Values

| Field                | Possible Values                                                                                | Lead Type | Description                                                                                    |
| -------------------- | ---------------------------------------------------------------------------------------------- | --------- | ---------------------------------------------------------------------------------------------- |
| RequestId            | numeric                                                                                        | All       | The lead's unique identifier                                                                   |
| UniversalLeadid      | 36 character unique string                                                                     | All       | Jornaya LeadiD token for the consumer's submission                                             |
| TCPA                 | 40 character unique string                                                                     | All       | Trusted form certificate                                                                       |
| LoanPurpose          | refinance & home equity<br />purchase                                                          | All       | The type of lead                                                                               |
| CreditRating         | Excellent<br />Good<br />Fair<br />Poor                                                        | All       | User's self-assessed credit                                                                    |
| DesiredRateType      | 30-Yr Fixed                                                                                    | All       | Desired rate type                                                                              |
| PropertyType         | Single<br />Multi<br />Condo<br />Town House<br />Cooperative<br /> Mobile <br /> Manufactured | All       | Type of home                                                                                   |
| PropertyUse          | primary<br />secondary<br />investment                                                         | All       | How the property is used                                                                       |
| PropertyValue        | A number ranging from 60000 - 2000001                                                          | Refinance | Estimated home value                                                                           |
| CashOut              | A number ranging from 5000 - 500000, OR the text "500000 or more"                              | Refinance | Requested cash out amount                                                                      |
| MortgageBalance      | A number ranging from 60000-1200000, OR the text of "Over 1200000"                             | Refinance | Current mortgage balance                                                                       |
| CashOutReason        | reduce-debt<br />home-improvement<br />emergency<br />other                                    | Refinance | Consumer's stated reason for requesting cash out. Only present when CashOut is greater than 0. |
| CurrentFHALoan       | yes<br />no                                                                                    | Refinance | If consumer is currently in an FHA loan                                                        |
| CurrentVALoan        | yes<br />no                                                                                    | All       | If consumer is currently in a VA loan                                                          |
| HomeEquity           | yes <br />no                                                                                   | Refinance | If consumer is requesting a home equity loan                                                   |
| VeteranMilitary      | yes<br />no                                                                                    | All       | If consumer is a veteran or active military                                                    |
| FoundHome            | yes<br />no                                                                                    | Purchase  | If consumer has found a home                                                                   |
| PurchaseAgreement    | yes<br />no                                                                                    | Purchase  | If consumer has signed a purchase agreement                                                    |
| DaysFromBuying       | Buying within 90<br />Researching Options                                                      | Purchase  | If consumer plans to purchase within 90 days or just researching                               |
| FirstTimeBuyer       | yes <br />no                                                                                   | Purchase  | If consumer is a first time home buyer                                                         |
| NewHomeValue         | A number ranging from 60000 - 3000000                                                          | Purchase  | Purchase price of new home                                                                     |
| EstimatedDownPayment | numeric percentage (e.g. 3.5, 5, 10, 20, 25)                                                   | Purchase  | Estimated down payment as a percentage of the purchase price                                   |
| DesiredLoanAmount    | numeric                                                                                        | All       | Loan amount                                                                                    |
| ltv                  | numeric                                                                                        | All       | Loan to value (total mortgage * 100 / property value)                                          |
| FirstName            | text                                                                                           | All       | Consumer's first name                                                                          |
| LastName             | text                                                                                           | All       | Consumer's last name                                                                           |
| Email                | text                                                                                           | All       | Consumer's email                                                                               |
| CellPhone            | 10 digit numeric                                                                               | All       | Consumer's primary phone number                                                                |
| HomePhone            | 10 digit numeric (may be blank)                                                                | All       | Consumer's secondary phone, if provided                                                        |
| StreetAddress        | text                                                                                           | All       | Consumer's street address                                                                      |
| PropertyCity         | text                                                                                           | All       | Property city                                                                                  |
| PropertyState        | 2 letter state abbreviation                                                                    | All       | Property state                                                                                 |
| Zip                  | 5 digit zip code                                                                               | All       | Property zip code                                                                              |
| campaign_id          | numeric (may be blank)                                                                         | All       | Campaign identifier the lead originated from                                                   |
| Price                | numeric                                                                                        | All       | Lead price for the receiving client                                                            |

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
