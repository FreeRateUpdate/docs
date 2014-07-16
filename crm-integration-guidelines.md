## FreeRateUpdate.com Mortgage Lead Manager Integration Guidelines

FreeRateUpdate.com provides a CRM system which can receive leads from multiple sources/campaigns. This document provides instructions and guidelines for properly sending leads to the system.

### Adding a New Campaign

FRU client admins can add and manage multiple lead campaigns using the CRM system by [accessing the Lead Campaigns page](https://leads.freerateupdate.com/account/lead_campaigns).

Adding a new source is as simple as choosing a unique name and pressing the "Create New Link" button. This will generate a unique Post URL for the lead source, e.g., *https://leads.freerateupdate.com/tools/post/gH/pD*

### Posting Leads and Handling Results

Leads should be posted to the URL created and provided by the FRU client using a POST request following the guidelines below. After sending the POST, the resulting output will contain the results of posting the lead, in JSON format, e.g. `{"status":"error","message":"First name is required"}` or `{"status":"success","message":"Lead posted successfully"}`.

`status` will contain either 'success' or 'error' and if there's an error, `message` will contain a text string explaining what went wrong.

### Possible Attributes and Values

<table>

  <thead>
    <tr>
      <th>Field Name</th>
      <th>Required?</th>
      <th>Description</th>
      <th>Accepted Values</th>
    </tr>
  </thead>

  <tbody>

    <tr><td colspan="4" style="text-align: center;"><strong>BORROWER FIELDS</strong></td></tr>

    <tr>
      <td><em>loan_type</em></td>
      <td><strong>Yes</strong></td>
      <td>The type of lead</td>
      <td>
        <ul>
          <li>refinance</li>
          <li>purchase</li>
        </ul>
      </td>
    </tr>

    <tr>
      <td><em>first_name</em></td>
      <td><strong>Yes</strong></td>
      <td>First Name</td>
      <td>Text</td>
    </tr>

    <tr>
      <td><em>last_name</em></td>
      <td><strong>Yes</strong></td>
      <td>Last Name</td>
      <td>Text</td>
    </tr>

    <tr>
      <td><em>email</em></td>
      <td><strong>Yes</strong></td>
      <td>Email Address</td>
      <td>Text</td>
    </tr>

    <tr>
      <td><em>address</em></td>
      <td>No</td>
      <td>Street address of the property</td>
      <td>Text</td>
    </tr>

    <tr>
      <td><em>city</em></td>
      <td>No</td>
      <td>City where the property is located</td>
      <td>Text</td>
    </tr>

    <tr>
      <td><em>state</em></td>
      <td>No</td>
      <td>State where the property is located</td>
      <td><a href="https://www.usps.com/send/official-abbreviations.htm" target="_blank">2-letter US state abbreviation</a></td>
    </tr>

    <tr>
      <td><em>zip</em></td>
      <td>No</td>
      <td>Zip code of the property</td>
      <td>5-digit zip code</td>
    </tr>

    <tr>
      <td><em>primary_phone</em></td>
      <td>No</td>
      <td>Primary phone number</td>
      <td>Text</td>
    </tr>

    <tr>
      <td><em>alt_phone_1</em></td>
      <td>No</td>
      <td>Secondary phone number</td>
      <td>Text</td>
    </tr>

    <tr>
      <td><em>alt_phone_2</em></td>
      <td>No</td>
      <td>Alternate phone number</td>
      <td>Text</td>
    </tr>

    <tr>
      <td><em>dob</em></td>
      <td>No</td>
      <td>Date of birth</td>
      <td>Text</td>
    </tr>

    <tr>
      <td><em>income</em></td>
      <td>No</td>
      <td>Monthly income</td>
      <td>Number</td>
    </tr>

    <tr>
      <td><em>ssn</em></td>
      <td>No</td>
      <td>Social security number</td>
      <td>Text</td>
    </tr>

    <tr>
      <td><em>credit_rating</em></td>
      <td>No</td>
      <td>Credit rating</td>
      <td>
        <ul>
          <li>Excellent</li>
          <li>Good</li>
          <li>Fair</li>
          <li>Poor</li>
        </ul>
      </td>
    </tr>

    <tr>
      <td><em>desired_loan_amount</em></td>
      <td>No</td>
      <td>Desired loan amount</td>
      <td>Number</td>
    </tr>

    <tr>
      <td><em>desired_rate_type</em></td>
      <td>No</td>
      <td>Rate type for the lead</td>
      <td>
        <ul>
          <li>30-Yr Fixed</li>
          <li>15-Yr Fixed</li>
          <li>ARM</li>
          <li>Don't Know</li>
        </ul>
      </td>
    </tr>

    <tr>
      <td><em>cash_out</em></td>
      <td>No</td>
      <td>How much cash out</td>
      <td>Number</td>
    </tr>

    <tr>
      <td><em>property_value</em></td>
      <td>No</td>
      <td>Estimated home value</td>
      <td>Number</td>
    </tr>

    <tr>
      <td><em>first_mortgage_balance</em></td>
      <td>No</td>
      <td>Total mortgage balance</td>
      <td>Number</td>
    </tr>

    <tr>
      <td><em>first_mortgage_rate</em></td>
      <td>No</td>
      <td>1st mortgage interest rate</td>
      <td>Number</td>
    </tr>

    <tr>
      <td><em>existing_rate_type</em></td>
      <td>No</td>
      <td>Existing rate type</td>
      <td>
        <ul>
          <li>30-Yr Fixed</li>
          <li>15-Yr Fixed</li>
          <li>ARM</li>
          <li>Don't Know</li>
        </ul>
      </td>
    </tr>

    <tr>
      <td><em>new_home_value</em></td>
      <td>No</td>
      <td>Purchase price of new home</td>
      <td>Number</td>
    </tr>

    <tr>
      <td><em>estimated_down_payment</em></td>
      <td>No</td>
      <td>Estimated down payment</td>
      <td>Number</td>
    </tr>

    <tr>
      <td><em>property_use</em></td>
      <td>No</td>
      <td>Primary use of the property</td>
      <td>
        <ul>
          <li>primary</li>
          <li>secondary</li>
          <li>investment</li>
        </ul>
      </td>
    </tr>

    <tr>
      <td><em>second_mortgage_balance</em></td>
      <td>No</td>
      <td>Second mortgage balance</td>
      <td>Number</td>
    </tr>

    <tr>
      <td><em>current_fha_loan</em></td>
      <td>No</td>
      <td>If the borrower currently has a FHA loan</td>
      <td>
        <ul>
          <li>Yes</li>
          <li>No</li>
        </ul>
      </td>
    </tr>

    <tr>
      <td><em>originated_before</em></td>
      <td>No</td>
      <td>If the loan originated before June 2009</td>
      <td>
        <ul>
          <li>Yes</li>
          <li>No</li>
        </ul>
      </td>
    </tr>

    <tr>
      <td><em>veteran_military</em></td>
      <td>No</td>
      <td>If the borrower is a veteran or active military</td>
      <td>
        <ul>
          <li>Yes</li>
          <li>No</li>
        </ul>
      </td>
    </tr>

    <tr>
      <td><em>found_home</em></td>
      <td>No</td>
      <td>If the borrower has found a home</td>
      <td>
        <ul>
          <li>Yes</li>
          <li>No</li>
        </ul>
      </td>
    </tr>

    <tr>
      <td><em>signed_purchase_agreement</em></td>
      <td>No</td>
      <td>If the borrower has signed a purchase agreement</td>
      <td>
        <ul>
          <li>Yes</li>
          <li>No</li>
        </ul>
      </td>
    </tr>

    <tr>
      <td><em>current_va_loan</em></td>
      <td>No</td>
      <td>If the borrower currently has a VA loan</td>
      <td>
        <ul>
          <li>Yes</li>
          <li>No</li>
        </ul>
      </td>
    </tr>

    <tr>
      <td><em>property_type</em></td>
      <td>No</td>
      <td>The type of property</td>
      <td>
        <ul>
          <li>Single</li>
          <li>Multi</li>
          <li>Condo</li>
          <li>Town House</li>
          <li>Cooperative</li>
          <li>Mobile</li>
          <li>Manufactured</li>
        </ul>
      </td>
    </tr>

    <tr>
      <td><em>first_interest_rate</em></td>
      <td>No</td>
      <td>First interest rate</td>
      <td>Number</td>
    </tr>

    <tr>
      <td><em>referred_by</em></td>
      <td>No</td>
      <td>Referred by</td>
      <td>Text</td>
    </tr>

    <tr><td colspan="4" style="text-align: center;"><strong>CO-BORROWER FIELDS</strong></td></tr>

    <tr>
      <td><em>cob_first_name</em></td>
      <td>No</td>
      <td>First Name</td>
      <td>Text</td>
    </tr>

    <tr>
      <td><em>cob_last_name</em></td>
      <td>No</td>
      <td>Last Name</td>
      <td>Text</td>
    </tr>

    <tr>
      <td><em>cob_email</em></td>
      <td>No</td>
      <td>Email Address</td>
      <td>Text</td>
    </tr>

    <tr>
      <td><em>cob_primary_phone</em></td>
      <td>No</td>
      <td>Primary phone number</td>
      <td>Text</td>
    </tr>

    <tr>
      <td><em>cob_alt_phone_1</em></td>
      <td>No</td>
      <td>Secondary phone number</td>
      <td>Text</td>
    </tr>

    <tr>
      <td><em>cob_income</em></td>
      <td>No</td>
      <td>Monthly income</td>
      <td>Number</td>
    </tr>

    <tr>
      <td><em>cob_ssn</em></td>
      <td>No</td>
      <td>Social security number</td>
      <td>Text</td>
    </tr>

    <tr>
      <td><em>cob_credit_rating</em></td>
      <td>No</td>
      <td>Credit rating</td>
      <td>
        <ul>
          <li>Excellent</li>
          <li>Good</li>
          <li>Fair</li>
          <li>Poor</li>
        </ul>
      </td>
    </tr>

  </tbody>

</table>
