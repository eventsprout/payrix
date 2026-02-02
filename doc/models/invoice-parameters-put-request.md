
# Invoice Parameters Put Request

## Structure

`InvoiceParametersPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `?string` | Optional | The identifier of the Login that owns this invoiceParameter resource. | getLogin(): ?string | setLogin(?string login): void |
| `entity` | `?string` | Optional | The identifier of the Entity associated with this invoiceParameter. | getEntity(): ?string | setEntity(?string entity): void |
| `division` | `?string` | Optional | The identifier of the Division associated with this invoiceParameter. | getDivision(): ?string | setDivision(?string division): void |
| `org` | `?string` | Optional | The identifier of the Org associated with this invoiceParameter. | getOrg(): ?string | setOrg(?string org): void |
| `partition` | `?string` | Optional | The identifier of the Partition associated with this invoiceParameter. | getPartition(): ?string | setPartition(?string partition): void |
| `locked` | [`?int(InvoiceParameterLockedEnum)`](../../doc/models/invoice-parameter-locked-enum.md) | Optional | Whether this invoiceParameter is locked. If locked, it defaults to the value of the invoiceParameter.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not locked**<br>- `1` - **Locked**<br></details><br>**Default**: `InvoiceParameterLockedEnum::NOTLOCKED`<br> | getLocked(): ?int | setLocked(?int locked): void |
| `type` | [`?string(InvoiceParameterTypeEnum)`](../../doc/models/invoice-parameter-type-enum.md) | Optional | The type of Transaction.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Credit Card Only:** Sale Transaction, processes a sale and charges the customer.<br>- `2` - **Credit Card Only:** Auth Transaction, authorizes and holds the requested total on the credit card.<br>- `3` - **Credit Card Only:** Capture Transaction, finalizes a prior Auth Transaction and charges the customer.<br>- `4` - **Credit Card Only:** Reverse Authorization, reverses a prior Auth or Sale Transaction and releases the credit hold.<br>- `5` - **Credit Card Only:** Refund Transaction, refunds a prior Capture or Sale Transaction (total may be specified for a partial refund).<br>- `7` - **Echeck Only:** Echeck Sale Transaction, sale transaction for ECheck payment.<br>- `8` - **Echeck Only:** ECheck Refund Transaction, refund transaction for prior ECheck Sale Transaction.<br>- `11` - **Echeck Only:** Echeck Redeposit Transaction, attempt to redeposit a prior failed eCheck Sale Transaction.<br>- `12` - **Echeck Only:** Echeck Account Verification Transaction, attempt to verify eCheck payment details.<br></details><br> | getType(): ?string | setType(?string type): void |
| `value` | `?string` | Optional | The value of this type of invoiceParameter. | getValue(): ?string | setValue(?string value): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "login": "t1_log_67c272f9078d060d291fdez",
  "entity": "t1_ent_67c272f920c1724d2709c0b",
  "division": "t1_div_67c56806728fbbf0bae0b00",
  "org": "t1_org_67b736ad7d05922340000cf",
  "partition": "t1_ptn_666834d4d504f11234578f0",
  "locked": 0,
  "type": "apikey",
  "value": "ecfb12e30dcfc1421a2e6c18345cb0a6",
  "inactive": 0,
  "frozen": 0
}
```

