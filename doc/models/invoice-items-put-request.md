
# Invoice Items Put Request

## Structure

`InvoiceItemsPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `?string` | Optional | The identifier of the Login that owns this Invoiceitem. | getLogin(): ?string | setLogin(?string login): void |
| `item` | `?string` | Optional | The desired name of this InvoiceItem. This field is stored as a text string and must be between 1 and 500 characters long. | getItem(): ?string | setItem(?string item): void |
| `description` | `?string` | Optional | The description of this InvoiceItem. This field is stored as a text string and must be between 0 and 500 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `custom` | `?string` | Optional | A custom field of this InvoiceItem. This field is stored as a text string and must be between 0 and 500 characters long. | getCustom(): ?string | setCustom(?string custom): void |
| `price` | `?int` | Optional | The price of this InvoiceItem is specified as an integer in cents. | getPrice(): ?int | setPrice(?int price): void |
| `um` | `?string` | Optional | The unit of measure of this InvoiceItem is stored as a text string and must be between 0 and 100 characters long; examples of units of measure may be: each, kilogram, pound, month. | getUm(): ?string | setUm(?string um): void |
| `commodityCode` | `?string` | Optional | The commodity code for this InvoiceItem. This field is stored as a text string and must be between 0 and 12 characters long. | getCommodityCode(): ?string | setCommodityCode(?string commodityCode): void |
| `productCode` | `?string` | Optional | The product code for this invoice item such as: UPC, catalog number, or inventory number. This field is stored as a text string and must be between 0 and 100 characters long. | getProductCode(): ?string | setProductCode(?string productCode): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "login": "t1_log_00d514abedbf6f641b7c2f2",
  "item": "Test Custom Links",
  "description": "Test Custom Links",
  "custom": "Sample custom field 1",
  "um": "kilogram",
  "commodityCode": "03000",
  "productCode": "SKU23456",
  "price": 1666,
  "inactive": 0,
  "frozen": 0
}
```

