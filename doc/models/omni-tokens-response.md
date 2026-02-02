
# Omni Tokens Response

## Structure

`OmniTokensResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `enablementDate` | `?string` | Optional | The Date and time when an entity was enabled for omniTokens.\nThe date is specified as an eight digit string in YYYY-MM-DD hh:mm:ss format, for example, '2023-06-01 01:00:00' for June 01, 2023. 1:00 am.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}` | getEnablementDate(): ?string | setEnablementDate(?string enablementDate): void |
| `org` | string\|[OrgsResponse](../../doc/models/orgs-response.md)\|null | Optional | The identifier of the Org (group) that omniTokens is associated to. | getOrg(): | setOrg( org): void |
| `division` | string\|[DivisionsResponse](../../doc/models/divisions-response.md)\|null | Optional | The identifier of the Division that omniTokens is associated to. | getDivision(): | setDivision( division): void |
| `partition` | string\|[PartitionsResponse](../../doc/models/partitions-response.md)\|null | Optional | The identifier of the Partition that omniTokens is associated to. | getPartition(): | setPartition( partition): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity that this omniTokens is associated to. | getEntity(): | setEntity( entity): void |
| `platform` | [`?string(PlatformModelEnum)`](../../doc/models/platform-model-enum.md) | Optional | The platform used to process this resource.<br><br><details><br><summary>Valid Values</summary><br>- `APPLE` - **The Apple Payment Processor.**<br>- `ELAVON` - **The Elavon processor.**<br>- `FIRSTDATA` - **The FirstData processor.**<br>- `GOOGLE` - **The Google Payment Processor.**<br>- `VANTIV` - **The WorldPay (aka Vantiv or Litle) eComm (aka VAP) processor.**<br>- `VCORE` - **The WorldPay (aka Vantiv) Core processor.**<br>- `TDBANKCA` - **External funding with TD Bank Canada via the Operating Account.**<br>- `WELLSACH` - **The Wells Fargo ACH processor.**<br>- `WELLSFARGO` - **The Wells Fargo Merchant Services processor.**<br>- `WFSINGLE` - **The WFSINGLE processor.**<br>- `WORLDPAY` - **The WORLDPAY processor.**<br></details><br> | getPlatform(): ?string | setPlatform(?string platform): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `deleted` | `?string` | Optional | The date and time at which this resource was deleted.\nThe date is specified as an eight digit string in YYYY-MM-DD hh:mm:ss format, for example, '2023-06-01 01:00:00' for June 01, 2023. 1:00 am.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}` | getDeleted(): ?string | setDeleted(?string deleted): void |
| `deleter` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the User who deleted the omniToken. | getDeleter(): | setDeleter( deleter): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id2",
  "created": "created2",
  "modified": "modified0",
  "creator": "String1",
  "modifier": "modifier6"
}
```

