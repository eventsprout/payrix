
# Entity Refs Post Request

## Structure

`EntityRefsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `entity` | `?string` | Required | The identifier of the Entity that owns this entityRefs resource. | getEntity(): ?string | setEntity(?string entity): void |
| `member` | `?string` | Required | The identifier of the Member associated with this entityRefs resource. Default value is 'null' | getMember(): ?string | setMember(?string member): void |
| `entityRoute` | `?string` | Optional | The original 'entity_route' that routed the merchant onto the platform which then returned this reference information, if applicable. | getEntityRoute(): ?string | setEntityRoute(?string entityRoute): void |
| `ref` | `string` | Required | The reference code itself.<br>This field is stored as a text string and must be between 0 and 50 characters long. | getRef(): string | setRef(string ref): void |
| `stage` | [`string(EntityRefStageEnum)`](../../doc/models/entity-ref-stage-enum.md) | Required | An indicator showing what this terminalRef refers to.<br><br><details><br><summary>Valid Values</summary><br>- `amexCharge` - **Amex Charge.**<br>- `batch` - **Batch.**<br>- `batchSuffix` - **Batch Suffix.**<br>- `boarding` - **Boarding.**<br>- `chain` - **The store chain ID for this Merchant.**<br>- `chargeback` - **Chargeback.**<br>- `companyDebit` - **Company Debit.**<br>- `companyCredit` - **Company Credit.**<br>- `create` - **Terminal Creation.**<br>- `disbursement` - **Disbursement.**<br>- `entity` - **The Entity ID.**<br>- `batchFile` - **Batch File.**<br>- `payoutFile` - **Payout File.**<br>- `frontend` - **Frontend.**<br>- `funding` - **The Payout funding ID for this Merchant.**<br>- `member` - **The member ID for this Member.**<br>- `merchant` - **The Merchant ID.**<br>- `mid` - **The transaction Merchant ID (MID).**<br>- `origId` - **Original ID.**<br>- `store` - **The store ID for this Merchant.**<br>- `software` - **Software.**<br>- `terminal` - **Terminal.**<br>- `displayName` - **Display Name.**<br>- `domain` - **Domain.**<br>- `expressCreds` - **Express Credentials.**<br></details><br> | getStage(): string | setStage(string stage): void |
| `staging` | [`?int(EntityRefStagingEnum)`](../../doc/models/entity-ref-staging-enum.md) | Optional | Allows a merchant to transact under the Staging environment while boarding is in progress, and allows for configuration with valid values such as **Disabled** or **Enabled**.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Disabled**<br>- `1` - **Enabled**<br></details><br> | getStaging(): ?int | setStaging(?int staging): void |
| `platform` | [`string(EntityPlatformEnum)`](../../doc/models/entity-platform-enum.md) | Required | The processor that issued this terminalTxnRef.<br><br><details><br><summary>Valid Values</summary><br>- `APPLE` - **APPLE**<br>- `ELAVON` - **ELAVON**<br>- `FIRSTDATA` - **FIRSTDATA**<br>- `GOOGLE` - **GOOGLE**<br>- `VANTIV` - **VANTIV**<br>- `VCORE` - **VCORE**<br>- `WELLSACH` - **WELLSACH**<br>- `WELLSFARGO` - **WELLSFARGO**<br>- `WFSINGLE` - **WFSINGLE**<br>- `WORLDPAY` - **WORLDPAY**<br>- `TDBANKCA` - **TDBANKCA**<br></details><br> | getPlatform(): string | setPlatform(string platform): void |
| `currency` | [`?string(CurrencyEnum)`](../../doc/models/currency-enum.md) | Optional | The currency of the entityRef. See <a href="https://www.iban.com/currency-codes" target="_blank">Currency codes</a>  for all valid values.<br><br>**Default**: `CurrencyEnum::USD` | getCurrency(): ?string | setCurrency(?string currency): void |
| `fundingCurrency` | [`?string(CurrencyEnum)`](../../doc/models/currency-enum.md) | Optional | The currency for which this entityRefs resource was funded on. See <a href="https://www.iban.com/currency-codes" target="_blank">Currency codes</a>  for all valid values.<br><br>**Default**: `CurrencyEnum::USD` | getFundingCurrency(): ?string | setFundingCurrency(?string fundingCurrency): void |
| `default` | [`?int(EntityDefaultEnum)`](../../doc/models/entity-default-enum.md) | Optional | Whether this entityRef is the default one. Default entityRefs will have priority when processing transactions with no MID or Platform set. <details> <summary>Valid Values</summary> - `0` - **Not default.** - `1` - **Default.** </details><br><br>**Default**: `EntityDefaultEnum::NOTDEFAULT` | getDefault(): ?int | setDefault(?int default): void |
| `fbo` | `?string` | Optional | The FBO from which this entity refers to. | getFbo(): ?string | setFbo(?string fbo): void |
| `options` | `?string` | Optional | A string-JSON of options for this reference value. | getOptions(): ?string | setOptions(?string options): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "entity": "t1_ent_67c6ceba8a94b8cea9664f3",
  "member": "Identifier Of Member",
  "ref": "7c6cec3badbf",
  "stage": "create",
  "staging": 0,
  "platform": "VCORE",
  "default": 0,
  "entityRoute": "g1599c89ae26f9c",
  "currency": "USD",
  "fundingCurrency": "USD",
  "fbo": "For-Benefit-Of account",
  "options": "string-JSON of options",
  "frozen": 0,
  "inactive": 0
}
```

