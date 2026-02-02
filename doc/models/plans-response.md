
# Plans Response

## Structure

`PlansResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `merchant` | string\|[MerchantsResponse](../../doc/models/merchants-response.md)\|null | Optional | The identifier of the Merchant associated with this Plan. | getMerchant(): | setMerchant( merchant): void |
| `billing` | string\|[BillingsResponse](../../doc/models/billings-response.md)\|null | Optional | The attached billing for which recurring payments should be made to pay off statements. | getBilling(): | setBilling( billing): void |
| `type` | [`?string(PlanTypeEnum)`](../../doc/models/plan-type-enum.md) | Optional | The type of plan.<br><br><details><br><summary>Valid Values</summary><br>- `recurring` - **A recurring payment plan (subcription).**<br>- `installment`  - **A deferred payment installment plan.**<br><br></details><br>**Default**: `PlanTypeEnum::RECURRING`<br> | getType(): ?string | setType(?string type): void |
| `name` | `?string` | Optional | The name of this Plan.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | A description of this Plan.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `txnDescription` | `?string` | Optional | The description of the Txn that will be created through this Plan. | getTxnDescription(): ?string | setTxnDescription(?string txnDescription): void |
| `order` | `?string` | Optional | The order of the Txn that will be created through this Plan. | getOrder(): ?string | setOrder(?string order): void |
| `schedule` | [`?int(PlanScheduleEnum)`](../../doc/models/plan-schedule-enum.md) | Optional | The schedule that determines when the subscription related to this Plan is triggered.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Daily**<br>- `2` - **Weekly**<br>- `3` - **Monthly**<br>- `4` - **Annually**<br></details><br> | getSchedule(): ?int | setSchedule(?int schedule): void |
| `scheduleFactor` | `?int` | Optional | A multiplier that you can use to adjust the schedule set in the 'schedule' field, such as daily, weekly, monthly, or annually.<br>This field is specified as an integer and its value determines how the interval is multiplied. | getScheduleFactor(): ?int | setScheduleFactor(?int scheduleFactor): void |
| `um` | [`?string(PlanUmEnum)`](../../doc/models/plan-um-enum.md) | Optional | The unit of measure for the amount on the plan.<br><br><details><br><summary>Valid Values</summary><br>- `actual` - **An actual amount to charge, in cents.**<br>- `percent` - **A percentage of another amount, in basis points.**<br></details><br>**Default**: `PlanUmEnum::ACTUAL`<br> | getUm(): ?string | setUm(?string um): void |
| `amount` | `?int` | Optional | The amount to charge with each payment under this Plan.<br>This field is specified as an integer in cents. | getAmount(): ?int | setAmount(?int amount): void |
| `maxFailures` | `?int` | Optional | The maximum consecutive amount of payment failures to allow for a subscription before inactivating it. | getMaxFailures(): ?int | setMaxFailures(?int maxFailures): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `subscriptions` | [`?(SubscriptionsResponse[])`](../../doc/models/subscriptions-response.md) | Optional | - | getSubscriptions(): ?array | setSubscriptions(?array subscriptions): void |

## Example (as JSON)

```json
{
  "type": "recurring",
  "um": "actual",
  "inactive": 0,
  "frozen": 0,
  "id": "id6",
  "created": "created6",
  "modified": "modified4",
  "creator": "String5",
  "modifier": "modifier0"
}
```

