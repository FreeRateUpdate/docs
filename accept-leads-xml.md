## XML Posting Guidelines

This document provides instructions on implementing an XML feed that may be used to immediately notify your CRM system of a lead. The following information outlines the format of the XML that will be sent to you.

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
Street_Address | text | All | Consumer's street address
PropertyCity | text | All | Consumer's city
State | 2 letter state abbreviation | All | Consumer's state
Zip | 5 digit zip code | All | Consumer's zip code
rid | numeric | All | The lead's unique identifier
ltv | numeric | All | total mortgage * (100 / property value)

### Sample Feed
```
<?xml version="1.0"?>
<lead>
  <rid>186052</rid>
  <LoanPurpose>Purchase</LoanPurpose>
  <PropertyType>Single</PropertyType>
  <CreditRating>Good</CreditRating>
  <DesiredRateType>30-Yr Fixed</DesiredRateType>
  <CashOut/>
  <PropertyValue/>
  <FirstMortgageBalance/>
  <FirstMortgageRate/>
  <RateType1/>
  <NewHomeValue>130000</NewHomeValue>
  <EstimatedDownPayment>20% down</EstimatedDownPayment>
  <PropertyUse/>
  <SecondMortgageBalance>0</SecondMortgageBalance>
  <CurrentFHALoan/>
  <OriginatedBefore/>
  <signed_contract>Yes</signed_contract>
  <VeteranMilitary>no</VeteranMilitary>
  <FoundHome>Yes</FoundHome>
  <FirstName>PERSON</FirstName>
  <LastName>SMITH</LastName>
  <Email>person@yahoo.com</Email>
  <Street_Address/>
  <PropertyCity>Cypress</PropertyCity>
  <State>TX</State>
  <Zip>77429</Zip>
  <CellPhone>5555559861</CellPhone>
  <Desired_Loan_Amount>104000</Desired_Loan_Amount>
  <ltv>0</ltv>
</lead>
```
