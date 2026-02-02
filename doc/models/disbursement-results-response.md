
# Disbursement Results Response

## Structure

`DisbursementResultsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `disbursement` | string\|[DisbursementsResponse](../../doc/models/disbursements-response.md)\|null | Optional | The identifier of the Disbursement that this disbursementResult resource refers to. | getDisbursement(): | setDisbursement( disbursement): void |
| `disbursementRef` | string\|[DisbursementRefsResponse](../../doc/models/disbursement-refs-response.md)\|null | Optional | The ID of the disbursementRef for which this result is recorded. | getDisbursementRef(): | setDisbursementRef( disbursementRef): void |
| `code` | [`?string(DisbursementResultCodeEnum)`](../../doc/models/disbursement-result-code-enum.md) | Optional | The code identifying the disbursement result.<br><br><details><br><summary>Valid Values</summary> <br>- `pending` - **Disbursement processing is pending account verification.**<br>- `internal` - **Failed. Internal note and/or failure.**<br><br>- `nsf` - **Failed. Disbursement return due to insufficient funds.**<br><br>- `badAccount` - **Failed. Disbursement return due to incorrect payment account information.**<br><br>- `unauthorized` - **Failed. Disbursement return due to customer dispute of authorization.**<br><br>- `general` - **General note and/or failure.**<br><br>- `noc` - **Notice of change.**<br><br>- `parameter` - **Disbursement processing withheld due to parameter configuration.**<br><br>- `sameDay` - **Failed. Same-day processing note and/or failure.**<br><br>- `transferDetails` - **Trace number note and/or data.**<br><br>- `platform` - **Failed. Processor note and/or failure.**<br><br></details><br> | getCode(): ?string | setCode(?string code): void |
| `originalCode` | `?string` | Optional | The original, unmapped code as received from the processor for this result. | getOriginalCode(): ?string | setOriginalCode(?string originalCode): void |
| `platform` | [`?string(DisbursementResultsPlatformEnum)`](../../doc/models/disbursement-results-platform-enum.md) | Optional | The platform used to process this Disbursement.<br><br><details><br><summary>Valid Values</summary><br>- `ELAVON`  - **The Elavon processor.**<br>- `VANTIV`  - **The Worldpay (aka Vantiv or Litle) eComm (aka VAP) processor.**<br><br>- `VCORE` - **The Worldpay (aka Vantiv) Core processor.**<br><br>- `TDBANK` - **External funding with TD Bank via the Operating Account.**<br><br>- `TDBANKCA` - **External funding with TD Bank Canada via the Operating Account.**<br><br>- `WELLSACH` - **The Wells Fargo ACH processor.**<br><br>- `WELLSFARGO` - **The Wells Fargo Merchant Services processor.**<br><br>- `WFSINGLE` - **The WFSINGLE processor.**<br><br>- `WORLDPAY` - **The WORLDPAY processor.**<br><br></details><br> | getPlatform(): ?string | setPlatform(?string platform): void |
| `message` | `?string` | Optional | The message string for this result. | getMessage(): ?string | setMessage(?string message): void |
| `amount` | `?int` | Optional | The amount of the disbursement relevant for this result. | getAmount(): ?int | setAmount(?int amount): void |
| `data` | `?string` | Optional | Data (the trace number, if applicable). | getData(): ?string | setData(?string data): void |

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

