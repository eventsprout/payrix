
# Revenue Boosts Post Request

A request body for creating new networkPaymentManager

## Structure

`RevenueBoostsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `entity` | `string` | Required | The identifier of the Entity that networkPaymentManager is associated with. | getEntity(): string | setEntity(string entity): void |
| `platform` | [`?string(RevenueBoostsPlatformEnum)`](../../doc/models/revenue-boosts-platform-enum.md) | Optional | The platform used to process this transaction.<br>Valid Values : - `VCORE` - **VCORE** | getPlatform(): ?string | setPlatform(?string platform): void |
| `org` | `?string` | Optional | The identifier of the Org (group) that networkPaymentManager is associated with. | getOrg(): ?string | setOrg(?string org): void |
| `division` | `?string` | Optional | The identifier of the Division that networkPaymentManager is associated with. | getDivision(): ?string | setDivision(?string division): void |
| `partition` | `?string` | Optional | The identifier of the Partition that networkPaymentManager is associated with. | getPartition(): ?string | setPartition(?string partition): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "entity": "t1_ent_5a1pf5a1234531155a12345",
  "platform": "VCORE",
  "org": "t1_org_5a1pf5a1234531155a12345",
  "division": "t1_div_67b51635da21f7399ce2af1",
  "partition": "t1_ptn_666834d4d504f11234578f5",
  "inactive": 0,
  "frozen": 0
}
```

