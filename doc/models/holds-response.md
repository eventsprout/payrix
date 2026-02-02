
# Holds Response

## Structure

`HoldsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that owns this holds resource. | getLogin(): | setLogin( login): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity associated with this Hold resource. | getEntity(): | setEntity( entity): void |
| `txn` | string\|[TxnsResponse](../../doc/models/txns-response.md)\|null | Optional | The identifier of the Txn that is being held with this hold. | getTxn(): | setTxn( txn): void |
| `terminalTxn` | string\|Terminal[TxnsResponse](../../doc/models/txns-response.md)\|null | Optional | The TerminalTxn id in which this Hold belongs to. | getTerminalTxn(): | setTerminalTxn( terminalTxn): void |
| `account` | string\|[AccountsResponse](../../doc/models/accounts-response.md)\|null | Optional | The identifier of the Account that owns this holds resource. | getAccount(): | setAccount( account): void |
| `verification` | string\|[VerificationsResponse](../../doc/models/verifications-response.md)\|null | Optional | If this hold resource was triggered through a verification, then this field stores the identifier of the Verification. | getVerification(): | setVerification( verification): void |
| `verificationRef` | string\|[VerificationRefsResponse](../../doc/models/verification-refs-response.md)\|null | Optional | If this hold resource was triggered through Payrix Integration Risk, then this field stores the identifier of the VerificationRef. | getVerificationRef(): | setVerificationRef( verificationRef): void |
| `decisionAction` | string\|[DecisionActionsResponse](../../doc/models/decision-actions-response.md)\|null | Optional | The identifier of the DecisionAction associated with this Hold resource. | getDecisionAction(): | setDecisionAction( decisionAction): void |
| `action` | [`?int(HoldActionEnum)`](../../doc/models/hold-action-enum.md) | Optional | The action taken on the referenced Txn. Block, Hold, or Reserve it.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **NONE**<br>- `1` - **Block.** Block the Transaction from proceeding. This returns an error.<br>- `3` - **Hold.** Hold the Transaction. It will not be captured until it is manually released.<br>- `4` - **Reserve** Reserve the Transaction. The funds for the transaction will not be released until the Transaction is manually reviewed.<br>- `5` - **LIMIT** Block current activity.<br>- `6` - **PASS** Passed decision(s).<br>- `8` - **POSTREVIEWONLY** Passed decision(s).<br></details><br> | getAction(): ?int | setAction(?int action): void |
| `released` | `?string` | Optional | If this hold was released, this will contain the timestamp for when it was released. The format should be YYYY-MM-DD HH:MM:SS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}$` | getReleased(): ?string | setReleased(?string released): void |
| `reviewed` | `?string` | Optional | If this hold was reviewed, this will contain the timestamp for when it was reviewed. The format should be YYYY-MM-DD HH:MM:SS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}$` | getReviewed(): ?string | setReviewed(?string reviewed): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `releaseAction` | [`?int(HoldsReleaseActionEnum)`](../../doc/models/holds-release-action-enum.md) | Optional | The final action taken on the hold while it's been released.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Holds released because the hold resource was approved.**<br>- `2` - **Holds released because the hold resource was cancelled.**<br>- `3` - **Holds released because the hold resource was refunded.**<br>- `4` - **Holds released because the hold resource was failed.**<br>- `5` - **Expired.**<br></details><br> | getReleaseAction(): ?int | setReleaseAction(?int releaseAction): void |
| `delayedFundingStartDate` | `?string` | Optional | The timestamp when hold was considered to be delaying funding. The format should be YYYY-MM-DD HH:MM:SS.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}$` | getDelayedFundingStartDate(): ?string | setDelayedFundingStartDate(?string delayedFundingStartDate): void |
| `delayedFundingEndDate` | `?string` | Optional | The timestamp when hold stopped delaying funding, this might be due to the hold been released, cancelled or funded. The format should be YYYY-MM-DD HH:MM:SS.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}$` | getDelayedFundingEndDate(): ?string | setDelayedFundingEndDate(?string delayedFundingEndDate): void |
| `analyst` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The person who review the hold applied. | getAnalyst(): | setAnalyst( analyst): void |
| `claimed` | `?string` | Optional | The timestamp for the most recent update of the analyst field. The format should be YYYY-MM-DD HH:MM:SS.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}$` | getClaimed(): ?string | setClaimed(?string claimed): void |
| `holdSource` | [`?string(HoldsHoldSourceEnum)`](../../doc/models/holds-hold-source-enum.md) | Optional | Field created to know the reason for why a hold was created.<br><br><details><br><summary>Valid Values</summary><br>- `DS_MODEL_POLICY_RUN` - **DS_MODEL_POLICY_RUN**<br>- `API_DECISION` - **API_DECISION**<br>- `POLICY_RUN` - **POLICY_RUN**<br>- `RISK_ALERT` - **RISK_ALERT**<br>- `MANUAL` - **MANUAL**<br>- `ERROR` - **ERROR**<br></details><br> | getHoldSource(): ?string | setHoldSource(?string holdSource): void |
| `holdSourceId` | `?string` | Optional | Reason id for why a hold was created. | getHoldSourceId(): ?string | setHoldSourceId(?string holdSourceId): void |
| `holdSourceDetails` | `?string` | Optional | It adds details to hold source. | getHoldSourceDetails(): ?string | setHoldSourceDetails(?string holdSourceDetails): void |
| `division` | `?string` | Optional | ID of the division associated with this vendor | getDivision(): ?string | setDivision(?string division): void |
| `messageThread` | [`?(MessageThreadsResponse[])`](../../doc/models/message-threads-response.md) | Optional | - | getMessageThread(): ?array | setMessageThread(?array messageThread): void |
| `notes` | [`?(NotesResponse[])`](../../doc/models/notes-response.md) | Optional | - | getNotes(): ?array | setNotes(?array notes): void |
| `reserveEntries` | [`?(ReserveEntriesResponse[])`](../../doc/models/reserve-entries-response.md) | Optional | - | getReserveEntries(): ?array | setReserveEntries(?array reserveEntries): void |
| `reserve` | [`?ReservesResponse`](../../doc/models/reserves-response.md) | Optional | - | getReserve(): ?ReservesResponse | setReserve(?ReservesResponse reserve): void |

## Example (as JSON)

```json
{
  "inactive": 0,
  "frozen": 0,
  "id": "id4",
  "created": "created4",
  "modified": "modified2",
  "creator": "String3",
  "modifier": "modifier8"
}
```

