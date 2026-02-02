
# Orgs VAS Safer Payments Non Compliance Post Request

## Structure

`OrgsVASSaferPaymentsNonCompliancePostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `org` | `string` | Required | The identifier of the Org (group) that OrgsVASSaferPaymentsNonCompliance is associated to. | getOrg(): string | setOrg(string org): void |
| `division` | `string` | Required | The identifier of the Division that OrgsVASSaferPaymentsNonCompliance is applied on. | getDivision(): string | setDivision(string division): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "org": "t1_org_680bfd2cea2729081810000",
  "division": "t1_div_680bfd2cea2729081810000",
  "inactive": 0,
  "frozen": 0
}
```

