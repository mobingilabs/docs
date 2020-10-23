# Contents of CSV data

<table>
  <thead>
    <tr>
      <th style="text-align:left">Item</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">BillingGroupID</td>
      <td style="text-align:left">Billing group ID of the billing group.</td>
    </tr>
    <tr>
      <td style="text-align:left">BillingGroupName</td>
      <td style="text-align:left">Billing group name of the billing group.</td>
    </tr>
    <tr>
      <td style="text-align:left">CompanypName</td>
      <td style="text-align:left">Business name of the billing group.</td>
    </tr>
    <tr>
      <td style="text-align:left">CustomerID</td>
      <td style="text-align:left">Account ID of AWS account registered in the billing group.</td>
    </tr>
    <tr>
      <td style="text-align:left">CustomerName</td>
      <td style="text-align:left">Account name of the AWS account registered in the billing group.</td>
    </tr>
    <tr>
      <td style="text-align:left">ServiceType</td>
      <td style="text-align:left">
        <p>Represents the type of service. One of Account, Product, or Service is
          displayed.
          <br />
        </p>
        <p>Account... ACCOUNT_TOTAL of ServiceName.
          <br />
        </p>
        <p>Product ... Indicates one of _SUPPORT_BUSINESS_JPY, _SUBSTITUTION_JPY,
          _TOTAL of ServiceName.
          <br />
        </p>
        <p>Service ... Indicates the value of lineItem / ProductCode of CUR.
          <br />
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">ServiceName</td>
      <td style="text-align:left">
        <p>Represents the name of the service.
          <br />
        </p>
        <p>_SUPPORT_BUSINESS_JPY ... AWS support costs (excl. Tax) set in the invoice
          settings of the billing group.
          <br />
        </p>
        <p>_SUBSTITUTION_JPY ... The agency fee (excl. Tax) set in the invoice settings
          of the billing group.
          <br />
        </p>
        <p>_TOTAL ... The total amount of BillingGroup ID (excluding tax).
          <br />
        </p>
        <p>_ACCOUNT_TOTAL ... Total amount per customer ID (excluding tax).
          <br />
        </p>
        <p>Other values ... AWS Cost and Usage Report (CUR) value of lineItem / ProductCode.
          <a
          href="https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/enhanced-lineitem-columns.html">Here</a>is the reference.
            <br />
        </p>
        <p></p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Charge</td>
      <td style="text-align:left">Amount per ServiceName (excluding tax).</td>
    </tr>
    <tr>
      <td style="text-align:left">DiscountCharge</td>
      <td style="text-align:left">Discount amount (excluding tax).</td>
    </tr>
    <tr>
      <td style="text-align:left">DiscountCharge - TaxFree</td>
      <td style="text-align:left">Discount amount (excluding tax).</td>
    </tr>
    <tr>
      <td style="text-align:left">Tax</td>
      <td style="text-align:left">
        <p>Tax.
          <br />
        </p>
        <p>[DiscountCharge with ServiceName &quot; _TOTAL&quot; - TaxFree] * [Consumption
          tax rate set in invoice settings for billing group]
          <br />
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Total</td>
      <td style="text-align:left">
        <p>Total amount of BillingGroup ID (tax included).
          <br />
        </p>
        <p>[DiscountCharge with ServiceName &quot;_TOTAL&quot;] + [Tax]
          <br />
        </p>
      </td>
    </tr>
  </tbody>
</table>

