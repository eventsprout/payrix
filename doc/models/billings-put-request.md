
# Billings Put Request

## Structure

`BillingsPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `?string` | Optional | The Login that owns this resource. | getLogin(): ?string | setLogin(?string login): void |
| `entity` | `?string` | Optional | The alphanumeric identifier of the Entity associated with this Account. | getEntity(): ?string | setEntity(?string entity): void |
| `forentity` | `?string` | Optional | The alphanumeric identifier of the Entity associated with this Account. | getForentity(): ?string | setForentity(?string forentity): void |
| `org` | `?string` | Optional | The identifier of the Org associated with this invoiceParameter. | getOrg(): ?string | setOrg(?string org): void |
| `division` | `?string` | Optional | ID of the division associated with this vendor | getDivision(): ?string | setDivision(?string division): void |
| `partition` | `?string` | Optional | The identifier of the Partition associated with this invoiceParameter. | getPartition(): ?string | setPartition(?string partition): void |
| `description` | `?string` | Optional | The billing details. | getDescription(): ?string | setDescription(?string description): void |
| `schedule` | [`?string(BillingScheduleEnum)`](../../doc/models/billing-schedule-enum.md) | Optional | The schedule that determines when this Billing is triggered to start collecting data.<br><br><details><br><summary>Valid Values</summary><br>- `days` - **Daily schedule.**<br>- `weeks` - **Weekly schedule.**<br>- `months` - **Monthly schedule.**<br>- `years` - **Annual schedule.**<br></details><br> | getSchedule(): ?string | setSchedule(?string schedule): void |
| `scheduleFactor` | `?int` | Optional | A multiplier that you can use to adjust the schedule set in the 'schedule' field, if it is set to a duration-based trigger, such as daily, weekly, monthly, or annually.<br>This field is specified as an integer and its value determines how the interval is multiplied. | getScheduleFactor(): ?int | setScheduleFactor(?int scheduleFactor): void |
| `start` | `?int` | Optional | The date on which this Billing period should start. | getStart(): ?int | setStart(?int start): void |
| `finish` | `?int` | Optional | The date on which this Billing period should end. | getFinish(): ?int | setFinish(?int finish): void |
| `collection` | [`?string(BillingCollectionEnum)`](../../doc/models/billing-collection-enum.md) | Optional | Determines who will be billed.<br><br><details><br><summary>Valid Values</summary><br>- `entity` - **The entity will be billed.**<br></details><br>**Default**: `BillingCollectionEnum::ENTITY`<br> | getCollection(): ?string | setCollection(?string collection): void |
| `collectionFactor` | [`?string(BillingsCollectionFactorEnum)`](../../doc/models/billings-collection-factor-enum.md) | Optional | A multiplier that you can use to adjust the set of data to be used in the collection calculation.<br><br><details><br><summary>Valid Values</summary><br>- `days` - **Days.** Multiplier based on days.<br>- `weeks` - **Weeks.** Multiplier based on weeks.<br>- `months` - **Months.** Multiplier based on months.<br>- `years` - **Years.** Multiplier based on years.<br></details><br> | getCollectionFactor(): ?string | setCollectionFactor(?string collectionFactor): void |
| `collectionOffset` | `?int` | Optional | The number of days, weeks, months or years to go back when selecting data for collection calculation. | getCollectionOffset(): ?int | setCollectionOffset(?int collectionOffset): void |
| `collectionIncludeCurrent` | [`?int(BillingsCollectionIncludeCurrentEnum)`](../../doc/models/billings-collection-include-current-enum.md) | Optional | Whether to include the current period in the collection calculation.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Exclude Current Period.** Do not include the current period in the calculation.<br>- `1` - **Include Current Period.** Include the current period in the calculation.<br></details><br> | getCollectionIncludeCurrent(): ?int | setCollectionIncludeCurrent(?int collectionIncludeCurrent): void |
| `currency` | [`?string(CurrencyEnum)`](../../doc/models/currency-enum.md) | Optional | The currency of the amount in this billing. See <a href="https://www.iban.com/currency-codes" target="_blank">Currency codes</a>  for all valid values.<br><br>**Default**: `CurrencyEnum::USD` | getCurrency(): ?string | setCurrency(?string currency): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "login": "t1_log_5cd987a73478a6179b95008",
  "entity": "identifier",
  "schedule": "months",
  "scheduleFactor": 1,
  "start": 20250401,
  "collection": "entity",
  "collectionFactor": "months",
  "collectionOffset": 1,
  "collectionIncludeCurrent": 0,
  "currency": "USD",
  "forentity": "t1_ent_67dbdc7bb6b1dd5dbf396e0",
  "org": "t1_org_5b0e08025ec790d3f9b8c00",
  "division": "t1_div_67c56806728fbbf0bae0b00",
  "partition": "t1_ptn_666834d4d504f21414970z0",
  "description": "Monthly Billing",
  "finish": 20250401,
  "inactive": 0,
  "frozen": 0
}
```

