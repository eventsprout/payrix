
# Reserves Response

## Structure

`ReservesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that owns this Reserve. | getLogin(): | setLogin( login): void |
| `org` | string\|[OrgsResponse](../../doc/models/orgs-response.md)\|null | Optional | The identifier of the Org that this Reserve's resource applies to. If you set this field, then the Reserve applies to all Entities in the Org. | getOrg(): | setOrg( org): void |
| `division` | string\|[DivisionsResponse](../../doc/models/divisions-response.md)\|null | Optional | The identifier of the Division that this Reserve's resource applies to. | getDivision(): | setDivision( division): void |
| `partition` | string\|[PartitionsResponse](../../doc/models/partitions-response.md)\|null | Optional | The identifier of the Partition that this Reserve's resource applies to. | getPartition(): | setPartition( partition): void |
| `level` | [`?string(ReservesLevelEnum)`](../../doc/models/reserves-level-enum.md) | Optional | The hierarchical level for this reserve setting.<br><br><details><br><summary>Valid Values</summary><br>- `admin` - **Admin User.**<br>- `division` - **Division-level User.**<br>- `merchant` - **Merchant-level User.**<br>- `partition` - **Partition-level User.**<br></details><br> | getLevel(): ?string | setLevel(?string level): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity that this Reserve applies to. | getEntity(): | setEntity( entity): void |
| `hold` | string\|[HoldsResponse](../../doc/models/holds-response.md)\|null | Optional | The identifier of the Entity Hold from which this Reserve was generated. | getHold(): | setHold( hold): void |
| `name` | `?string` | Optional | The name of this Reserve. This field is stored as a text string and must be between 1 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this Reserve. This field is stored as a text string and must be between 0 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `percent` | `?int` | Optional | The percentage of funds to reserve, expressed in basis points. For example, 25.3% is expressed as '2530'. | getPercent(): ?int | setPercent(?int percent): void |
| `release` | [`?string(ReservesReleaseEnum)`](../../doc/models/reserves-release-enum.md) | Optional | The schedule that determines when the funds in this Reserve should be released, which can have valid values such as never, days, weeks, months, or years.<br><br><details><br><summary>Valid Values</summary><br>- `never` - **Never.**<br>- `days` - **Daily. The funds are released every day.**<br>- `weeks` - **Weekly. The funds are released every week.**<br>- `months` - **Monthly. The funds are released every month.**<br>- `years` - **Annually. The funds are released every year.**<br></details><br> | getRelease(): ?string | setRelease(?string release): void |
| `releaseFactor` | `?int` | Optional | A multiplier that you can use to adjust the schedule set in the 'release' field, which is specified as an integer and its value determines how the schedule is multiplied. | getReleaseFactor(): ?int | setReleaseFactor(?int releaseFactor): void |
| `start` | `?int` | Optional | The date on which this Reserve resource should start reserving funds from the Entity or Org. The date is specified as an eight digit string in YYYYMMDD format, for example, '20160120' for January 20, 2016. | getStart(): ?int | setStart(?int start): void |
| `finish` | `?int` | Optional | The date on which this Reserve resource should stop reserving funds from the Entity or Org. The date is specified as an eight digit string in YYYYMMDD format, for example, '20160120' for January 20, 2016. | getFinish(): ?int | setFinish(?int finish): void |
| `max` | `?int` | Optional | The maximum amount to reserve. | getMax(): ?int | setMax(?int max): void |
| `status` | [`?int(ReserveStatusEnum)`](../../doc/models/reserve-status-enum.md) | Optional | The status of reserve.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **The reserve is active.**<br>- `2` - **The reserve is under review.**<br>- `3` - **The reserve is inactive.**<br></details><br> | getStatus(): ?int | setStatus(?int status): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `reserveEntries` | [`?(ReserveEntriesResponse[])`](../../doc/models/reserve-entries-response.md) | Optional | - | getReserveEntries(): ?array | setReserveEntries(?array reserveEntries): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id0",
  "created": "created0",
  "modified": "modified8",
  "creator": "String9",
  "modifier": "modifier4"
}
```

