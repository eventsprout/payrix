
# Profit Shares Response

## Structure

`ProfitSharesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that owns this ProfitShare. | getLogin(): | setLogin( login): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity that this ProfitShare refers to. This is the entity that will receive the split income/expense. | getEntity(): | setEntity( entity): void |
| `forentity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity that will have it's earnings/expenses shared. | getForentity(): | setForentity( forentity): void |
| `org` | string\|[OrgsResponse](../../doc/models/orgs-response.md)\|null | Optional | The identifier of the Org in which entities will have their earnings/expenses shares. | getOrg(): | setOrg( org): void |
| `division` | string\|[DivisionsResponse](../../doc/models/divisions-response.md)\|null | Optional | The identifier of the Division in which entities will have their earnings/expenses shares. | getDivision(): | setDivision( division): void |
| `partition` | string\|[PartitionsResponse](../../doc/models/partitions-response.md)\|null | Optional | The identifier of the Partition in which entities will have their earnings/expenses shares. | getPartition(): | setPartition( partition): void |
| `type` | [`?string(ProfitShareTypeEnum)`](../../doc/models/profit-share-type-enum.md) | Optional | Indicates if the Profit Share should be processed when there is an income, expense, or both.<br><br><details><br><summary>Valid Values</summary><br>- `income` - **Profit Share processing for income-only.**<br>- `expense` - **Profit Share processing for expense-only.**<br>- `both` - **Profit Share processing for both income and expense.**<br></details><br> | getType(): ?string | setType(?string type): void |
| `name` | `?string` | Optional | The name of this ProfitShare.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this ProfitShare.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `amount` | `?int` | Optional | The percentage to be shared.<br>This field is specified as an integer between 1 and 10000.<br>Percentages are calculated over the income/expense amount. | getAmount(): ?int | setAmount(?int amount): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `billingEvents` | [`?(BillingEventsResponse[])`](../../doc/models/billing-events-response.md) | Optional | - | getBillingEvents(): ?array | setBillingEvents(?array billingEvents): void |
| `pendingEntries` | [`?(PendingEntriesResponse[])`](../../doc/models/pending-entries-response.md) | Optional | - | getPendingEntries(): ?array | setPendingEntries(?array pendingEntries): void |
| `profitShareResults` | [`?(ProfitShareResultsResponse[])`](../../doc/models/profit-share-results-response.md) | Optional | - | getProfitShareResults(): ?array | setProfitShareResults(?array profitShareResults): void |
| `profitShareRules` | [`?(ProfitShareRulesResponse[])`](../../doc/models/profit-share-rules-response.md) | Optional | - | getProfitShareRules(): ?array | setProfitShareRules(?array profitShareRules): void |
| `statementEntries` | [`?(StatementEntriesResponse[])`](../../doc/models/statement-entries-response.md) | Optional | - | getStatementEntries(): ?array | setStatementEntries(?array statementEntries): void |
| `entries` | [`?(EntriesResponse[])`](../../doc/models/entries-response.md) | Optional | - | getEntries(): ?array | setEntries(?array entries): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id4",
  "created": "created4",
  "modified": "modified2",
  "creator": "String3",
  "modifier": "modifier2"
}
```

