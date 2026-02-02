
# Reserves Post Request

## Structure

`ReservesPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `string` | Required | The Login that owns this resource. | getLogin(): string | setLogin(string login): void |
| `org` | string\|[OrgsPostRequest](../../doc/models/orgs-post-request.md)\|null | Optional | The identifier of the Org that this Reserve's resource applies to. If you set this field, then the Reserve applies to all Entities in the Org. | getOrg(): | setOrg( org): void |
| `division` | `?string` | Optional | The division on which this reserve applies. | getDivision(): ?string | setDivision(?string division): void |
| `partition` | `?string` | Optional | The partition on which this reserve applies. | getPartition(): ?string | setPartition(?string partition): void |
| `level` | [`?string(ReservesLevelEnum)`](../../doc/models/reserves-level-enum.md) | Optional | The hierarchical level for this reserve setting.<br><br><details><br><summary>Valid Values</summary><br>- `admin` - **Admin User.**<br>- `division` - **Division-level User.**<br>- `merchant` - **Merchant-level User.**<br>- `partition` - **Partition-level User.**<br></details><br> | getLevel(): ?string | setLevel(?string level): void |
| `entity` | `?string` | Optional | The identifier of the Entity that this Reserve applies to. | getEntity(): ?string | setEntity(?string entity): void |
| `hold` | `?string` | Optional | The entity hold from which this reserve was generated. | getHold(): ?string | setHold(?string hold): void |
| `name` | `?string` | Optional | The name of this Reserve. This field is stored as a text string and must be between 1 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this Reserve. This field is stored as a text string and must be between 0 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `percent` | `int` | Required | The percentage of funds to reserve, expressed in basis points. For example, 25.3% is expressed as '2530'. | getPercent(): int | setPercent(int percent): void |
| `release` | [`?string(ReservesReleaseEnum)`](../../doc/models/reserves-release-enum.md) | Optional | The schedule that determines when the funds in this Reserve should be released, which can have valid values such as never, days, weeks, months, or years.<br><br><details><br><summary>Valid Values</summary><br>- `never` - **Never.**<br>- `days` - **Daily. The funds are released every day.**<br>- `weeks` - **Weekly. The funds are released every week.**<br>- `months` - **Monthly. The funds are released every month.**<br>- `years` - **Annually. The funds are released every year.**<br></details><br> | getRelease(): ?string | setRelease(?string release): void |
| `releaseFactor` | `?int` | Optional | A multiplier that you can use to adjust the schedule set in the 'release' field, which is specified as an integer and its value determines how the schedule is multiplied.<br><br>**Default**: `1` | getReleaseFactor(): ?int | setReleaseFactor(?int releaseFactor): void |
| `start` | `?int` | Optional | The date on which this Reserve resource should start reserving funds from the Entity or Org. The date is specified as an eight digit string in YYYYMMDD format, for example, '20160120' for January 20, 2016. | getStart(): ?int | setStart(?int start): void |
| `finish` | `?int` | Optional | The date on which this Reserve resource should stop reserving funds from the Entity or Org. The date is specified as an eight digit string in YYYYMMDD format, for example, '20160120' for January 20, 2016. | getFinish(): ?int | setFinish(?int finish): void |
| `max` | `?int` | Optional | The maximum amount to reserve. | getMax(): ?int | setMax(?int max): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "login": "t1_log_611e6ca320fae7afab2f256",
  "org": "t1_org_5fada4629c317f80bc9cb00",
  "division": "t1_div_67b51635da21f7399ce2az0",
  "partition": "t1_ptn_000834d4d504f11234578f0",
  "level": "merchant",
  "entity": "t1_ent_5f9058fe8c8d21ead8f68dc",
  "hold": "t1_hld_66f27fca0236545c4f125d2",
  "name": "Additional Underwriting Review Required",
  "description": "Will release the reserve once all information is verified.",
  "percent": 10000,
  "release": "never",
  "releaseFactor": 1,
  "start": 20160120,
  "finish": 20160120,
  "max": 0,
  "inactive": 0,
  "frozen": 0
}
```

