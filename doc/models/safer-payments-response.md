
# Safer Payments Response

## Structure

`SaferPaymentsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity that saferPayments is associated to. | getEntity(): | setEntity( entity): void |
| `status` | [`?string(SaferPaymentStatusEnum)`](../../doc/models/safer-payment-status-enum.md) | Optional | This field indicates the entity's current PCI compliance status for the service.<br><br><details><br><summary>Valid Values</summary><br>- `compliance` - **Compliance**<br>- `non-compliance` - **Non-Compliance**<br>- `pending` - **Pending**<br></details><br> | getStatus(): ?string | setStatus(?string status): void |
| `enablementDate` | `?string` | Optional | The Date and time when an entity was enabled for saferPayments.\nThe date is specified as an eight digit string in YYYY-MM-DD hh:mm:ss format, for example, '2023-06-01 01:00:00' for June 01, 2023. 1:00 am.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}` | getEnablementDate(): ?string | setEnablementDate(?string enablementDate): void |
| `pciNonValidationFeeEnabled` | [`?int(SaferPaymentPciNonValidationFeeEnabledEnum)`](../../doc/models/safer-payment-pci-non-validation-fee-enabled-enum.md) | Optional | This field indicates if the entity should be charged penalty fees for non-compliance.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Penalty Disabled.**<br>- `1` - **Penalty Enabled.**<br></details><br> | getPciNonValidationFeeEnabled(): ?int | setPciNonValidationFeeEnabled(?int pciNonValidationFeeEnabled): void |
| `org` | string\|[OrgsResponse](../../doc/models/orgs-response.md)\|null | Optional | The identifier of the Org (group) that saferPayments is associated to. | getOrg(): | setOrg( org): void |
| `division` | string\|[DivisionsResponse](../../doc/models/divisions-response.md)\|null | Optional | The identifier of the Division that saferPayments  is associated to. | getDivision(): | setDivision( division): void |
| `partition` | string\|[PartitionsResponse](../../doc/models/partitions-response.md)\|null | Optional | The identifier of the Partition that saferPayments is associated to. | getPartition(): | setPartition( partition): void |
| `program` | [`?string(SaferPaymentProgramEnum)`](../../doc/models/safer-payment-program-enum.md) | Optional | This field contains the program type of the saferPayments.<br><br><details><br><summary>Valid Values</summary><br>- `basic` - **Basic**<br>- `managed` - **Managed**<br></details><br> | getProgram(): ?string | setProgram(?string program): void |
| `deleted` | `?string` | Optional | The date and time at which this resource was deleted.\nThe date is specified as an eight digit string in YYYY-MM-DD hh:mm:ss format, for example, '2023-06-01 01:00:00' for June 01, 2023. 1:00 am.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}` | getDeleted(): ?string | setDeleted(?string deleted): void |
| `deleter` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The id of user who deleted the omniToken. | getDeleter(): | setDeleter( deleter): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id2",
  "created": "created2",
  "modified": "modified0",
  "creator": "String1",
  "modifier": "modifier6"
}
```

