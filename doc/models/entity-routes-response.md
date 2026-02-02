
# Entity Routes Response

## Structure

`EntityRoutesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The Login that owns this EntityRoute. | getLogin(): | setLogin( login): void |
| `division` | string\|[DivisionsResponse](../../doc/models/divisions-response.md)\|null | Optional | Division ID in which the entity route is associated. | getDivision(): | setDivision( division): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity that this entityRoute applies to. | getEntity(): | setEntity( entity): void |
| `org` | string\|[OrgsResponse](../../doc/models/orgs-response.md)\|null | Optional | The identifier of the Org that this entityRoute applies to. | getOrg(): | setOrg( org): void |
| `partition` | string\|[PartitionsResponse](../../doc/models/partitions-response.md)\|null | Optional | ID of the partition in which this entity operates. | getPartition(): | setPartition( partition): void |
| `platform` | [`?string(EntityPlatformEnum)`](../../doc/models/entity-platform-enum.md) | Optional | The processor that issued this terminalTxnRef.<br><br><details><br><summary>Valid Values</summary><br>- `APPLE` - **APPLE**<br>- `ELAVON` - **ELAVON**<br>- `FIRSTDATA` - **FIRSTDATA**<br>- `GOOGLE` - **GOOGLE**<br>- `VANTIV` - **VANTIV**<br>- `VCORE` - **VCORE**<br>- `WELLSACH` - **WELLSACH**<br>- `WELLSFARGO` - **WELLSFARGO**<br>- `WFSINGLE` - **WFSINGLE**<br>- `WORLDPAY` - **WORLDPAY**<br>- `TDBANKCA` - **TDBANKCA**<br></details><br> | getPlatform(): ?string | setPlatform(?string platform): void |
| `currency` | [`?string(CurrencyEnum)`](../../doc/models/currency-enum.md) | Optional | The currency in which an entity should board with. This is an optional field that is only required for some platforms. See <a href="https://www.iban.com/currency-codes" target="_blank">Currency codes</a>  for all valid values.<br><br>**Default**: `CurrencyEnum::USD` | getCurrency(): ?string | setCurrency(?string currency): void |
| `fundingCurrency` | [`?string(EntityRoutesFundingCurrencyEnum)`](../../doc/models/entity-routes-funding-currency-enum.md) | Optional | The currency for which this entity will be funded on.<br><br><details><br><summary>Valid Values</summary><br>- `USD` - **US Dollar.**<br>- `CAD` - **Canadian Dollar.**<br></details><br> | getFundingCurrency(): ?string | setFundingCurrency(?string fundingCurrency): void |
| `options` | `?string` | Optional | Whether to disable ACH.<br>This is a JSON field.<br>Accepted values are {"eCheckDisabled": true}. | getOptions(): ?string | setOptions(?string options): void |
| `default` | [`?int(EntityDefaultEnum)`](../../doc/models/entity-default-enum.md) | Optional | Whether this entityRef is the default one. Default entityRefs will have priority when processing transactions with no MID or Platform set. <details> <summary>Valid Values</summary> - `0` - **Not default.** - `1` - **Default.** </details><br><br>**Default**: `EntityDefaultEnum::NOTDEFAULT` | getDefault(): ?int | setDefault(?int default): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `entityRefs` | [`?(EntityRefsResponse[])`](../../doc/models/entity-refs-response.md) | Optional | - | getEntityRefs(): ?array | setEntityRefs(?array entityRefs): void |

## Example (as JSON)

```json
{
  "platform": "VCORE",
  "currency": "USD",
  "default": 0,
  "inactive": 0,
  "frozen": 0,
  "id": "id0",
  "created": "created0",
  "modified": "modified8",
  "creator": "String9",
  "modifier": "modifier4"
}
```

