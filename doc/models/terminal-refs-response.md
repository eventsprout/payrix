
# Terminal Refs Response

## Structure

`TerminalRefsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of this resource. | getId(): ?string | setId(?string id): void |
| `created` | `?string` | Optional | The date and time at which this resource was created. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getCreated(): ?string | setCreated(?string created): void |
| `modified` | `?string` | Optional | The date and time at which this resource was modified. The format should be YYYY-MM-DD HH:MM:SS.SSSS<br><br>**Constraints**: *Pattern*: `^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.\d{4}$` | getModified(): ?string | setModified(?string modified): void |
| `creator` | string\|[LoginsResponse](../../doc/models/logins-response.md)\|null | Optional | The identifier of the Login that created this resource. | getCreator(): | setCreator( creator): void |
| `modifier` | `?string` | Optional | The identifier of the Login that last modified this resource. | getModifier(): ?string | setModifier(?string modifier): void |
| `terminal` | `?string` | Optional | The identifier of the Terminal that owns this terminalRefs resource. | getTerminal(): ?string | setTerminal(?string terminal): void |
| `ref` | `?string` | Optional | The reference code itself. This field is stored as a text string and must be between 0 and 50 characters long. | getRef(): ?string | setRef(?string ref): void |
| `stage` | [`?string(TerminalRefStageEnum)`](../../doc/models/terminal-ref-stage-enum.md) | Optional | An indicator showing what this terminalRef refers to, such as 'create', 'pid', 'tid', 'token', or 'ctid'.<br><br><details><br><summary>Valid Values</summary><br>- `create`  -  **Terminal Creation**<br>- `pid`  -  **Platform ID**<br>- `tid`  -  **Terminal ID**<br>- `token`  -  **Token ID**<br>- `ctid`  -  **Custom Terminal ID**<br></details><br> | getStage(): ?string | setStage(?string stage): void |
| `platform` | [`?string(TerminalRefPlatformEnum)`](../../doc/models/terminal-ref-platform-enum.md) | Optional | The platform that issued this terminalRef.<br><br><details><br><summary>Valid Values</summary><br>- `ELAVON` - **ELAVON Payments Platform.**<br>- `FIRSTDATA` - **FirstData Payments Platform.**<br>- `VCORE` - **WorldPay / Vantiv Core Payments Platform.**<br>- `VANTIV` - **WorldPay / Vantiv eComm Payments (VAP) Platform.**<br>- `WELLSFARGO` - **Wells Fargo Merchant Services Payments Platform.**<br>- `SOUNDPAYMENTS` - **SoundPayments EMV and POS Payments Platform.**<br>- `PAYRIX` - **Payrix Merchant Payments Platform.**<br></details><br> | getPlatform(): ?string | setPlatform(?string platform): void |
| `processor` | [`?string(TerminalRefsProcessorEnum)`](../../doc/models/terminal-refs-processor-enum.md) | Optional | The processor that issued this terminalTxnRef.<br><br><details><br><summary>Valid Values</summary><br>- `APPLE` - **APPLE**<br>- `ELAVON` - **ELAVON**<br>- `FIRSTDATA` - **FIRSTDATA**<br>- `GOOGLE` - **GOOGLE**<br>- `VANTIV` - **VANTIV**<br>- `VCORE` - **VCORE**<br>- `WELLSACH` - **WELLSACH**<br>- `WELLSFARGO` - **WELLSFARGO**<br>- `WFSINGLE` - **WFSINGLE**<br>- `WORLDPAY` - **WORLDPAY**<br>- `TDBANKCA` - **TDBANKCA**<br></details><br> | getProcessor(): ?string | setProcessor(?string processor): void |

## Example (as JSON)

```json
{
  "processor": "VCORE",
  "id": "id4",
  "created": "created4",
  "modified": "modified8",
  "creator": "String3",
  "modifier": "modifier2"
}
```

