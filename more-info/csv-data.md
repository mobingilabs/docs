# CSVデータの中身



<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x9805;&#x76EE;</th>
      <th style="text-align:left">&#x8AAC;&#x660E;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">BillingGroupID</td>
      <td style="text-align:left">&#x8ACB;&#x6C42;&#x30B0;&#x30EB;&#x30FC;&#x30D7;&#x306E;&#x8ACB;&#x6C42;&#x30B0;&#x30EB;&#x30FC;&#x30D7;ID&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">BillingGroupName</td>
      <td style="text-align:left">&#x8ACB;&#x6C42;&#x30B0;&#x30EB;&#x30FC;&#x30D7;&#x306E;&#x8ACB;&#x6C42;&#x30B0;&#x30EB;&#x30FC;&#x30D7;&#x540D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">CompanypName</td>
      <td style="text-align:left">&#x8ACB;&#x6C42;&#x30B0;&#x30EB;&#x30FC;&#x30D7;&#x306E;&#x4F01;&#x696D;&#x540D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">CustomerID</td>
      <td style="text-align:left">&#x8ACB;&#x6C42;&#x30B0;&#x30EB;&#x30FC;&#x30D7;&#x306B;&#x767B;&#x9332;&#x3055;&#x308C;&#x3066;&#x3044;&#x308B;AWS&#x30AB;&#x30A6;&#x30F3;&#x30C8;&#x306E;&#x30A2;&#x30AB;&#x30A6;&#x30F3;&#x30C8;ID&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">CustomerName</td>
      <td style="text-align:left">&#x8ACB;&#x6C42;&#x30B0;&#x30EB;&#x30FC;&#x30D7;&#x306B;&#x767B;&#x9332;&#x3055;&#x308C;&#x3066;&#x3044;&#x308B;AWS&#x30A2;&#x30AB;&#x30A6;&#x30F3;&#x30C8;&#x306E;&#x30A2;&#x30AB;&#x30A6;&#x30F3;&#x30C8;&#x540D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">ServiceType</td>
      <td style="text-align:left">
        <p>&#x30B5;&#x30FC;&#x30D3;&#x30B9;&#x306E;&#x7A2E;&#x985E;&#x3092;&#x8868;&#x3057;&#x307E;&#x3059;&#x3002;Account,
          Product, Service &#x306E;&#x3069;&#x308C;&#x304B;&#x306E;&#x5024;&#x304C;&#x5165;&#x308A;&#x307E;&#x3059;&#x3002;</p>
        <p>Account... ServiceName &#x306E; _ACCOUNT_TOTAL &#x3092;&#x8868;&#x3057;&#x307E;&#x3059;&#x3002;</p>
        <p>Product... ServiceName &#x306E; _SUPPORT_BUSINESS_JPY , _SUBSTITUTION_JPY
          , _TOTAL &#x306E;&#x3069;&#x308C;&#x304B;&#x3092;&#x8868;&#x3057;&#x307E;&#x3059;&#x3002;</p>
        <p>Service... CUR&#x306E;lineItem/ProductCode&#x306E;&#x5024;&#x3092;&#x8868;&#x3057;&#x307E;&#x3059;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">ServiceName</td>
      <td style="text-align:left">
        <p>&#x30B5;&#x30FC;&#x30D3;&#x30B9;&#x306E;&#x540D;&#x524D;&#x3092;&#x8868;&#x3057;&#x307E;&#x3059;&#x3002;</p>
        <p>_SUPPORT_BUSINESS_JPY... &#x8ACB;&#x6C42;&#x30B0;&#x30EB;&#x30FC;&#x30D7;&#x306E;&#x8ACB;&#x6C42;&#x66F8;&#x8A2D;&#x5B9A;&#x3067;&#x8A2D;&#x5B9A;&#x3057;&#x305F;AWS&#x30B5;&#x30DD;&#x30FC;&#x30C8;&#x8CBB;&#x7528;&#xFF08;&#x7A0E;&#x629C;&#xFF09;&#x3002;
          <br
          />_SUBSTITUTION_JPY... &#x8ACB;&#x6C42;&#x30B0;&#x30EB;&#x30FC;&#x30D7;&#x306E;&#x8ACB;&#x6C42;&#x66F8;&#x8A2D;&#x5B9A;&#x3067;&#x8A2D;&#x5B9A;&#x3057;&#x305F;&#x4EE3;&#x884C;&#x624B;&#x6570;&#x6599;&#xFF08;&#x7A0E;&#x629C;&#xFF09;&#x3002;
          <br
          />_TOTAL... BillingGroupID&#x306E;&#x5408;&#x8A08;&#x91D1;&#x984D;&#xFF08;&#x7A0E;&#x629C;&#xFF09;&#x3002;</p>
        <p>_ACCOUNT_TOTAL... CustomerID&#x3054;&#x3068;&#x306E;&#x5408;&#x8A08;&#x91D1;&#x984D;&#xFF08;&#x7A0E;&#x629C;&#xFF09;&#x3002;</p>
        <p>&#x305D;&#x306E;&#x4ED6;&#x306E;&#x5024;... AWS Cost and Usage Report
          &#xFF08;CUR&#xFF09;&#x306E;lineItem/ProductCode&#x306E;&#x5024;&#x3002;
          <a
          href="https://docs.aws.amazon.com/ja_jp/awsaccountbilling/latest/aboutv2/enhanced-lineitem-columns.html">&#x53C2;&#x7167;</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Charge</td>
      <td style="text-align:left">ServiceName&#x3054;&#x3068;&#x306E;&#x91D1;&#x984D;&#xFF08;&#x7A0E;&#x629C;&#xFF09;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">DiscountCharge</td>
      <td style="text-align:left">&#x5272;&#x5F15;&#x91D1;&#x984D;&#xFF08;&#x7A0E;&#x629C;&#xFF09;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">DiscountCharge - TaxFree</td>
      <td style="text-align:left">&#x5272;&#x5F15;&#x91D1;&#x984D;&#xFF08;&#x7A0E;&#x629C;&#xFF09;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">Tax</td>
      <td style="text-align:left">
        <p>&#x7A0E;&#x91D1;&#x3002;</p>
        <p><code>[ServiceName&#x304C;_TOTAL&#x306E;DiscountCharge - TaxFree] * [&#x8ACB;&#x6C42;&#x30B0;&#x30EB;&#x30FC;&#x30D7;&#x306E;&#x8ACB;&#x6C42;&#x66F8;&#x8A2D;&#x5B9A;&#x3067;&#x8A2D;&#x5B9A;&#x3057;&#x305F;&#x6D88;&#x8CBB;&#x7A0E;&#x7387;]</code>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Total</td>
      <td style="text-align:left">
        <p>BillingGroupID&#x306E;&#x5408;&#x8A08;&#x91D1;&#x984D;&#xFF08;&#x7A0E;&#x8FBC;&#xFF09;&#x3002;</p>
        <p><code>[ServiceName&#x304C;_TOTAL&#x306E;DiscountCharge] + [Tax]</code>
        </p>
      </td>
    </tr>
  </tbody>
</table>



