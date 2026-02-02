
# Invoice Parameters Response

## Structure

`InvoiceParametersResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that owns this invoiceParameter resource. | getLogin(): | setLogin( login): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity associated with this invoiceParameter. | getEntity(): | setEntity( entity): void |
| `org` | string\|[OrgsResponse](../../doc/models/orgs-response.md)\|null | Optional | The identifier of the Org associated with this invoiceParameter. | getOrg(): | setOrg( org): void |
| `division` | string\|[DivisionsResponse](../../doc/models/divisions-response.md)\|null | Optional | The identifier of the Division associated with this invoiceParameter. | getDivision(): | setDivision( division): void |
| `partition` | string\|[PartitionsResponse](../../doc/models/partitions-response.md)\|null | Optional | The identifier of the Partition associated with this invoiceParameter. | getPartition(): | setPartition( partition): void |
| `type` | [`?string(InvoiceParameterTypeEnum)`](../../doc/models/invoice-parameter-type-enum.md) | Optional | The type of Transaction.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Credit Card Only:** Sale Transaction, processes a sale and charges the customer.<br>- `2` - **Credit Card Only:** Auth Transaction, authorizes and holds the requested total on the credit card.<br>- `3` - **Credit Card Only:** Capture Transaction, finalizes a prior Auth Transaction and charges the customer.<br>- `4` - **Credit Card Only:** Reverse Authorization, reverses a prior Auth or Sale Transaction and releases the credit hold.<br>- `5` - **Credit Card Only:** Refund Transaction, refunds a prior Capture or Sale Transaction (total may be specified for a partial refund).<br>- `7` - **Echeck Only:** Echeck Sale Transaction, sale transaction for ECheck payment.<br>- `8` - **Echeck Only:** ECheck Refund Transaction, refund transaction for prior ECheck Sale Transaction.<br>- `11` - **Echeck Only:** Echeck Redeposit Transaction, attempt to redeposit a prior failed eCheck Sale Transaction.<br>- `12` - **Echeck Only:** Echeck Account Verification Transaction, attempt to verify eCheck payment details.<br></details><br> | getType(): ?string | setType(?string type): void |
| `value` | `?string` | Optional | The value of this type of invoiceParameter. | getValue(): ?string | setValue(?string value): void |
| `locked` | [`?int(InvoiceParameterLockedEnum)`](../../doc/models/invoice-parameter-locked-enum.md) | Optional | Whether this invoiceParameter is locked. If locked, it defaults to the value of the invoiceParameter.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not locked**<br>- `1` - **Locked**<br></details><br>**Default**: `InvoiceParameterLockedEnum::NOTLOCKED`<br> | getLocked(): ?int | setLocked(?int locked): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "locked": 0,
  "inactive": 0,
  "frozen": 0,
  "id": "id0",
  "created": "created0",
  "modified": "modified8",
  "creator": "String9",
  "modifier": "modifier4"
}
```

