
# Adjustments Response

## Structure

`AdjustmentsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getLogin(): | setLogin( login): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity associated with this Account. | getEntity(): | setEntity( entity): void |
| `fromentity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The applicable Entity for this Adjustment.<br>This field is an optional field. | getFromentity(): | setFromentity( fromentity): void |
| `onentity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity associated with this Adjustment. | getOnentity(): | setOnentity( onentity): void |
| `disbursement` | string\|[DisbursementsResponse](../../doc/models/disbursements-response.md)\|null | Optional | The identifier of the Disbursement associated with this Adjustment. | getDisbursement(): | setDisbursement( disbursement): void |
| `description` | `?string` | Optional | The description of this Decision Rule.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `amount` | `?float` | Optional | The amount of the Adjustment, This field is specified in cents(up to three decimal points). | getAmount(): ?float | setAmount(?float amount): void |
| `currency` | [`?string(CurrencyEnum)`](../../doc/models/currency-enum.md) | Optional | The currency for the amount of this resource. See <a href="https://www.iban.com/currency-codes" target="_blank">Currency codes</a>  for all valid values.<br><br>**Default**: `CurrencyEnum::USD` | getCurrency(): ?string | setCurrency(?string currency): void |
| `funding` | string\|[EntityRefsResponse](../../doc/models/entity-refs-response.md)\|null | Optional | The ID of the fund which the disbursement’s movement applies. | getFunding(): | setFunding( funding): void |
| `platform` | `?string` | Optional | The processor that issued this terminalTxnRef.<br><br><details><br><summary>Valid Values</summary><br>- `APPLE` - **Apple Payment Processor**<br>- `ELAVON` - **ELAVON Payment Processor**<br>- `FIRSTDATA` - **FirstData Payment Processor**<br>- `GOOGLE` - **Google Payment Processor**<br>- `VANTIV` - **WorldPay / Vantiv eComm Payment Processor (VAP)**<br>- `VCORE` - **WorldPay / Vantiv Core Payment Processor**<br>- `WELLSACH` - **Wells Fargo Merchant Services Payment Processor (ACH)**<br>- `WELLSFARGO` - **Wells Fargo Merchant Services Payment Processor**<br>- `WFSINGLE` - **Wells Fargo Single Payment Processor**<br>- `WORLDPAY` - **WORLDPAY**<br>- `TDBANKCA` - **TDBANKCA**<br></details><br> | getPlatform(): ?string | setPlatform(?string platform): void |
| `fbo` | `?string` | Optional | FBO account (For-Benefit-Of account) identifier. | getFbo(): ?string | setFbo(?string fbo): void |
| `entry` | [`?EntriesResponse`](../../doc/models/entries-response.md) | Optional | - | getEntry(): ?EntriesResponse | setEntry(?EntriesResponse entry): void |
| `entryOrigins` | [`?(EntryOriginsResponse[])`](../../doc/models/entry-origins-response.md) | Optional | - | getEntryOrigins(): ?array | setEntryOrigins(?array entryOrigins): void |
| `pendingEntry` | [`?PendingEntriesResponse`](../../doc/models/pending-entries-response.md) | Optional | - | getPendingEntry(): ?PendingEntriesResponse | setPendingEntry(?PendingEntriesResponse pendingEntry): void |

## Example (as JSON)

```json
{
  "currency": "USD",
  "id": "id6",
  "created": "created6",
  "modified": "modified4",
  "creator": "String5",
  "modifier": "modifier0"
}
```

