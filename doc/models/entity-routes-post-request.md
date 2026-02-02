
# Entity Routes Post Request

## Structure

`EntityRoutesPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `string` | Required | The Login that owns this EntityRoute. | getLogin(): string | setLogin(string login): void |
| `division` | `?string` | Optional | Division ID in which the entity route is associated. | getDivision(): ?string | setDivision(?string division): void |
| `entity` | `?string` | Optional | The identifier of the Entity that this entityRoute applies to. | getEntity(): ?string | setEntity(?string entity): void |
| `org` | `?string` | Optional | The identifier of the Org that this entityRoute applies to. | getOrg(): ?string | setOrg(?string org): void |
| `partition` | `?string` | Optional | ID of the partition in which this entity operates. | getPartition(): ?string | setPartition(?string partition): void |
| `platform` | [`string(EntityPlatformEnum)`](../../doc/models/entity-platform-enum.md) | Required | The processor that issued this terminalTxnRef.<br><br><details><br><summary>Valid Values</summary><br>- `APPLE` - **APPLE**<br>- `ELAVON` - **ELAVON**<br>- `FIRSTDATA` - **FIRSTDATA**<br>- `GOOGLE` - **GOOGLE**<br>- `VANTIV` - **VANTIV**<br>- `VCORE` - **VCORE**<br>- `WELLSACH` - **WELLSACH**<br>- `WELLSFARGO` - **WELLSFARGO**<br>- `WFSINGLE` - **WFSINGLE**<br>- `WORLDPAY` - **WORLDPAY**<br>- `TDBANKCA` - **TDBANKCA**<br></details><br> | getPlatform(): string | setPlatform(string platform): void |
| `currency` | [`?string(CurrencyEnum)`](../../doc/models/currency-enum.md) | Optional | The currency in which an entity should board with. This is an optional field that is only required for some platforms. See <a href="https://www.iban.com/currency-codes" target="_blank">Currency codes</a>  for all valid values.<br><br>**Default**: `CurrencyEnum::USD` | getCurrency(): ?string | setCurrency(?string currency): void |
| `fundingCurrency` | [`?string(EntityRoutesFundingCurrencyEnum)`](../../doc/models/entity-routes-funding-currency-enum.md) | Optional | The currency for which this entity will be funded on.<br><br><details><br><summary>Valid Values</summary><br>- `USD` - **US Dollar.**<br>- `CAD` - **Canadian Dollar.**<br></details><br> | getFundingCurrency(): ?string | setFundingCurrency(?string fundingCurrency): void |
| `options` | `?string` | Optional | Whether to disable ACH.<br>This is a JSON field.<br>Accepted values are {"eCheckDisabled": true}. | getOptions(): ?string | setOptions(?string options): void |
| `default` | [`int(EntityDefaultEnum)`](../../doc/models/entity-default-enum.md) | Required | Whether this entityRef is the default one. Default entityRefs will have priority when processing transactions with no MID or Platform set. <details> <summary>Valid Values</summary> - `0` - **Not default.** - `1` - **Default.** </details><br><br>**Default**: `EntityDefaultEnum::NOTDEFAULT` | getDefault(): int | setDefault(int default): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "login": "t1_log_68caacb09a6a14a26e3afd2",
  "division": "t1_div_67b51635da21f7399ce2af0",
  "entity": "t1_ent_68caacb12716c8ab6fdee62",
  "org": "t1_org_67b736ad7d05922343246cf",
  "partition": "t1_ptn_666834d4d504f11234578f0",
  "platform": "VCORE",
  "currency": "USD",
  "fundingCurrency": "USD",
  "options": "{\"addTerminalsEnabled\":false,\"debitPinEnabled\":false,\"debitPinlessEnabled\":true}",
  "default": 1,
  "inactive": 0,
  "frozen": 0
}
```

