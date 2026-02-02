
# Vendors Post Request

## Structure

`VendorsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `entity` | string\|[EntitiesPostRequest](../../doc/models/entities-post-request.md) | Required | The identifier of the Entity associated with this Vendor resource. | getEntity(): | setEntity( entity): void |
| `division` | string\|[DivisionsPostRequest](../../doc/models/divisions-post-request.md)\|null | Optional | ID of the division associated with this vendor. | getDivision(): | setDivision( division): void |
| `onboardingContactEmails` | `?string` | Optional | This holds the different emails the partners will want to be reached for onboarding related queries/concerns, this is a way of allowing the risk team to manage contacts more efficiently. | getOnboardingContactEmails(): ?string | setOnboardingContactEmails(?string onboardingContactEmails): void |
| `riskContactEmails` | `?string` | Optional | This holds the different emails the partners will want to be reached for risk related queries/concerns, this is a way of allowing the risk team to manage contacts more efficiently. | getRiskContactEmails(): ?string | setRiskContactEmails(?string riskContactEmails): void |
| `inactive` | [`int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Required | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): int | setInactive(int inactive): void |
| `frozen` | [`int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Required | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): int | setFrozen(int frozen): void |

## Example (as JSON)

```json
{
  "entity": "p1_ent_67be57c6a1d97f564021b6b",
  "division": "p1_div_67be57c6d34928c1ee16155",
  "onboardingContactEmails": "robert@example.com",
  "riskContactEmails": "robert.j@example.com",
  "inactive": 0,
  "frozen": 0
}
```

