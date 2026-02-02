
# Divisions Post Request

## Structure

`DivisionsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `string` | Required | The Login that owns this resource. | getLogin(): string | setLogin(string login): void |
| `name` | `string` | Required | The name of the division, which may be used for some white-label purposes. | getName(): string | setName(string name): void |
| `email` | `?string` | Optional | The white-labeled outgoing email for all automated emails generated throughout this division. | getEmail(): ?string | setEmail(?string email): void |
| `saferPaymentNonComplianceFeeManaged` | [`?int(SaferPaymentNonComplianceFeeManagedModelEnum)`](../../doc/models/safer-payment-non-compliance-fee-managed-model-enum.md) | Optional | Whether SaferPayment Non-compliance fee management is enabled<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Disabled.**<br>- `1` - **Enabled.**<br></details><br> | getSaferPaymentNonComplianceFeeManaged(): ?int | setSaferPaymentNonComplianceFeeManaged(?int saferPaymentNonComplianceFeeManaged): void |
| `changeManagementEnabled` | [`?int(ChangeManagementEnabledEnum)`](../../doc/models/change-management-enabled-enum.md) | Optional | Whether change management is enabled.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Disabled**<br>- `1` - **Enabled**<br></details><br> | getChangeManagementEnabled(): ?int | setChangeManagementEnabled(?int changeManagementEnabled): void |
| `minPasswordLength` | `?int` | Optional | Limit for password validations length. | getMinPasswordLength(): ?int | setMinPasswordLength(?int minPasswordLength): void |
| `minPasswordComplexity` | [`?int(MinPasswordComplexityEnum)`](../../doc/models/min-password-complexity-enum.md) | Optional | The minimum level of complexity that all passwords used in this Partition must have.<br>There are four complexity 'factors' that can be evaluated. These are the presence<br>of the following character types in the password: lowercase characters, uppercase<br>characters, integers, and special characters. For instance, the password '123a'<br>would get a complexity rating of '2', since it contains integers and lowercase characters.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Needs to include one type.**<br>- `2` - **Needs to include two types.**<br>- `3` - **Needs to include three types.**<br>- `4` - **Needs to include four types.**<br></details><br> | getMinPasswordComplexity(): ?int | setMinPasswordComplexity(?int minPasswordComplexity): void |
| `hosts` | [`?(HostsPostRequest[])`](../../doc/models/hosts-post-request.md) | Optional | - | getHosts(): ?array | setHosts(?array hosts): void |

## Example (as JSON)

```json
{
  "login": "t1_log_67e150467ee225924163f18",
  "name": "sampleDivision",
  "email": "testuse1@example.com",
  "changeManagementEnabled": 0,
  "minPasswordLength": 9,
  "minPasswordComplexity": 1,
  "saferPaymentNonComplianceFeeManaged": 0
}
```

