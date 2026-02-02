
# Change Request

## Structure

`ChangeRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `deleted` | `?string` | Optional | In case resource is deleted, this field will then show the date it occurred. The format should be YYYY-MM-DD HH:MM:SS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}` | getDeleted(): ?string | setDeleted(?string deleted): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login associated with this ChangeRequest. | getLogin(): | setLogin( login): void |
| `authType` | `?int` | Optional | Auth Type that originate the request. | getAuthType(): ?int | setAuthType(?int authType): void |
| `operation` | [`?string(ChangeRequestOperationEnum)`](../../doc/models/change-request-operation-enum.md) | Optional | The operation being performed on the resource.<br><br><details><br><summary>Valid Values</summary><br>- `create` - **When creating a model.**<br>- `update` - **When updating a model.**<br></details><br> | getOperation(): ?string | setOperation(?string operation): void |
| `status` | [`?string(ChangeRequestStatusEnum)`](../../doc/models/change-request-status-enum.md) | Optional | The status of the requested change.<br><br><details><br><summary>Valid Values</summary><br>- `pending` - **The Change Request has a pending status.**<br>- `manualReview` - **The Change Request was escalated to be manually reviewed.**<br>- `approved` - **The Change Request has been approved.**<br>- `declined` - **The Change Request was declined.**<br></details><br> | getStatus(): ?string | setStatus(?string status): void |
| `reasonType` | `?string` | Optional | A type which categorizes the reason, in case the change was declined. | getReasonType(): ?string | setReasonType(?string reasonType): void |
| `reason` | `?string` | Optional | The reason in case the change was declined. | getReason(): ?string | setReason(?string reason): void |
| `changes` | `?string` | Optional | A JSON encoded string with the request payload | getChanges(): ?string | setChanges(?string changes): void |
| `model` | `?string` | Optional | The model being changed. | getModel(): ?string | setModel(?string model): void |
| `recordId` | string\|[AccountsResponse](../../doc/models/accounts-response.md)\|null | Optional | The id of the model, only set when operation is update. | getRecordId(): | setRecordId( recordId): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity associated with this Account. | getEntity(): | setEntity( entity): void |
| `analyst` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The person who review the request. | getAnalyst(): | setAnalyst( analyst): void |
| `reviewed` | `?string` | Optional | If this change request was reviewed. The format should be YYYY-MM-DD HH:MM:SS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}` | getReviewed(): ?string | setReviewed(?string reviewed): void |
| `verificationRef` | [`?VerificationRefsResponse`](../../doc/models/verification-refs-response.md) | Optional | - | getVerificationRef(): ?VerificationRefsResponse | setVerificationRef(?VerificationRefsResponse verificationRef): void |

## Example (as JSON)

```json
{
  "id": "id0",
  "created": "created0",
  "modified": "modified8",
  "creator": "String9",
  "modifier": "modifier4"
}
```

