
# Invoice Line Items Response

## Structure

`InvoiceLineItemsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `invoice` | string\|[InvoicesResponse](../../doc/models/invoices-response.md)\|null | Optional | The identifier of the Invoice that owns this InvoiceLineItem. | getInvoice(): | setInvoice( invoice): void |
| `invoiceItem` | string\|[InvoiceItemsResponse](../../doc/models/invoice-items-response.md)\|null | Optional | The identifier of the InvoiceItem associated with this InvoiceLineItem. | getInvoiceItem(): | setInvoiceItem( invoiceItem): void |
| `quantity` | `?int` | Optional | The quantity purchased for this line item, specified as an integer. | getQuantity(): ?int | setQuantity(?int quantity): void |
| `price` | `?int` | Optional | The price for each item, this field is specified as an integer in cents. | getPrice(): ?int | setPrice(?int price): void |
| `discount` | `?int` | Optional | The discount for the line item, this field is specified as an integer in cents. | getDiscount(): ?int | setDiscount(?int discount): void |
| `total` | `?int` | Optional | The total price for the line item, which is specified as an integer in cents. | getTotal(): ?int | setTotal(?int total): void |

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

