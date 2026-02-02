
# Tax Form Requests Post Request

## Structure

`TaxFormRequestsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchant` | `?string` | Optional | The identifies of the Merchant requesting the tax document. | getMerchant(): ?string | setMerchant(?string merchant): void |
| `type` | [`?string(TaxFormTypeEnum)`](../../doc/models/tax-form-type-enum.md) | Optional | The tax document type.<br>Valid Value - `1099k` - **1099k Tax Document.** | getType(): ?string | setType(?string type): void |
| `taxYear` | `?int` | Optional | The tax year for which the document is requested. | getTaxYear(): ?int | setTaxYear(?int taxYear): void |
| `responseCode` | `?int` | Optional | The API call response code. | getResponseCode(): ?int | setResponseCode(?int responseCode): void |

## Example (as JSON)

```json
{
  "merchant": "t1_mer_6705400c6dbd095b4cb0000",
  "type": "1099k",
  "taxYear": 2024,
  "responseCode": 500
}
```

