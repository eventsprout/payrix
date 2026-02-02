
# Items Response

## Structure

`ItemsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `txn` | string\|[TxnsResponse](../../doc/models/txns-response.md)\|null | Optional | The txn in which these items have been sold, A single txn may have many items. | getTxn(): | setTxn( txn): void |
| `item` | `?string` | Optional | The SKU, short name or title of the item sold. | getItem(): ?string | setItem(?string item): void |
| `description` | `?string` | Optional | A description of this Item. This field is stored as a text string and must be between 0 and 500 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `custom` | `?string` | Optional | A custom identifier for this line Item. This field is stored as a text string and must be between 0 and 500 characters long. | getCustom(): ?string | setCustom(?string custom): void |
| `um` | `?string` | Optional | The unit of measure for this Item. This field is stored as a text string and must be between 0 and 100 characters long. Examples of units of measure may be: each, kilogram, pound, month. | getUm(): ?string | setUm(?string um): void |
| `commodityCode` | `?string` | Optional | The commodity code for this Item. This field is stored as a text string and must be between 0 and 12 characters long. | getCommodityCode(): ?string | setCommodityCode(?string commodityCode): void |
| `productCode` | `?string` | Optional | The product code for this Item such as: UPC, catalog number, or inventory number. This field is stored as a text string and must be between 0 and 100 characters long. | getProductCode(): ?string | setProductCode(?string productCode): void |
| `quantity` | `?int` | Optional | The quantity of this Item included in the Transaction. This field is specified as an integer. | getQuantity(): ?int | setQuantity(?int quantity): void |
| `price` | `?int` | Optional | The amount charged for this Item. This field is specified as an integer in cents. | getPrice(): ?int | setPrice(?int price): void |
| `total` | `?int` | Optional | The total price for the line item. This field is specified as an integer in cents. | getTotal(): ?int | setTotal(?int total): void |
| `discount` | `?int` | Optional | The discount for the line item. This field is specified as an integer in cents. | getDiscount(): ?int | setDiscount(?int discount): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id2",
  "created": "created8",
  "modified": "modified0",
  "creator": "String1",
  "modifier": "modifier4"
}
```

