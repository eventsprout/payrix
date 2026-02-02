
# Aggregation Results Response

## Structure

`AggregationResultsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `aggregationResultGroup` | string\|[AggregationResultGroupsResponse](../../doc/models/aggregation-result-groups-response.md)\|null | Optional | The identifier of the AggregationResultGroup that this AggregationResult refers to. | getAggregationResultGroup(): | setAggregationResultGroup( aggregationResultGroup): void |
| `grouping` | `?string` | Optional | Grouping is a process used in data aggregation to organize data into specific categories or groups based on certain attributes. This allows for detailed analysis and reporting on subsets of data. For example, grouping transactions by merchant and payment method enables you to see the breakdown of transactions for each merchant and payment method combination. | getGrouping(): ?string | setGrouping(?string grouping): void |
| `field` | `?string` | Optional | The field of the resource where calculations were made based on.<br>This field is stored as a text string and must be between 1 and 100 characters long. | getField(): ?string | setField(?string field): void |
| `count` | `?int` | Optional | The value calculated by the count aggregation function.<br>This field is specified as an integer. | getCount(): ?int | setCount(?int count): void |
| `sum` | `?float` | Optional | The value calculated by the sum aggregation function.<br>This field is specified in cents(up to three decimal points). | getSum(): ?float | setSum(?float sum): void |
| `min` | `?float` | Optional | The value calculated by the min aggregation function.<br>This field is specified in cents(up to three decimal points). | getMin(): ?float | setMin(?float min): void |
| `max` | `?float` | Optional | The value calculated by the max aggregation function.<br>This field is specified in cents(up to three decimal points). | getMax(): ?float | setMax(?float max): void |

## Example (as JSON)

```json
{
  "id": "id0",
  "created": "created0",
  "modified": "modified8",
  "creator": "String9",
  "modifier": "modifier4"
}
```

