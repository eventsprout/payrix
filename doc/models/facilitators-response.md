
# Facilitators Response

## Structure

`FacilitatorsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `entity` | `?string` | Optional | The identifier of the Entity that this Facilitators resource belongs to. | getEntity(): ?string | setEntity(?string entity): void |
| `prefix` | `?string` | Optional | The billing descriptor prefix for this Facilitator.<br>This string appears at the start of the description for transactions on credit card statements when any sub-Merchant of this Facilitator charges a card. | getPrefix(): ?string | setPrefix(?string prefix): void |
| `partition` | `?string` | Optional | The identifier of the Partition that this Facilitator is associated with.<br>You can only associate one Facilitator to each Partition. | getPartition(): ?string | setPartition(?string partition): void |
| `gatewayName` | `?string` | Optional | The name of the credit card processor.<br>Optional field used by transaction fraud checking. | getGatewayName(): ?string | setGatewayName(?string gatewayName): void |
| `tcMerchant` | `?string` | Optional | Latest merchant terms and conditions version for this facilitator. | getTcMerchant(): ?string | setTcMerchant(?string tcMerchant): void |
| `tcVendor` | `?string` | Optional | Latest vendor terms and conditions version for this facilitator. | getTcVendor(): ?string | setTcVendor(?string tcVendor): void |
| `chargebackNotificationEmail` | `?string` | Optional | Email for the facilitator to recieve a notification of a chargeback | getChargebackNotificationEmail(): ?string | setChargebackNotificationEmail(?string chargebackNotificationEmail): void |
| `riskContactEmails` | `?string` | Optional | List of risk contact emails. \nThese emails are used for risk management communications. | getRiskContactEmails(): ?string | setRiskContactEmails(?string riskContactEmails): void |
| `onboardingContactEmails` | `?string` | Optional | List of onboarding contact emails. \nThese emails are used for initial contact and setup processes. | getOnboardingContactEmails(): ?string | setOnboardingContactEmails(?string onboardingContactEmails): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id0",
  "created": "created0",
  "modified": "modified8",
  "creator": "String9",
  "modifier": "modifier4"
}
```

