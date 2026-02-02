
# Terminal Refs Post Request

## Structure

`TerminalRefsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `terminal` | `string` | Required | The identifier of the Terminal that owns this terminalRefs resource. | getTerminal(): string | setTerminal(string terminal): void |
| `ref` | `string` | Required | The reference code itself. This field is stored as a text string and must be between 0 and 50 characters long. | getRef(): string | setRef(string ref): void |
| `stage` | [`string(TerminalRefStageEnum)`](../../doc/models/terminal-ref-stage-enum.md) | Required | An indicator showing what this terminalRef refers to, such as 'create', 'pid', 'tid', 'token', or 'ctid'.<br><br><details><br><summary>Valid Values</summary><br>- `create`  -  **Terminal Creation**<br>- `pid`  -  **Platform ID**<br>- `tid`  -  **Terminal ID**<br>- `token`  -  **Token ID**<br>- `ctid`  -  **Custom Terminal ID**<br></details><br> | getStage(): string | setStage(string stage): void |
| `platform` | [`string(TerminalRefPlatformEnum)`](../../doc/models/terminal-ref-platform-enum.md) | Required | The platform that issued this terminalRef.<br><br><details><br><summary>Valid Values</summary><br>- `ELAVON` - **ELAVON Payments Platform.**<br>- `FIRSTDATA` - **FirstData Payments Platform.**<br>- `VCORE` - **WorldPay / Vantiv Core Payments Platform.**<br>- `VANTIV` - **WorldPay / Vantiv eComm Payments (VAP) Platform.**<br>- `WELLSFARGO` - **Wells Fargo Merchant Services Payments Platform.**<br>- `SOUNDPAYMENTS` - **SoundPayments EMV and POS Payments Platform.**<br>- `PAYRIX` - **Payrix Merchant Payments Platform.**<br></details><br> | getPlatform(): string | setPlatform(string platform): void |
| `processor` | [`string(TerminalRefsProcessorEnum)`](../../doc/models/terminal-refs-processor-enum.md) | Required | The processor that issued this terminalTxnRef.<br><br><details><br><summary>Valid Values</summary><br>- `APPLE` - **APPLE**<br>- `ELAVON` - **ELAVON**<br>- `FIRSTDATA` - **FIRSTDATA**<br>- `GOOGLE` - **GOOGLE**<br>- `VANTIV` - **VANTIV**<br>- `VCORE` - **VCORE**<br>- `WELLSACH` - **WELLSACH**<br>- `WELLSFARGO` - **WELLSFARGO**<br>- `WFSINGLE` - **WFSINGLE**<br>- `WORLDPAY` - **WORLDPAY**<br>- `TDBANKCA` - **TDBANKCA**<br></details><br> | getProcessor(): string | setProcessor(string processor): void |

## Example (as JSON)

```json
{
  "terminal": "terminal8",
  "ref": "ref0",
  "stage": "ctid",
  "platform": "VANTIV",
  "processor": "VCORE"
}
```

