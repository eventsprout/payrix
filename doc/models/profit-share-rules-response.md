
# Profit Share Rules Response

## Structure

`ProfitShareRulesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `profitShare` | string\|[ProfitSharesResponse](../../doc/models/profit-shares-response.md)\|null | Optional | The identifier of the ProfitShare that this ProfitShare Rule applies to. | getProfitShare(): | setProfitShare( profitShare): void |
| `name` | `?string` | Optional | The name of this ProfitShare Rule.<br>This field is stored as a text string and must be between 0 and 100 characters long. | getName(): ?string | setName(?string name): void |
| `description` | `?string` | Optional | Description of the Profit Share Rules. | getDescription(): ?string | setDescription(?string description): void |
| `type` | [`?string(ProfitShareRuleTypeEnum)`](../../doc/models/profit-share-rule-type-enum.md) | Optional | The type of logic to apply with this ProfitShare Rule.<br><br><details><br><summary>Valid Values</summary><br>- `less` - **The ProfitShare applies only if the entry amount is lower than the amount set in the 'value' field of the ProfitShare Rule.**<br>- `equal` - **The ProfitShare applies only if the entry amount is exactly the same as the amount set in the 'value' field of the ProfitShare Rule.**<br>- `notEqual` - **The ProfitShare applies only if the entry amount is not exactly equal to the amount set in the 'value' field of the ProfitShare Rule.**<br>- `greater` - **The ProfitShare applies only if the entry amount is higher than the amount set in the 'value' field of the ProfitShare Rule.**<br>- `event` - **The ProfitShare applies only if the entry event is exactly the same as the event set in the 'value' field of the ProfitShare Rule.**<br>- `notEvent` - **The ProfitShare applies only if the entry event is not exactly equal to the event set in the 'value' field of the ProfitShare Rule.**<br>- `fee` - **The ProfitShare applies only if the entry fee is exactly the same as the fee set in the 'value' field of the ProfitShare Rule.**<br>- `notFee` - **The ProfitShare applies only if the entry fee is not exactly equal to the fee set in the 'value' field of the ProfitShare Rule.**<br>- `fromentity` - **The ProfitShare applies only if the entry fromentity (or opposingEntryfromentity) is exactly the same as the entity set in the 'value' field of the ProfitShare Rule.**<br>- `notFromentity` - **The ProfitShare applies only if the entry fromentity (or opposingEntryfromentity) is not exactly equal to the entity set in the 'value' field of the ProfitShare Rule.**<br></details><br> | getType(): ?string | setType(?string type): void |
| `value` | `?string` | Optional | The value to compare against when evaluating this ProfitShare Rule. | getValue(): ?string | setValue(?string value): void |
| `grouping` | `?string` | Optional | A name for a group of rules to be applied in conjunction when evaluating this ProfitShare Rule.<br>When grouping is used the ProfitShare will be allowed to be processed if at least one of the rules are matched. | getGrouping(): ?string | setGrouping(?string grouping): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `fee` | [`?FeesResponse`](../../doc/models/fees-response.md) | Optional | - | getFee(): ?FeesResponse | setFee(?FeesResponse fee): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id6",
  "created": "created6",
  "modified": "modified4",
  "creator": "String5",
  "modifier": "modifier0"
}
```

