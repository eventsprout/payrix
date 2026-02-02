
# Partitions Response

## Structure

`PartitionsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | `?string` | Optional | The Login that owns this resource. | getLogin(): ?string | setLogin(?string login): void |
| `name` | `?string` | Optional | The name of this Partition.<br>This field is stored as a text string and must be between 0 and 50 characters long. | getName(): ?string | setName(?string name): void |
| `email` | `?string` | Optional | The email address that the API should send email notifications from when processing requests in this Partition.<br>This field is stored as a text string and must be between 1 and 100 characters long. | getEmail(): ?string | setEmail(?string email): void |
| `minPasswordLength` | `?int` | Optional | The minimum number of characters that all passwords used in this Partition must have.<br>This field is specified as an integer.<br>The value must be between 8 and 16. | getMinPasswordLength(): ?int | setMinPasswordLength(?int minPasswordLength): void |
| `minPasswordComplexity` | [`?int(MinPasswordComplexityEnum)`](../../doc/models/min-password-complexity-enum.md) | Optional | The minimum level of complexity that all passwords used in this Partition must have.<br>There are four complexity 'factors' that can be evaluated. These are the presence<br>of the following character types in the password: lowercase characters, uppercase<br>characters, integers, and special characters. For instance, the password '123a'<br>would get a complexity rating of '2', since it contains integers and lowercase characters.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Needs to include one type.**<br>- `2` - **Needs to include two types.**<br>- `3` - **Needs to include three types.**<br>- `4` - **Needs to include four types.**<br></details><br> | getMinPasswordComplexity(): ?int | setMinPasswordComplexity(?int minPasswordComplexity): void |
| `minPasswordHistory` | `?int` | Optional | The minimum number of previous passwords that the current password must be distinct from.<br>This field is specified as an integer. The value must be between 3 and 12. | getMinPasswordHistory(): ?int | setMinPasswordHistory(?int minPasswordHistory): void |
| `noEmailConfirmation` | [`?int(PartitionNoEmailConfirmationEnum)`](../../doc/models/partition-no-email-confirmation-enum.md) | Optional | Whether to disable the email address confirmation process for this Partition.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Disabled**<br>- `1` - **Enabled**<br></details><br> | getNoEmailConfirmation(): ?int | setNoEmailConfirmation(?int noEmailConfirmation): void |
| `noHoldEmail` | [`?int(PartitionNoHoldEmailEnum)`](../../doc/models/partition-no-hold-email-enum.md) | Optional | Whether to disable email notification for automated hold messages.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Disabled**<br>- `1` - **Enabled**<br></details><br> | getNoHoldEmail(): ?int | setNoHoldEmail(?int noHoldEmail): void |
| `changeManagementEnabled` | [`?int(ChangeManagementEnabledEnum)`](../../doc/models/change-management-enabled-enum.md) | Optional | Whether change management is enabled.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Disabled**<br>- `1` - **Enabled**<br></details><br> | getChangeManagementEnabled(): ?int | setChangeManagementEnabled(?int changeManagementEnabled): void |
| `currency` | [`?string(CurrencyEnum)`](../../doc/models/currency-enum.md) | Optional | The currency in which an entity should board. See <a href="https://www.iban.com/currency-codes" target="_blank">Currency codes</a>  for all valid values.<br><br>**Default**: `CurrencyEnum::USD` | getCurrency(): ?string | setCurrency(?string currency): void |

## Example (as JSON)

```json
{
  "currency": "USD",
  "id": "id0",
  "created": "created0",
  "modified": "modified8",
  "creator": "String9",
  "modifier": "modifier4"
}
```

