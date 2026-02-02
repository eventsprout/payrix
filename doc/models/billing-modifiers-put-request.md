
# Billing Modifiers Put Request

## Structure

`BillingModifiersPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `billing` | `?string` | Optional | The identifier of the Billing that this Billing Modifier applies to. | getBilling(): ?string | setBilling(?string billing): void |
| `entity` | `?string` | Optional | The identifier of the Entity that this Billing Modifier applies to. | getEntity(): ?string | setEntity(?string entity): void |
| `org` | `?string` | Optional | The identifier of the Org that this Billing Modifier applies to. | getOrg(): ?string | setOrg(?string org): void |
| `division` | `?string` | Optional | The identifier of the Division that this Billing Modifier applies to. | getDivision(): ?string | setDivision(?string division): void |
| `partition` | `?string` | Optional | The identifier of the Partition that this Billing Modifier applies to. | getPartition(): ?string | setPartition(?string partition): void |
| `fromentity` | `?string` | Optional | The identifier of the Entity that is responsible for paying this Bill on behalf of the Entity specified in the 'entity' field. | getFromentity(): ?string | setFromentity(?string fromentity): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "billing": "t1_bil_67d9c8a7df33cf77a3e5e4a",
  "entity": "t1_ent_5cd987a735c33bab09e7570",
  "org": "t1_org_67d9c6a866e5d47dca276c3",
  "division": "t1_div_67c56806728fbbf0bae0b00",
  "partition": "t1_ptn_666834d4d504f21414970z0",
  "fromentity": "t1_ent_67d851660b5836731a89ee3",
  "inactive": 0,
  "frozen": 0
}
```

