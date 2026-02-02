
# Terminal Txn Ref Post Request

## Structure

`TerminalTxnRefPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `terminalTxn` | `string` | Required | The parent terminalTxn that owns this terminalTxnRef and to which this reference applies A single terminalTxn may have many terminalTxnRef records. | getTerminalTxn(): string | setTerminalTxn(string terminalTxn): void |
| `ref` | `string` | Required | The reference value retrieved from the third party. | getRef(): string | setRef(string ref): void |
| `stage` | [`string(TerminalTxnRefStageEnum)`](../../doc/models/terminal-txn-ref-stage-enum.md) | Required | An indicator showing what this terminalTxnRef refers to.<br><br><details><br><summary>Valid Values</summary><br>- `activation` - **Terminal Activation**<br>- `auth` - **Transaction Authorization**<br>- `draft` - **Transaction Draft Number**<br>- `file` - **Import File Ref**<br>- `retrieval` - **Transaction Retrieval Number**<br></details><br> | getStage(): string | setStage(string stage): void |
| `platform` | [`string(PlatformModelEnum)`](../../doc/models/platform-model-enum.md) | Required | The platform used to process this resource.<br><br><details><br><summary>Valid Values</summary><br>- `APPLE` - **The Apple Payment Processor.**<br>- `ELAVON` - **The Elavon processor.**<br>- `FIRSTDATA` - **The FirstData processor.**<br>- `GOOGLE` - **The Google Payment Processor.**<br>- `VANTIV` - **The WorldPay (aka Vantiv or Litle) eComm (aka VAP) processor.**<br>- `VCORE` - **The WorldPay (aka Vantiv) Core processor.**<br>- `TDBANKCA` - **External funding with TD Bank Canada via the Operating Account.**<br>- `WELLSACH` - **The Wells Fargo ACH processor.**<br>- `WELLSFARGO` - **The Wells Fargo Merchant Services processor.**<br>- `WFSINGLE` - **The WFSINGLE processor.**<br>- `WORLDPAY` - **The WORLDPAY processor.**<br></details><br> | getPlatform(): string | setPlatform(string platform): void |

## Example (as JSON)

```json
{
  "terminalTxn": "t1_ttx_6806cde42b47ee61cdf6ab9",
  "ref": "MCC000012",
  "stage": "auth",
  "platform": "VCORE"
}
```

