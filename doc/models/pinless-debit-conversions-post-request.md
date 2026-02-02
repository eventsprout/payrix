
# Pinless Debit Conversions Post Request

## Structure

`PinlessDebitConversionsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `enablementDate` | `?string` | Optional | The Date and time when an entity was enabled for pinlessDebitConversion.<br>The date is specified as an eight digit string in YYYY-MM-DD hh:mm:ss format, for example, '2023-06-01 01:00:00' for June 01, 2023. 1:00 am.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}` | getEnablementDate(): ?string | setEnablementDate(?string enablementDate): void |
| `org` | `?string` | Optional | The identifier of the Org (group) that pinlessDebitConversion is associated to. | getOrg(): ?string | setOrg(?string org): void |
| `division` | `?string` | Optional | The identifier of the Division that pinlessDebitConversion is associated to. | getDivision(): ?string | setDivision(?string division): void |
| `partition` | `?string` | Optional | The identifier of the Partition that pinlessDebitConversion is associated to. | getPartition(): ?string | setPartition(?string partition): void |
| `platform` | [`?string(PinlessDebitConversionsPlatformEnum)`](../../doc/models/pinless-debit-conversions-platform-enum.md) | Optional | The platform used to process this transaction. | getPlatform(): ?string | setPlatform(?string platform): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `deleted` | `?string` | Optional | In case resource is deleted, this field will then show the date it occurred.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}` | getDeleted(): ?string | setDeleted(?string deleted): void |
| `deleter` | `?string` | Optional | The id of user who deleted the pinlessDebitConversion. | getDeleter(): ?string | setDeleter(?string deleter): void |

## Example (as JSON)

```json
{
  "enablementDate": "2023-06-01 01:00:00",
  "org": "t1_org_684c7ae33b2d4f98520a79a",
  "division": "t1_div_684c7ae33b2d4f98520a00b",
  "partition": "t1_ptn_666834d4d504f11234578f0",
  "platform": "VCORE",
  "inactive": 0,
  "frozen": 0,
  "deleted": "2023-06-01 01:00:00",
  "deleter": "t1_log_67a4e72ad2ccca060a2fcfb"
}
```

