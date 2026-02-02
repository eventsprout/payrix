
# Disbursements Response

## Structure

`DisbursementsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity that owns this Disbursement. | getEntity(): | setEntity( entity): void |
| `account` | string\|[AccountsResponse](../../doc/models/accounts-response.md)\|null | Optional | The token of the accounts resource used for this Disbursement. | getAccount(): | setAccount( account): void |
| `payment` | `?string` | Optional | A reference to the actual account or card data used for this disbursement. If someone changes the details in their bank account within Payrix Pro, the account token will point to a new account but the payment will always point to the data used for this disbursement. | getPayment(): ?string | setPayment(?string payment): void |
| `payout` | string\|[PayoutsResponse](../../doc/models/payouts-response.md)\|null | Optional | The identifier of the Payout that represents the schedule for this Disbursement. | getPayout(): | setPayout( payout): void |
| `settlement` | string\|[SettlementsResponse](../../doc/models/settlements-response.md)\|null | Optional | The settlement record for this disbursement. | getSettlement(): | setSettlement( settlement): void |
| `statement` | string\|[StatementsResponse](../../doc/models/statements-response.md)\|null | Optional | The identifier of the Statement being paid by this Disbursement. | getStatement(): | setStatement( statement): void |
| `description` | `?string` | Optional | A description of this Disbursement. | getDescription(): ?string | setDescription(?string description): void |
| `secondaryDescriptor` | `?string` | Optional | A secondary descriptor for the ACH transaction sent to the receiving bank. | getSecondaryDescriptor(): ?string | setSecondaryDescriptor(?string secondaryDescriptor): void |
| `amount` | `?int` | Optional | The total amount of this Disbursement. | getAmount(): ?int | setAmount(?int amount): void |
| `returnedAmount` | `?int` | Optional | The amount that has been returned within the disbursement. | getReturnedAmount(): ?int | setReturnedAmount(?int returnedAmount): void |
| `status` | [`?int(DisbursementStatusEnum)`](../../doc/models/disbursement-status-enum.md) | Optional | The current status of this Disbursement<br><br><details><summary>Valid Values</summary><br>- `1` - **Requested.** The request for this Disbursement has been received.<br>- `2` - **Processing.** This Disbursement is being processed to be paid out.<br><br>- `3` - **Processed.** This Disbursement has been paid by ACH to the bank account referenced in the Disbursement data.<br><br>- `4` - **Failed.** A problem occurred and the payment processor has failed to process this Disbursement.<br><br>- `6` - **Returned.** This Disbursement has been returned.<br>  <br>  </details><br> | getStatus(): ?int | setStatus(?int status): void |
| `fundingStatus` | [`?string(DisbursementsFundingStatusEnum)`](../../doc/models/disbursements-funding-status-enum.md) | Optional | Indicates if entries were processed for this Disbursement. <details><summary>Valid Values</summary><br><br>- `pending` - **Pending entry creation and processing.**<br><br>- `processed` - **Entry created and processed.**<br>  <br>  </details><br> | getFundingStatus(): ?string | setFundingStatus(?string fundingStatus): void |
| `processed` | `?string` | Optional | A timestamp indicating when the Disbursement was processed. The format should be YYYY-MM-DD HH:MM:SS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}` | getProcessed(): ?string | setProcessed(?string processed): void |
| `disbursementEntriesStatus` | [`?string(DisbursementsDisbursementEntriesStatusEnum)`](../../doc/models/disbursements-disbursement-entries-status-enum.md) | Optional | The current status of disbursementEntries creation.<br><br><details><br><summary>Valid Values</summary><br>- `pending` - **Pending entry creation and processing.**<br>- `processing` - **Entry is still processing.**<br><br>- `processed` - **Entry created and processed.**<br><br></details><br> | getDisbursementEntriesStatus(): ?string | setDisbursementEntriesStatus(?string disbursementEntriesStatus): void |
| `lastNegativeEntry` | string\|[EntriesResponse](../../doc/models/entries-response.md)\|null | Optional | The last negative Entry processed included in the disbursement. | getLastNegativeEntry(): | setLastNegativeEntry( lastNegativeEntry): void |
| `lastNegativePendingEntry` | string\|Pending[EntriesResponse](../../doc/models/entries-response.md)\|null | Optional | The last negative PendingEntry processed included in the disbursement. | getLastNegativePendingEntry(): | setLastNegativePendingEntry( lastNegativePendingEntry): void |
| `lastPositiveReserveEntry` | string\|Reserve[EntriesResponse](../../doc/models/entries-response.md)\|null | Optional | The last positive ReserveEntry processed included in the disbursement. | getLastPositiveReserveEntry(): | setLastPositiveReserveEntry( lastPositiveReserveEntry): void |
| `lastPositiveEntry` | string\|[EntriesResponse](../../doc/models/entries-response.md)\|null | Optional | The last positive Entry processed included in the disbursement. | getLastPositiveEntry(): | setLastPositiveEntry( lastPositiveEntry): void |
| `lastPositivePendingEntry` | string\|Pending[EntriesResponse](../../doc/models/entries-response.md)\|null | Optional | The last positive PendingEntry processed included in the disbursement. | getLastPositivePendingEntry(): | setLastPositivePendingEntry( lastPositivePendingEntry): void |
| `lastNegativeReserveEntry` | string\|Reserve[EntriesResponse](../../doc/models/entries-response.md)\|null | Optional | The last negative ReserveEntry processed included in the disbursement. | getLastNegativeReserveEntry(): | setLastNegativeReserveEntry( lastNegativeReserveEntry): void |
| `currency` | [`?string(CurrencyEnum)`](../../doc/models/currency-enum.md) | Optional | The currency of this Disbursement. See <a href="https://www.iban.com/currency-codes" target="_blank">Currency codes</a>  for all valid values.<br><br>**Default**: `CurrencyEnum::USD` | getCurrency(): ?string | setCurrency(?string currency): void |
| `expiration` | `?string` | Optional | The expiration date of the related debit account. | getExpiration(): ?string | setExpiration(?string expiration): void |
| `sameDay` | [`?int(DisbursementsSameDayEnum)`](../../doc/models/disbursements-same-day-enum.md) | Optional | Whether sameDay funding is enabled or disabled for this disbursement.<br><br><details><br><summary>Valid Values</summary><br>- `0`  - **Disabled.**<br>- `1` - **Enabled.**<br><br></details><br> | getSameDay(): ?int | setSameDay(?int sameDay): void |
| `adjustments` | [`?(AdjustmentsResponse[])`](../../doc/models/adjustments-response.md) | Optional | - | getAdjustments(): ?array | setAdjustments(?array adjustments): void |
| `disbursementEntries` | [`?(DisbursementEntriesResponse[])`](../../doc/models/disbursement-entries-response.md) | Optional | - | getDisbursementEntries(): ?array | setDisbursementEntries(?array disbursementEntries): void |
| `disbursementResults` | [`?(DisbursementResultsResponse[])`](../../doc/models/disbursement-results-response.md) | Optional | - | getDisbursementResults(): ?array | setDisbursementResults(?array disbursementResults): void |
| `entityReturns` | [`?(EntityReturnsResponse[])`](../../doc/models/entity-returns-response.md) | Optional | - | getEntityReturns(): ?array | setEntityReturns(?array entityReturns): void |
| `entries` | [`?(EntriesResponse[])`](../../doc/models/entries-response.md) | Optional | - | getEntries(): ?array | setEntries(?array entries): void |
| `entryOrigins` | [`?(EntryOriginsResponse[])`](../../doc/models/entry-origins-response.md) | Optional | - | getEntryOrigins(): ?array | setEntryOrigins(?array entryOrigins): void |
| `funding` | [`?(EntityRefsResponse[])`](../../doc/models/entity-refs-response.md) | Optional | - | getFunding(): ?array | setFunding(?array funding): void |
| `pendingEntries` | [`?(PendingEntriesResponse[])`](../../doc/models/pending-entries-response.md) | Optional | - | getPendingEntries(): ?array | setPendingEntries(?array pendingEntries): void |

## Example (as JSON)

```json
{
  "currency": "USD",
  "id": "id8",
  "created": "created8",
  "modified": "modified6",
  "creator": "String7",
  "modifier": "modifier2"
}
```

