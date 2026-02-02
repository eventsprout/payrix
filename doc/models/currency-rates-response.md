
# Currency Rates Response

## Structure

`CurrencyRatesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that owns this resource. | getLogin(): | setLogin( login): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | If this currency rate relates to an entity, then this field stores the identifier of the Entity. | getEntity(): | setEntity( entity): void |
| `org` | string\|[OrgsResponse](../../doc/models/orgs-response.md)\|null | Optional | If this currency rate relates to an org, then this field stores the identifier of the Org. | getOrg(): | setOrg( org): void |
| `division` | string\|[DivisionsResponse](../../doc/models/divisions-response.md)\|null | Optional | If this currency rate relates to a division, then this field stores the identifier of the Division. | getDivision(): | setDivision( division): void |
| `partition` | string\|[PartitionsResponse](../../doc/models/partitions-response.md)\|null | Optional | If this currency rate relates to a partition, then this field stores the identifier of the Partition. | getPartition(): | setPartition( partition): void |
| `fromCurrency` | [`?string(CurrencyRatesFromCurrencyEnum)`](../../doc/models/currency-rates-from-currency-enum.md) | Optional | The currency that will serve as base for this rate. | getFromCurrency(): ?string | setFromCurrency(?string fromCurrency): void |
| `toCurrency` | [`?string(CurrencyRatesToCurrencyEnum)`](../../doc/models/currency-rates-to-currency-enum.md) | Optional | The currency that the fromCurrency will be converting to. | getToCurrency(): ?string | setToCurrency(?string toCurrency): void |
| `rate` | `?float` | Optional | The rate of this currency in cents(up to three decimal points). | getRate(): ?float | setRate(?float rate): void |
| `start` | `?int` | Optional | The start date that this rate will start to be effective. | getStart(): ?int | setStart(?int start): void |
| `finish` | `?int` | Optional | The finish date that this rate will stop being effective. | getFinish(): ?int | setFinish(?int finish): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

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

