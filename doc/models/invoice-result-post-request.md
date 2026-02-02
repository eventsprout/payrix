
# Invoice Result Post Request

## Structure

`InvoiceResultPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `invoice` | `string` | Required | The identifier of the Invoice that owns this invoiceResults resource. | getInvoice(): string | setInvoice(string invoice): void |
| `txn` | `?string` | Optional | The identifier of the Transaction associated with this invoiceResults resource. | getTxn(): ?string | setTxn(?string txn): void |
| `status` | [`?string(InvoiceResultStatusEnum)`](../../doc/models/invoice-result-status-enum.md) | Optional | The status of this invoiceResult<br><br><details><br><summary>Valid Values</summary><br>- `success` - **Successfuly processed.**<br>- `failure` - **Failed to process.**<br><br></details><br> | getStatus(): ?string | setStatus(?string status): void |
| `message` | `?string` | Optional | A message that accompanies and describes this invoice result. This field is specified as a text string and must be between 1 and 500 characters long. | getMessage(): ?string | setMessage(?string message): void |
| `shippingFirst` | `?string` | Optional | The shipping first name associated with this InvoiceResult. This field is stored as a text string and must be between 0 and 100 characters long. | getShippingFirst(): ?string | setShippingFirst(?string shippingFirst): void |
| `shippingMiddle` | `?string` | Optional | The shipping middle name associated with this InvoiceResult. This field is stored as a text string and must be between 0 and 100 characters long. | getShippingMiddle(): ?string | setShippingMiddle(?string shippingMiddle): void |
| `shippingLast` | `?string` | Optional | The shipping last name associated with this InvoiceResult. This field is stored as a text string and must be between 0 and 100 characters long. | getShippingLast(): ?string | setShippingLast(?string shippingLast): void |
| `shippingCompany` | `?string` | Optional | The shipping name of the company associated with this InvoiceResult. This field is stored as a text string and must be between 0 and 100 characters long. | getShippingCompany(): ?string | setShippingCompany(?string shippingCompany): void |
| `shippingAddress1` | `?string` | Optional | The shipping first line of the address associated with this InvoiceResult. This field is stored as a text string and must be between 0 and 500 characters long. | getShippingAddress1(): ?string | setShippingAddress1(?string shippingAddress1): void |
| `shippingAddress2` | `?string` | Optional | The shipping second line of the address associated with this InvoiceResult. This field is stored as a text string and must be between 0 and 500 characters long. | getShippingAddress2(): ?string | setShippingAddress2(?string shippingAddress2): void |
| `shippingCity` | `?string` | Optional | The shipping name of the city in the address associated with this InvoiceResult. This field is stored as a text string and must be between 0 and 500 characters long. | getShippingCity(): ?string | setShippingCity(?string shippingCity): void |
| `shippingState` | `?string` | Optional | The U.S. state or Canadian province relevant to the address provided here. If the location is within the U.S. and Canada, specify the 2-character postal abbreviation for the state. If the location is outside of the U.S. and Canada, provide the full state name. This field is stored as a text string and must be between 2 and 100 characters long.<br><br><details><br><summary>U.S. States</summary><br> <br> - `AK` - **Alaska (US)**<br> <br> - `AR` - **Arkansas (US)**<br> <br> - `AL` - **Alabama (US)**<br> <br> - `AZ` - **Arizona (US)**<br> <br> - `CA` - **California (US)**<br> <br> - `CO` - **Colorado (US)**<br> <br> - `CT` - **Connecticut (US)**<br> <br> - `DE` - **Delaware (US)**<br> <br> - `FL` - **Florida (US)**<br> <br> - `GA` - **Georgia (US)**<br> <br> - `HI` - **Hawaii (US)**<br> <br> - `IA` - **Iowa (US)**<br> <br> - `ID` - **Idaho (US)**<br> <br> - `IL` - **Illinois (US)**<br> <br> - `IN` - **Indiana (US)**<br> <br> - `KY` - **Kentucky (US)**<br> <br> - `KS` - **Kansas (US)**<br> <br> - `LA` - **Louisiana (US)**<br> <br> - `MA` - **Massachusetts (US)**<br> <br> - `MD` - **Maryland (US)**<br> <br> - `ME` - **Maine (US)**<br> <br> - `MI` - **Michigan (US)**<br> <br> - `MN` - **Minnesota (US)**<br> <br> - `MO` - **Missouri (US)**<br> <br> - `MS` - **Mississippi (US)**<br> <br> - `MT` - **Montana (US)**<br> <br> - `NC` - **North Carolina (US)**<br> <br> - `ND` - **North Dakota (US)**<br> <br> - `NE` - **Nebraska (US)**<br> <br> - `NH` - **New Hampshire (US)**<br> <br> - `NJ` - **New Jersey (US)**<br> <br> - `NM` - **New Mexico (US)**<br> <br> - `NV` - **Nevada (US)**<br> <br> - `NY` - **New York (US)**<br> <br> - `OH` - **Ohio (US)**<br> <br> - `OK`- **Oklahoma (US)**<br> <br> - `OR` - **Oregon (US)**<br> <br> - `PA` - **Pennsylvania (US)**<br> <br> - `RI` - **Rhode Island (US)**<br> <br> - `SC`- **South Carolina (US)**<br> <br> - `SD` - **South Dakota (US)**<br> <br> - `TN` - **Tennessee (US)**<br> <br> - `TX` - **Texas (US)**<br> <br> - `UT` - **Utah (US)**<br> <br> - `VA` - **Virginia (US)**<br> <br> - `VT` - **Vermont (US)**<br> <br> - `WA` - **Washington (US)**<br> <br> - `WI` - **Wisconsin (US)**<br> <br> - `WV` - **West Virginia (US)**<br> <br> - `WY` - **Wyoming (US)**<br> </details><br> <details><br><summary>Canada Provinces and Territories</summary><br> <br> - `AB` - **Alberta (CAN)**<br> <br> - `BC` - **British Columbia (CAN)**<br> <br> - `MB` - **Manitoba (CAN)**<br> <br> - `ON` - **Ontario (CAN)**<br> <br> - `NS` - **Nova Scotia (CAN)**<br> <br> - `NB` - **New Brunswick (CAN)**<br> <br> - `NL` - **Newfoundland and Labrador (CAN)**<br> <br> - `NT` - **Northwest Territories (CAN)**<br> <br> - `NU` - **Nunavut (CAN)**<br> <br> - `PE` - **Prince Edward Island (CAN)**<br> <br> - `QC` - **Quebec (CAN)**<br> <br> - `SK` - **Saskatchewan (CAN)**<br> <br> - `YT` - **Yukon (CAN)**<br> </details><br> | getShippingState(): ?string | setShippingState(?string shippingState): void |
| `shippingZip` | `?string` | Optional | The shipping zip code in the address associated with this InvoiceResult. This field is stored as a text string and must be between 1 and 20 characters long. | getShippingZip(): ?string | setShippingZip(?string shippingZip): void |
| `shippingCountry` | [`?string(CountryEnum)`](../../doc/models/country-enum.md) | Optional | The shipping country associated with this InvoiceResult, valid values being the 3-letter ISO code for the country. | getShippingCountry(): ?string | setShippingCountry(?string shippingCountry): void |
| `shippingPhone` | `?string` | Optional | The shipping phone number associated with this InvoiceResult. This field is stored as a text string and must be between 5 and 15 characters long. | getShippingPhone(): ?string | setShippingPhone(?string shippingPhone): void |
| `shippingFax` | `?string` | Optional | The shipping fax number associated with this InvoiceResult, stored as a text string and must be between 5 and 15 characters long. | getShippingFax(): ?string | setShippingFax(?string shippingFax): void |
| `authorization` | `?string` | Optional | The authorization text the customer agreed to when making this payment. | getAuthorization(): ?string | setAuthorization(?string authorization): void |
| `authorizationData` | `?string` | Optional | Replacement data for replaceable strings in the authorization text. | getAuthorizationData(): ?string | setAuthorizationData(?string authorizationData): void |
| `signature` | `?string` | Optional | The signature on file for the customer’s authorization acceptance. | getSignature(): ?string | setSignature(?string signature): void |

## Example (as JSON)

```json
{
  "invoice": "t1_inv_00b62cb82db90057aae4157",
  "txn": "p1_txn_67b7c41d9d166b99ac02b36",
  "status": "success",
  "message": "Invoice Paid",
  "shippingFirst": "John",
  "shippingMiddle": "M",
  "shippingLast": "Doe",
  "shippingCompany": "Doe Shippin Co.",
  "shippingAddress1": "123 Mai st.",
  "shippingAddress2": "Suite 10",
  "shippingCity": "Springfield",
  "shippingState": "TX",
  "shippingZip": "62701",
  "shippingCountry": "USA",
  "shippingPhone": "+1123456784",
  "shippingFax": "+1123456784",
  "authorization": "Test Authorization with a field name = :field: and a replace text = :replace:",
  "authorizationData": "{\"field\":\"field\", \"replace\":\"replace\"}",
  "signature": "/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAYEBQYFBAYGBQYHBwYIChAKCgkJChQODwwQFxQYGBcUFhYaHSUfGhsjHBYWICwgIyYnKSop"
}
```

