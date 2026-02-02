
# Notes Post Request

## Structure

`NotesPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `login` | `?string` | Optional | The identifier of the Login that owns this notes resource. | getLogin(): ?string | setLogin(?string login): void |
| `txn` | `?string` | Optional | The identifier of the Txn that relates to this notes resource, Only one of txn, hold, entity, terminalTxn may be set. | getTxn(): ?string | setTxn(?string txn): void |
| `terminalTxn` | `?string` | Optional | The identifier of the TerminalTxn that relates to this notes resource, Only one of txn, hold, entity, terminalTxn may be set. | getTerminalTxn(): ?string | setTerminalTxn(?string terminalTxn): void |
| `hold` | `?string` | Optional | The identifier of the Hold that relates to this notes resource, Only one of txn, hold, entity, terminalTxn may be set. | getHold(): ?string | setHold(?string hold): void |
| `entity` | `?string` | Optional | The identifier of the Entity that relates to this notes resource, Only one of txn, hold, entity, terminalTxn may be set. | getEntity(): ?string | setEntity(?string entity): void |
| `type` | [`string(NoteTypeEnum)`](../../doc/models/note-type-enum.md) | Required | The desired type to take on the referenced Note.<br><br><details><br><summary>Valid Values</summary><br>- `note` - **Just add a note to the hold.**<br>- `release` - **Release the hold for this Hold.**<br>- `review` - **Mark the hold as having been reviewed.**<br>- `reReview` - **If the hold was marked as reviewed, this will allow resetting the review.**<br>- `amexSales` - **If the entity does sales with amex.**<br>- `businessSales` - **If the entity does business direct sales.**<br>- `consumerSales` - **If the entity does consumer direct sales.**<br>- `deliverySchedule` - **The delivery schedule of the entity.**<br>- `immediateDeliveryPercent` - **The amount of immediate deliveries with 0 day after the transaction.**<br>- `sevenDayDeliveryPercent` - **The amount of deliveries between 1-7 days after the transaction.**<br>- `fourteenDayDeliveryPercent` - **The amount of deliveries between 8-14 days after the transaction.**<br>- `thirtyDayDeliveryPercent` - **The amount of deliveries between 15-30 days after the transaction.**<br>- `cardPresentSales` - **If the entity does sales with card present.**<br>- `motoSales` - **If the entity does sales over the phone or mail.**<br>- `ecommerceSales` - **If the entity does ecommerce sales.**<br>- `siteVisit` - **If the entity had the site visit.**<br>- `goodsSold` - **The type of goods the entity sales.**<br>- `authorizationFlatFee` - **The flat fee agreement for each authorization.**<br>- `capturePercentFee` - **The percentage fee agreement for each capture.**<br>- `captureFlatFee` - **The flat fee agreement for each capture.**<br>- `riskApproved` - **The entity was approved.**<br>- `riskPending` - **The entity is in pending status.**<br>- `riskCancelled` - **The entity has a cancelled status.**<br>- `riskDenied` - **The entity has a denied status.**<br>- `riskClosed` - **The entity has a closed status.**<br>- `riskInvestigation` - **The entity is in investigation status.**<br>- `riskPendingData` - **Pending Docs/Info for The entity.**<br>- `riskFundsReleased` - **Funds released for The entity.**<br>- `riskActivityApproved` - **Activity approved for the entity.**<br></details><br> | getType(): string | setType(string type): void |
| `data` | `?string` | Optional | Free-form text for adding a message along with the type ,<br>required in case of type value is in one of these - amexSales, businessSales, consumerSales, deliverySchedule, immediateDeliveryPercent, sevenDayDeliveryPercent, fourteenDayDeliveryPercent, thirtyDayDeliveryPercent, cardPresentSales, motoSales, ecommerceSales, siteVisit, goodsSold, authorizationFlatFee, capturePercentFee, captureFlatFee<br>else null | getData(): ?string | setData(?string data): void |
| `note` | `?string` | Optional | A Message/Note regarding this notes resource. This field is stored as a text string. | getNote(): ?string | setNote(?string note): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |
| `noteDocuments` | [`?(NoteDocumentsPostRequest[])`](../../doc/models/note-documents-post-request.md) | Optional | - | getNoteDocuments(): ?array | setNoteDocuments(?array noteDocuments): void |

## Example (as JSON)

```json
{
  "login": "p1_log_00c59f2b74896e4086c2fe6",
  "type": "note",
  "hold": "t1_hld_67e08f086e275ddcc8820e1",
  "txn": "t1_txn_67ea9ac271f195a95059550",
  "terminalTxn": "identifier",
  "entity": "p1_ent_00c1ff2d61b43ffab63cec5",
  "note": "Raised HT limit",
  "data": "amexSales",
  "inactive": 0,
  "frozen": 0
}
```

