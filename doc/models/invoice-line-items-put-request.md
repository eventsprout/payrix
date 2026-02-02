
# Invoice Line Items Put Request

## Structure

`InvoiceLineItemsPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `invoice` | `?string` | Optional | The identifier of the Invoice that owns this InvoiceLineItem. | getInvoice(): ?string | setInvoice(?string invoice): void |
| `invoiceItem` | `?string` | Optional | The identifier of the InvoiceItem associated with this InvoiceLineItem. | getInvoiceItem(): ?string | setInvoiceItem(?string invoiceItem): void |
| `quantity` | `?int` | Optional | The quantity purchased for this line item, specified as an integer. | getQuantity(): ?int | setQuantity(?int quantity): void |
| `price` | `?int` | Optional | The price for each item, this field is specified as an integer in cents. | getPrice(): ?int | setPrice(?int price): void |
| `discount` | `?int` | Optional | The discount for the line item, this field is specified as an integer in cents. | getDiscount(): ?int | setDiscount(?int discount): void |

## Example (as JSON)

```json
{
  "invoice": "t1_inv_00b62cb82db90057aae7000",
  "invoiceItem": "t1_ini_00b62cb7d3b3a7e6a841000",
  "quantity": 1,
  "price": 50000,
  "discount": 100
}
```

