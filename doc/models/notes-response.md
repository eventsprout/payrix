
# Notes Response

## Structure

`NotesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `login` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that owns this notes resource. | getLogin(): | setLogin( login): void |
| `hold` | string\|[HoldsResponse](../../doc/models/holds-response.md)\|null | Optional | The identifier of the Hold that relates to this notes resource. | getHold(): | setHold( hold): void |
| `txn` | string\|[TxnsResponse](../../doc/models/txns-response.md)\|null | Optional | The identifier of the Txn that relates to this notes resource. | getTxn(): | setTxn( txn): void |
| `terminalTxn` | string\|Terminal[TxnsResponse](../../doc/models/txns-response.md)\|null | Optional | The identifier of the TerminalTxn that relates to this notes resource. | getTerminalTxn(): | setTerminalTxn( terminalTxn): void |
| `entity` | string\|[EntitiesResponse](../../doc/models/entities-response.md)\|null | Optional | The identifier of the Entity that relates to this notes resource. | getEntity(): | setEntity( entity): void |
| `type` | [`?string(NoteTypeEnum)`](../../doc/models/note-type-enum.md) | Optional | The desired type to take on the referenced Note.<br><br><details><br><summary>Valid Values</summary><br>- `note` - **Just add a note to the hold.**<br>- `release` - **Release the hold for this Hold.**<br>- `review` - **Mark the hold as having been reviewed.**<br>- `reReview` - **If the hold was marked as reviewed, this will allow resetting the review.**<br>- `amexSales` - **If the entity does sales with amex.**<br>- `businessSales` - **If the entity does business direct sales.**<br>- `consumerSales` - **If the entity does consumer direct sales.**<br>- `deliverySchedule` - **The delivery schedule of the entity.**<br>- `immediateDeliveryPercent` - **The amount of immediate deliveries with 0 day after the transaction.**<br>- `sevenDayDeliveryPercent` - **The amount of deliveries between 1-7 days after the transaction.**<br>- `fourteenDayDeliveryPercent` - **The amount of deliveries between 8-14 days after the transaction.**<br>- `thirtyDayDeliveryPercent` - **The amount of deliveries between 15-30 days after the transaction.**<br>- `cardPresentSales` - **If the entity does sales with card present.**<br>- `motoSales` - **If the entity does sales over the phone or mail.**<br>- `ecommerceSales` - **If the entity does ecommerce sales.**<br>- `siteVisit` - **If the entity had the site visit.**<br>- `goodsSold` - **The type of goods the entity sales.**<br>- `authorizationFlatFee` - **The flat fee agreement for each authorization.**<br>- `capturePercentFee` - **The percentage fee agreement for each capture.**<br>- `captureFlatFee` - **The flat fee agreement for each capture.**<br>- `riskApproved` - **The entity was approved.**<br>- `riskPending` - **The entity is in pending status.**<br>- `riskCancelled` - **The entity has a cancelled status.**<br>- `riskDenied` - **The entity has a denied status.**<br>- `riskClosed` - **The entity has a closed status.**<br>- `riskInvestigation` - **The entity is in investigation status.**<br>- `riskPendingData` - **Pending Docs/Info for The entity.**<br>- `riskFundsReleased` - **Funds released for The entity.**<br>- `riskActivityApproved` - **Activity approved for the entity.**<br></details><br> | getType(): ?string | setType(?string type): void |
| `note` | `?string` | Optional | A Message/Note regarding this notes resource.<br>This field is stored as a text string. | getNote(): ?string | setNote(?string note): void |
| `data` | `?string` | Optional | Free-form text for adding a message along with the type. | getData(): ?string | setData(?string data): void |
| `pinned` | `?int` | Optional | Flag to determine if a note has been pinned or not.. | getPinned(): ?int | setPinned(?int pinned): void |
| `pinnedDate` | `?string` | Optional | The timestamp indicating the date and time when a note was pinned. The format should be YYYY-MM-DD HH:MM:SS.<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}$` | getPinnedDate(): ?string | setPinnedDate(?string pinnedDate): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `noteDocuments` | [`?(NoteDocumentsResponse[])`](../../doc/models/note-documents-response.md) | Optional | - | getNoteDocuments(): ?array | setNoteDocuments(?array noteDocuments): void |

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

