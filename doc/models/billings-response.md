
# Billings Response

## Structure

`BillingsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The Login that owns this resource. | getLogin(): | setLogin( login): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The alphanumeric identifier of the Entity associated with this Account. | getEntity(): | setEntity( entity): void |
| `forentity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The alphanumeric identifier of the Entity associated with this Account. | getForentity(): | setForentity( forentity): void |
| `org` | string\|[OrgsResponse](../../doc/models/orgs-response.md)\|null | Optional | The identifier of the Org associated with this invoiceParameter. | getOrg(): | setOrg( org): void |
| `division` | string\|[DivisionsResponse](../../doc/models/divisions-response.md)\|null | Optional | The identifier of the Division associated with this vendor. | getDivision(): | setDivision( division): void |
| `partition` | string\|[PartitionsResponse](../../doc/models/partitions-response.md)\|null | Optional | The identifier of the Partition associated with this invoiceParameter. | getPartition(): | setPartition( partition): void |
| `description` | `?string` | Optional | The billing details. | getDescription(): ?string | setDescription(?string description): void |
| `schedule` | [`?string(BillingScheduleEnum)`](../../doc/models/billing-schedule-enum.md) | Optional | The schedule that determines when this Billing is triggered to start collecting data.<br><br><details><br><summary>Valid Values</summary><br>- `days` - **Daily schedule.**<br>- `weeks` - **Weekly schedule.**<br>- `months` - **Monthly schedule.**<br>- `years` - **Annual schedule.**<br></details><br> | getSchedule(): ?string | setSchedule(?string schedule): void |
| `scheduleFactor` | `?int` | Optional | A multiplier that you can use to adjust the schedule set in the 'schedule' field, if it is set to a duration-based trigger, such as daily, weekly, monthly, or annually.<br>This field is specified as an integer and its value determines how the interval is multiplied. | getScheduleFactor(): ?int | setScheduleFactor(?int scheduleFactor): void |
| `start` | `?int` | Optional | The date on which this Billing period should start. | getStart(): ?int | setStart(?int start): void |
| `finish` | `?int` | Optional | The date on which this Billing period should end. | getFinish(): ?int | setFinish(?int finish): void |
| `collectionFactor` | [`?string(BillingsCollectionFactorEnum)`](../../doc/models/billings-collection-factor-enum.md) | Optional | A multiplier that you can use to adjust the set of data to be used in the collection calculation.<br><br><details><br><summary>Valid Values</summary><br>- `days` - **Days.** Multiplier based on days.<br>- `weeks` - **Weeks.** Multiplier based on weeks.<br>- `months` - **Months.** Multiplier based on months.<br>- `years` - **Years.** Multiplier based on years.<br></details><br> | getCollectionFactor(): ?string | setCollectionFactor(?string collectionFactor): void |
| `collectionOffset` | `?int` | Optional | The number of days, weeks, months or years to go back when selecting data for collection calculation. | getCollectionOffset(): ?int | setCollectionOffset(?int collectionOffset): void |
| `collectionIncludeCurrent` | [`?int(BillingsCollectionIncludeCurrentEnum)`](../../doc/models/billings-collection-include-current-enum.md) | Optional | Whether to include the current period in the collection calculation.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Exclude Current Period.** Do not include the current period in the calculation.<br>- `1` - **Include Current Period.** Include the current period in the calculation.<br></details><br> | getCollectionIncludeCurrent(): ?int | setCollectionIncludeCurrent(?int collectionIncludeCurrent): void |
| `currency` | [`?string(CurrencyEnum)`](../../doc/models/currency-enum.md) | Optional | The currency of the amount in this billing. See <a href="https://www.iban.com/currency-codes" target="_blank">Currency codes</a>  for all valid values.<br><br>**Default**: `CurrencyEnum::USD` | getCurrency(): ?string | setCurrency(?string currency): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `collection` | [`?string(BillingCollectionEnum)`](../../doc/models/billing-collection-enum.md) | Optional | Determines who will be billed.<br><br><details><br><summary>Valid Values</summary><br>- `entity` - **The entity will be billed.**<br></details><br>**Default**: `BillingCollectionEnum::ENTITY`<br> | getCollection(): ?string | setCollection(?string collection): void |
| `billingEvents` | [`?(BillingEventsResponse[])`](../../doc/models/billing-events-response.md) | Optional | - | getBillingEvents(): ?array | setBillingEvents(?array billingEvents): void |
| `billingModifiers` | [`?(BillingModifiersResponse[])`](../../doc/models/billing-modifiers-response.md) | Optional | - | getBillingModifiers(): ?array | setBillingModifiers(?array billingModifiers): void |
| `payoutFlows` | [`?(PayoutFlowsResponse[])`](../../doc/models/payout-flows-response.md) | Optional | - | getPayoutFlows(): ?array | setPayoutFlows(?array payoutFlows): void |
| `payouts` | [`?(PayoutsResponse[])`](../../doc/models/payouts-response.md) | Optional | - | getPayouts(): ?array | setPayouts(?array payouts): void |
| `plans` | [`?(PlansResponse[])`](../../doc/models/plans-response.md) | Optional | - | getPlans(): ?array | setPlans(?array plans): void |
| `statementEntries` | [`?(StatementEntriesResponse[])`](../../doc/models/statement-entries-response.md) | Optional | - | getStatementEntries(): ?array | setStatementEntries(?array statementEntries): void |
| `statements` | [`?(StatementsResponse[])`](../../doc/models/statements-response.md) | Optional | - | getStatements(): ?array | setStatements(?array statements): void |

## Example (as JSON)

```json
{
  "currency": "USD",
  "inactive": 0,
  "frozen": 0,
  "collection": "entity",
  "id": "id8",
  "created": "created8",
  "modified": "modified6",
  "creator": "String7",
  "modifier": "modifier8"
}
```

