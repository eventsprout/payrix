
# Tax Form Requests Response

## Structure

`TaxFormRequestsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `merchant` | string\|[MerchantsResponse](../../doc/models/merchants-response.md)\|null | Optional | The identifies of the Merchant requesting the tax document. | getMerchant(): | setMerchant( merchant): void |
| `type` | [`?string(TaxFormTypeEnum)`](../../doc/models/tax-form-type-enum.md) | Optional | The tax document type.<br>Valid Value - `1099k` - **1099k Tax Document.** | getType(): ?string | setType(?string type): void |
| `taxYear` | `?int` | Optional | The tax year for which the document is requested. | getTaxYear(): ?int | setTaxYear(?int taxYear): void |
| `responseCode` | `?int` | Optional | The API call response code. | getResponseCode(): ?int | setResponseCode(?int responseCode): void |

## Example (as JSON)

```json
{
  "id": "id8",
  "created": "created8",
  "modified": "modified6",
  "creator": "String7",
  "modifier": "modifier2"
}
```

