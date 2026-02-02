
# Txn Refs Response

## Structure

`TxnRefsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `txn` | `?string` | Optional | The parent transaction that owns this txnRef and to which this reference applies. | getTxn(): ?string | setTxn(?string txn): void |
| `ref` | `?string` | Optional | The reference value retrieved from the third party (platform). | getRef(): ?string | setRef(?string ref): void |
| `stage` | [`?string(TxnRefStageEnum)`](../../doc/models/txn-ref-stage-enum.md) | Optional | An indicator showing what this txnRef refers to, such as auth, capture, draft, file, refund, or an unknown value.<br><br><details><br><summary>Valid Values</summary><br>- `auth`  -  **Related to transaction authorization stage.**<br>- `capture`  -  **Related to transaction capture stage.**<br>- `draft`  -  **Transaction is in draft stage. Draft locator for transaction.**<br>- `file`  -  **Import Transaction Reference file.**<br>- `refund`  -  **Related to transaction refund stage.**<br>- `retrieval`  -  **A reference to the retrieval number (a reference exchanged with the processor for later cross-reference).**<br>- `threatMetrix`  -  **Threat Matrix.**<br></details><br> | getStage(): ?string | setStage(?string stage): void |
| `platform` | [`?string(PlatformModelEnum)`](../../doc/models/platform-model-enum.md) | Optional | The platform used to process this resource.<br><br><details><br><summary>Valid Values</summary><br>- `APPLE` - **The Apple Payment Processor.**<br>- `ELAVON` - **The Elavon processor.**<br>- `FIRSTDATA` - **The FirstData processor.**<br>- `GOOGLE` - **The Google Payment Processor.**<br>- `VANTIV` - **The WorldPay (aka Vantiv or Litle) eComm (aka VAP) processor.**<br>- `VCORE` - **The WorldPay (aka Vantiv) Core processor.**<br>- `TDBANKCA` - **External funding with TD Bank Canada via the Operating Account.**<br>- `WELLSACH` - **The Wells Fargo ACH processor.**<br>- `WELLSFARGO` - **The Wells Fargo Merchant Services processor.**<br>- `WFSINGLE` - **The WFSINGLE processor.**<br>- `WORLDPAY` - **The WORLDPAY processor.**<br></details><br> | getPlatform(): ?string | setPlatform(?string platform): void |

## Example (as JSON)

```json
{
  "id": "id2",
  "created": "created2",
  "modified": "modified0",
  "creator": "String1",
  "modifier": "modifier6"
}
```

