
# Funds Response

## Structure

`FundsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity that owns this Fund. | getEntity(): | setEntity( entity): void |
| `currency` | [`?string(CurrencyEnum)`](../../doc/models/currency-enum.md) | Optional | The currency of the Fund.<br><br>**Default**: `CurrencyEnum::USD` | getCurrency(): ?string | setCurrency(?string currency): void |
| `reserved` | `?float` | Optional | The amount held in this Fund that is marked as reserved, This field is specified in cents(up to three decimal points). See <a href="https://www.iban.com/currency-codes" target="_blank">Currency codes</a>  for all valid values. | getReserved(): ?float | setReserved(?float reserved): void |
| `pending` | `?float` | Optional | The current funds pending for the entity, This field is specified in cents(up to three decimal points) | getPending(): ?float | setPending(?float pending): void |
| `available` | `?float` | Optional | The amount held in this Fund that is currently available for disbursement, This field is specified in cents(up to three decimal points). | getAvailable(): ?float | setAvailable(?float available): void |
| `total` | `?float` | Optional | The total amount held in this Fund, This field is specified in cents(up to three decimal points). | getTotal(): ?float | setTotal(?float total): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `entityReserves` | [`?(EntityReservesResponse[])`](../../doc/models/entity-reserves-response.md) | Optional | - | getEntityReserves(): ?array | setEntityReserves(?array entityReserves): void |
| `entries` | [`?(EntriesResponse[])`](../../doc/models/entries-response.md) | Optional | - | getEntries(): ?array | setEntries(?array entries): void |
| `reserveEntries` | [`?(ReserveEntriesResponse[])`](../../doc/models/reserve-entries-response.md) | Optional | - | getReserveEntries(): ?array | setReserveEntries(?array reserveEntries): void |
| `fundOrigins` | [`?(FundOriginsResponse[])`](../../doc/models/fund-origins-response.md) | Optional | - | getFundOrigins(): ?array | setFundOrigins(?array fundOrigins): void |

## Example (as JSON)

```json
{
  "currency": "USD",
  "inactive": 0,
  "frozen": 0,
  "id": "id8",
  "created": "created8",
  "modified": "modified6",
  "creator": "String7",
  "modifier": "modifier2"
}
```

