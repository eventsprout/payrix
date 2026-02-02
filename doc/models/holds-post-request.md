
# Holds Post Request

## Structure

`HoldsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `string` | Required | The identifier of the Login that owns this holds resource. | getLogin(): string | setLogin(string login): void |
| `verificationRef` | `?string` | Optional | If this hold resource was triggered through Payrix Integration Risk, then this field stores the identifier of the VerificationRef. | getVerificationRef(): ?string | setVerificationRef(?string verificationRef): void |
| `released` | `?string` | Optional | If this hold was released, this will contain the timestamp for when it was released. (YYYY-MM-DD HH:II:SS)<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}$` | getReleased(): ?string | setReleased(?string released): void |
| `reviewed` | `?string` | Optional | If this hold was reviewed, this will contain the timestamp for when it was reviewed. The format should be YYYY-MM-DD HH:MM:SS.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}$` | getReviewed(): ?string | setReviewed(?string reviewed): void |
| `releaseAction` | [`?int(HoldsReleaseActionEnum)`](../../doc/models/holds-release-action-enum.md) | Optional | The final action taken on the hold while it's been released.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Holds released because the hold resource was approved.**<br>- `2` - **Holds released because the hold resource was cancelled.**<br>- `3` - **Holds released because the hold resource was refunded.**<br>- `4` - **Holds released because the hold resource was failed.**<br>- `5` - **Expired.**<br></details><br> | getReleaseAction(): ?int | setReleaseAction(?int releaseAction): void |
| `holdSource` | [`?string(HoldsHoldSourceEnum)`](../../doc/models/holds-hold-source-enum.md) | Optional | Field created to know the reason for why a hold was created.<br><br><details><br><summary>Valid Values</summary><br>- `DS_MODEL_POLICY_RUN` - **DS_MODEL_POLICY_RUN**<br>- `API_DECISION` - **API_DECISION**<br>- `POLICY_RUN` - **POLICY_RUN**<br>- `RISK_ALERT` - **RISK_ALERT**<br>- `MANUAL` - **MANUAL**<br>- `ERROR` - **ERROR**<br></details><br> | getHoldSource(): ?string | setHoldSource(?string holdSource): void |
| `holdSourceId` | `?string` | Optional | reasonid for why a hold was created. | getHoldSourceId(): ?string | setHoldSourceId(?string holdSourceId): void |
| `delayedFundingStartDate` | `?string` | Optional | The timestamp when hold was considered to be delaying funding. The format should be YYYY-MM-DD HH:MM:SS.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}$` | getDelayedFundingStartDate(): ?string | setDelayedFundingStartDate(?string delayedFundingStartDate): void |
| `delayedFundingEndDate` | `?string` | Optional | The timestamp when hold stopped delaying funding, this might be due to the hold been released, cancelled or funded. (YYYY-MM-DD HH:II:SS)<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}$` | getDelayedFundingEndDate(): ?string | setDelayedFundingEndDate(?string delayedFundingEndDate): void |
| `analyst` | `?string` | Optional | The person who review the hold applied. | getAnalyst(): ?string | setAnalyst(?string analyst): void |
| `claimed` | `?string` | Optional | The timestamp for the most recent update of the analyst field. (YYYY-MM-DD HH:II:SS)<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}$` | getClaimed(): ?string | setClaimed(?string claimed): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `notes` | [`?(NotesPostRequest[])`](../../doc/models/notes-post-request.md) | Optional | - | getNotes(): ?array | setNotes(?array notes): void |

## Example (as JSON)

```json
{
  "login": "t1_hld_0000fc11df8e4c00000e00c",
  "verificationRef": "t1_xyz_12345eb00f0cf1bfc00be0f",
  "released": "2025-01-31 08:42:16",
  "reviewed": "2025-01-31 08:42:16",
  "releaseAction": 2,
  "holdSource": "API_DECISION",
  "holdSourceId": "5a9bba34-38eb-489e-abd8-765e18562a08",
  "delayedFundingStartDate": "2025-01-31 08:42:16",
  "delayedFundingEndDate": "2025-01-31 08:42:16",
  "analyst": "name",
  "claimed": "2025-01-31 08:42:16",
  "inactive": 0,
  "frozen": 0
}
```

