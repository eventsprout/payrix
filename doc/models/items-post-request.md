
# Items Post Request

## Structure

`ItemsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `txn` | string\|[TxnsPostRequest](../../doc/models/txns-post-request.md) | Required | The txn in which these items have been sold, A single txn may have many items. | getTxn(): | setTxn( txn): void |
| `item` | `string` | Required | This is item resource. | getItem(): string | setItem(string item): void |
| `description` | `?string` | Optional | A description of this Item.<br>This field is stored as a text string and must be between 0 and 500 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `custom` | `?string` | Optional | A custom identifier for this line Item.<br>This field is stored as a text string and must be between 0 and 500 characters long. | getCustom(): ?string | setCustom(?string custom): void |
| `quantity` | `int` | Required | The quantity of this Item included in the Transaction.<br>This field is specified as an integer. | getQuantity(): int | setQuantity(int quantity): void |
| `price` | `int` | Required | The amount charged for this Item.<br>This field is specified as an integer in cents. | getPrice(): int | setPrice(int price): void |
| `um` | `?string` | Optional | The unit of measure for this Item.<br>This field is stored as a text string and must be between 0 and 100 characters long.<br>Examples of units of measure may be: each, kilogram, pound, month. | getUm(): ?string | setUm(?string um): void |
| `total` | `?int` | Optional | The total price for the line item.<br>This field is specified as an integer in cents. | getTotal(): ?int | setTotal(?int total): void |
| `commodityCode` | `?string` | Optional | The commodity code for this Item.<br>This field is stored as a text string and must be between 0 and 12 characters long. | getCommodityCode(): ?string | setCommodityCode(?string commodityCode): void |
| `productCode` | `?string` | Optional | The product code for this Item such as: UPC, catalog number, or inventory number.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getProductCode(): ?string | setProductCode(?string productCode): void |
| `discount` | `?int` | Optional | The discount for the line item.<br>This field is specified as an integer in cents. | getDiscount(): ?int | setDiscount(?int discount): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "txn": "t1_txn_00b483904b280af5316218a",
  "item": "Line Item 21",
  "description": "A description of Item",
  "custom": "Identifier",
  "quantity": 1,
  "price": 471,
  "um": "EACH",
  "total": 471,
  "commodityCode": "9717123",
  "productCode": "Prorated Tenant Protection Fee",
  "discount": 0,
  "inactive": 0,
  "frozen": 0
}
```

