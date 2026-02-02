
# Fee Modifiers Post Request

## Structure

`FeeModifiersPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fee` | `string` | Required | The identifier of the Fee that this Fee Modifier applies. | getFee(): string | setFee(string fee): void |
| `entity` | `?string` | Optional | The identifier of the Entity that this Fee Modifier applies for. | getEntity(): ?string | setEntity(?string entity): void |
| `org` | `?string` | Optional | The identifier of the Org this Fee Modifiers should apply for on behalf of the Entity identified in the value of the 'entity' field.<br>This field is optional. If it is set, then the Fee Modifier is applied to this Org instead. | getOrg(): ?string | setOrg(?string org): void |
| `fromentity` | `?string` | Optional | The identifier of the Entity who should pay this Fee on behalf of the Entity identified in the value of the 'entity' or 'org' field.<br>This field is optional. If it is set, then the Fee is charged to this Entity instead. | getFromentity(): ?string | setFromentity(?string fromentity): void |
| `markupUm` | [`?int(FeeModifiersMarkupUmEnum)`](../../doc/models/fee-modifiers-markup-um-enum.md) | Optional | The unit of measure for the markup amount for the Fee.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Fixed Amount.** Specified in the 'markupAmount' field as an integer in cents.<br>- `2` - **Percentage.** Specified in the 'markupAmount' field in basis points.<br></details><br> | getMarkupUm(): ?int | setMarkupUm(?int markupUm): void |
| `markupAmount` | `?int` | Optional | The total amount of the markup value for this Fee.<br>The units used in this field are determined by the value of the 'markupUm' field on the Fee. If the 'markupUm' field is set to 'percentage', then this field specifies the Fee percentage to levy in basis points. If the 'markupUm' field is set to 'actual', then this field specifies the markup amount in cents. | getMarkupAmount(): ?int | setMarkupAmount(?int markupAmount): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "fee": "t1_fee_6809dd0aa16f89a3f28ca98",
  "entity": "t1_ent_00c2b1a6102ffdd33f00000",
  "org": "t1_org_00b2ac11ed8bed97fb80000",
  "fromentity": "t1_ent_0088c831a31ca8841c80000",
  "markupUm": 1,
  "markupAmount": 0,
  "inactive": 0,
  "frozen": 0
}
```

