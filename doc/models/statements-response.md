
# Statements Response

## Structure

`StatementsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `billing` | string\|[BillingsResponse](../../doc/models/billings-response.md)\|null | Optional | The identifier of the Billing of this statement resource. | getBilling(): | setBilling( billing): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The paying entity for which this statement applies. | getEntity(): | setEntity( entity): void |
| `start` | `?int` | Optional | The date on which this Statement period should start. The date is specified as an eight digit string in YYYYMMDD format, for example, '20160120' for January 20, 2016. | getStart(): ?int | setStart(?int start): void |
| `finish` | `?int` | Optional | The date on which this Statement period should finish. The date is specified as an eight digit string in YYYYMMDD format, for example, '20160120' for January 20, 2016. | getFinish(): ?int | setFinish(?int finish): void |
| `status` | [`?string(StatementStatusEnum)`](../../doc/models/statement-status-enum.md) | Optional | The current status of the statement.<br><br><details><br><summary>Valid Values</summary><br>- `pending` - **Statement amount is owed and is pending payment.**<br>- `processing` - **A payment is processing for this statement, pending completion.**<br>- `partiallyPaid` - **The statement was partially paid, some amount is still outstanding.**<br>- `paid` - **The statement was paid in full.**<br>- `partiallyCancelled` - **The statement was partially cancelled, some amount is still outstanding.**<br>- `cancelled` - **The statement was completely cancelled and is no longer due for payment.**<br></details><br>**Default**: `StatementStatusEnum::PENDING`<br> | getStatus(): ?string | setStatus(?string status): void |
| `totalPaid` | `?int` | Optional | The total paid amount for this statement, specified as an integer in cents. | getTotalPaid(): ?int | setTotalPaid(?int totalPaid): void |
| `total` | `?int` | Optional | The total amount for this statement. This field is specified as an integer in cents. | getTotal(): ?int | setTotal(?int total): void |
| `currency` | [`?string(CurrencyEnum)`](../../doc/models/currency-enum.md) | Optional | The currency for this statement. See <a href="https://www.iban.com/currency-codes" target="_blank">Currency codes</a>  for all valid values.<br><br>**Default**: `CurrencyEnum::USD` | getCurrency(): ?string | setCurrency(?string currency): void |
| `forentity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The payee entity of the statement. | getForentity(): | setForentity( forentity): void |
| `disbursements` | [`?(DisbursementsResponse[])`](../../doc/models/disbursements-response.md) | Optional | - | getDisbursements(): ?array | setDisbursements(?array disbursements): void |
| `entries` | [`?(EntriesResponse[])`](../../doc/models/entries-response.md) | Optional | - | getEntries(): ?array | setEntries(?array entries): void |
| `pendingEntries` | [`?(PendingEntriesResponse[])`](../../doc/models/pending-entries-response.md) | Optional | - | getPendingEntries(): ?array | setPendingEntries(?array pendingEntries): void |
| `statementEntries` | [`?(StatementEntriesResponse[])`](../../doc/models/statement-entries-response.md) | Optional | - | getStatementEntries(): ?array | setStatementEntries(?array statementEntries): void |
| `txns` | [`?(TxnsResponse[])`](../../doc/models/txns-response.md) | Optional | - | getTxns(): ?array | setTxns(?array txns): void |

## Example (as JSON)

```json
{
  "status": "pending",
  "currency": "USD",
  "id": "id8",
  "created": "created8",
  "modified": "modified6",
  "creator": "String7",
  "modifier": "modifier2"
}
```

