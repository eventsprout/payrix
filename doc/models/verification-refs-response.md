
# Verification Refs Response

## Structure

`VerificationRefsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | `?string` | Optional | The Login that owns this resource. | getLogin(): ?string | setLogin(?string login): void |
| `entity` | `?string` | Optional | The identifier of the Entity that was verified. | getEntity(): ?string | setEntity(?string entity): void |
| `txn` | `?string` | Optional | The ID of the transaction. | getTxn(): ?string | setTxn(?string txn): void |
| `changeRequest` | `?string` | Optional | The concept of change request is to get a second level authorization before actioning the result of a verification/policy run. | getChangeRequest(): ?string | setChangeRequest(?string changeRequest): void |
| `ref` | `?string` | Optional | This is the reference from the integration response. | getRef(): ?string | setRef(?string ref): void |
| `riskLevel` | [`?string(VerificationRiskLevelEnum)`](../../doc/models/verification-risk-level-enum.md) | Optional | <details><br><summary>Valid Values</summary><br>- `Low` - **Risk level for Low.**<br>- `High` - **Risk level for High.**<br>- `Medium` - **Risk level for Medium.**<br></details><br> | getRiskLevel(): ?string | setRiskLevel(?string riskLevel): void |
| `stage` | `?string` | Optional | This is the stage where the decisions or policy run is been triggered. | getStage(): ?string | setStage(?string stage): void |
| `policyName` | `?string` | Optional | This is the name of the policy that is ran in this stage as returned from the integratio n response. | getPolicyName(): ?string | setPolicyName(?string policyName): void |
| `action` | [`?string(VerificationRefActionEnum)`](../../doc/models/verification-ref-action-enum.md) | Optional | The action to take when this check fails.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **No action.**<br>- `1` - **Block txn, will never be processed. The Entity is sent to the manual review queue.**<br>- `3` - **Hold txn, will not be captured.**<br>- `4` - **Reserve txn, funds should be reserved.**<br>- `5` - **Block current activity, no change for merchant.**<br>- `6` - **Passed decision(s). Will not be set anywhere, will only be used for integration purposes.**<br>- `8` - **We onboard the merchant and wait for manual check later.**<br>- `manualReview` - **Schedule the automatic release of the reserve.**<br>- `approved` - **Hold txn, will not be captured. Automatic release when the associated sale is done.**<br>- `declined` - **Hold txn, will not be captured. Automatic release when the associated sale is done.**<br></details><br> | getAction(): ?string | setAction(?string action): void |
| `policyUuid` | `?string` | Optional | This is the ID of the policy as returned from the integration response. | getPolicyUuid(): ?string | setPolicyUuid(?string policyUuid): void |

## Example (as JSON)

```json
{
  "id": "id8",
  "created": "created8",
  "modified": "modified6",
  "creator": "String7",
  "modifier": "modifier8"
}
```

