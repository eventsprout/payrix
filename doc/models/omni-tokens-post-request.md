
# Omni Tokens Post Request

## Structure

`OmniTokensPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `enablementDate` | `?string` | Optional | The Date and time when an entity was enabled for omniTokens.\nThe date is specified as an eight digit string in YYYY-MM-DD hh:mm:ss format, for example, '2023-06-01 01:00:00' for June 01, 2023. 1:00 am.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}` | getEnablementDate(): ?string | setEnablementDate(?string enablementDate): void |
| `org` | `?string` | Optional | The identifier of the Org (group) that omniTokens is associated to. | getOrg(): ?string | setOrg(?string org): void |
| `division` | `?string` | Optional | The identifier of the Division that omniTokens  is associated to. | getDivision(): ?string | setDivision(?string division): void |
| `partition` | `?string` | Optional | The identifier of the Partition that omniTokens is associated to. | getPartition(): ?string | setPartition(?string partition): void |
| `entity` | `?string` | Optional | The identifier of the Entity that this omniTokens is associated to. | getEntity(): ?string | setEntity(?string entity): void |
| `platform` | [`?string(PlatformModelEnum)`](../../doc/models/platform-model-enum.md) | Optional | The platform used to process this resource.<br><br><details><br><summary>Valid Values</summary><br>- `APPLE` - **The Apple Payment Processor.**<br>- `ELAVON` - **The Elavon processor.**<br>- `FIRSTDATA` - **The FirstData processor.**<br>- `GOOGLE` - **The Google Payment Processor.**<br>- `VANTIV` - **The WorldPay (aka Vantiv or Litle) eComm (aka VAP) processor.**<br>- `VCORE` - **The WorldPay (aka Vantiv) Core processor.**<br>- `TDBANKCA` - **External funding with TD Bank Canada via the Operating Account.**<br>- `WELLSACH` - **The Wells Fargo ACH processor.**<br>- `WELLSFARGO` - **The Wells Fargo Merchant Services processor.**<br>- `WFSINGLE` - **The WFSINGLE processor.**<br>- `WORLDPAY` - **The WORLDPAY processor.**<br></details><br> | getPlatform(): ?string | setPlatform(?string platform): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `deleted` | `?string` | Optional | The date and time at which this resource was deleted.\nThe date is specified as an eight digit string in YYYY-MM-DD hh:mm:ss format, for example, '2023-06-01 01:00:00' for June 01, 2023. 1:00 am.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}` | getDeleted(): ?string | setDeleted(?string deleted): void |
| `deleter` | `?string` | Optional | The id of user who deleted the omniToken. | getDeleter(): ?string | setDeleter(?string deleter): void |

## Example (as JSON)

```json
{
  "enablementDate": "2025-04-24 02:35:04",
  "org": "t1_org_5b0e08025ec790d3f9b8c00",
  "division": "t1_div_67c56806728fbbf0bae0b00",
  "partition": "t1_ptn_666834d4d504f21414978z0",
  "entity": "t1_ent_6809db6dd78923dadbfd904",
  "platform": "VCORE",
  "inactive": 0,
  "frozen": 0,
  "deleted": "2025-04-24 02:35:04",
  "deleter": ""
}
```

