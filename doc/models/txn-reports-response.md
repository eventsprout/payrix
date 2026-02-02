
# Txn Reports Response

## Structure

`TxnReportsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `txn` | `?string` | Optional | The identifier of the Transaction resource associated with this txnReports resource. | getTxn(): ?string | setTxn(?string txn): void |
| `interchangeType` | `?string` | Optional | The type of interchange used by the Transaction. | getInterchangeType(): ?string | setInterchangeType(?string interchangeType): void |
| `issuingBank` | `?string` | Optional | The name of the bank that issued the card used in the Transaction. | getIssuingBank(): ?string | setIssuingBank(?string issuingBank): void |
| `flatRateFee` | `?int` | Optional | If the fee charged by the Processor was a flat rate, then this field specifies its absolute amount.<br>This field is specified as an integer in cents. | getFlatRateFee(): ?int | setFlatRateFee(?int flatRateFee): void |
| `percentFee` | `?int` | Optional | If the fee charged by the Processor was a percentage of the Transaction value, then this field specifies the percentage, expressed in basis points.<br>For example, 25.3% is expressed as '2530'. | getPercentFee(): ?int | setPercentFee(?int percentFee): void |
| `feeTotal` | `?int` | Optional | This is the total amount charged in interchange fees.<br>This field is specified as an integer in cents. | getFeeTotal(): ?int | setFeeTotal(?int feeTotal): void |

## Example (as JSON)

```json
{
  "id": "id4",
  "created": "created4",
  "modified": "modified2",
  "creator": "String3",
  "modifier": "modifier8"
}
```

