
# Safer Payments Post Request

## Structure

`SaferPaymentsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `entity` | `?string` | Optional | The identifier of the Entity that saferPayments is associated to. | getEntity(): ?string | setEntity(?string entity): void |
| `status` | [`?string(SaferPaymentStatusEnum)`](../../doc/models/safer-payment-status-enum.md) | Optional | This field indicates the entity's current PCI compliance status for the service.<br><br><details><br><summary>Valid Values</summary><br>- `compliance` - **Compliance**<br>- `non-compliance` - **Non-Compliance**<br>- `pending` - **Pending**<br></details><br> | getStatus(): ?string | setStatus(?string status): void |
| `enablementDate` | `?string` | Optional | The Date and time when an entity was enabled for saferPayments.\nThe date is specified as an eight digit string in YYYY-MM-DD hh:mm:ss format, for example, '2023-06-01 01:00:00' for June 01, 2023. 1:00 am.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}` | getEnablementDate(): ?string | setEnablementDate(?string enablementDate): void |
| `pciNonValidationFeeEnabled` | [`?int(SaferPaymentPciNonValidationFeeEnabledEnum)`](../../doc/models/safer-payment-pci-non-validation-fee-enabled-enum.md) | Optional | This field indicates if the entity should be charged penalty fees for non-compliance.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Penalty Disabled.**<br>- `1` - **Penalty Enabled.**<br></details><br> | getPciNonValidationFeeEnabled(): ?int | setPciNonValidationFeeEnabled(?int pciNonValidationFeeEnabled): void |
| `org` | `?string` | Optional | The identifier of the Org (group) that saferPayments is associated to. | getOrg(): ?string | setOrg(?string org): void |
| `division` | `?string` | Optional | The identifier of the Division that saferPayments  is associated to. | getDivision(): ?string | setDivision(?string division): void |
| `partition` | `?string` | Optional | The identifier of the Partition that saferPayments is associated to. | getPartition(): ?string | setPartition(?string partition): void |
| `program` | [`?string(SaferPaymentProgramEnum)`](../../doc/models/safer-payment-program-enum.md) | Optional | This field contains the program type of the saferPayments.<br><br><details><br><summary>Valid Values</summary><br>- `basic` - **Basic**<br>- `managed` - **Managed**<br></details><br> | getProgram(): ?string | setProgram(?string program): void |
| `deleted` | `?string` | Optional | The date and time at which this resource was deleted.\nThe date is specified as an eight digit string in YYYY-MM-DD hh:mm:ss format, for example, '2023-06-01 01:00:00' for June 01, 2023. 1:00 am.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}` | getDeleted(): ?string | setDeleted(?string deleted): void |
| `deleter` | `?string` | Optional | The id of user who deleted the omniToken. | getDeleter(): ?string | setDeleter(?string deleter): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "entity": "t1_ent_65de12aabb1f58e2a3441f7",
  "status": "compliance",
  "enablementDate": "2024-02-27 11:54:19",
  "pciNonValidationFeeEnabled": 0,
  "org": "t1_org_00b2ac11ed8bed97fb80000",
  "division": "t1_div_67c56806728fbbf0bae0b00",
  "partition": "t1_ptn_666834d4d504f21414978z5",
  "program": "basic",
  "deleted": "2024-02-27 11:54:19",
  "deleter": "",
  "inactive": 0,
  "frozen": 0
}
```

