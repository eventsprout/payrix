
# Txns Put Request

## Structure

`TxnsPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `batch` | `?string` | Optional | If the Transaction is linked to a Batch, this field specifies the identifier of the Batch. | getBatch(): ?string | setBatch(?string batch): void |
| `debtRepayment` | [`?int(TxnsDebtRepaymentEnum)`](../../doc/models/txns-debt-repayment-enum.md) | Optional | If this transaction is for debt repayment or not for debt repayment.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Transaction not for debt repayment.**<br>- `1` - **Transaction for debt repayment.**<br><br></details><br>**Default**: `TxnsDebtRepaymentEnum::OFF`<br> | getDebtRepayment(): ?int | setDebtRepayment(?int debtRepayment): void |
| `processedSequence` | `?int` | Optional | For entry creation and deletion job sequencing: the current processed sequence number for this transaction. | getProcessedSequence(): ?int | setProcessedSequence(?int processedSequence): void |
| `funded` | `?int` | Optional | A date indicating when this Transaction was funded.<br>This field is set automatically. | getFunded(): ?int | setFunded(?int funded): void |
| `returned` | `?string` | Optional | The transaction has been returned by the receiver. | getReturned(): ?string | setReturned(?string returned): void |
| `fundingEnabled` | [`?int(TxnsFundingEnabledEnum)`](../../doc/models/txns-funding-enabled-enum.md) | Optional | Whether or not funding is enabled for this Transaction.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Disabled.**<br>- `1` - **Enabled.**<br><br></details><br> | getFundingEnabled(): ?int | setFundingEnabled(?int fundingEnabled): void |
| `requestSequence` | `?int` | Optional | For entry creation and deletion job sequencing: the current processed sequence number for this transaction. | getRequestSequence(): ?int | setRequestSequence(?int requestSequence): void |
| `token` | `?string` | Optional | The token of the Tokens resource this Transaction is associated with. | getToken(): ?string | setToken(?string token): void |
| `authTokenCustomer` | `?string` | Optional | The customer identifier from the AuthToken used during authentication. | getAuthTokenCustomer(): ?string | setAuthTokenCustomer(?string authTokenCustomer): void |
| `channel` | `?string` | Optional | This field is stored as a text string and must be between 0 and 1000 characters long. | getChannel(): ?string | setChannel(?string channel): void |
| `clientIp` | `?string` | Optional | The client ip address from which the Transaction was created.<br>Valid values are any Ipv4 or Ipv6 address. | getClientIp(): ?string | setClientIp(?string clientIp): void |
| `currency` | [`?string(CurrencyEnum)`](../../doc/models/currency-enum.md) | Optional | The currency for this transaction. See <a href="https://www.iban.com/currency-codes" target="_blank">Currency codes</a>  for all valid values.<br><br>**Default**: `CurrencyEnum::USD` | getCurrency(): ?string | setCurrency(?string currency): void |
| `feeConsumed` | `?int` | Optional | When fee is set, this will track the amount of the fee that has been consumed.<br>This field is specified as an integer in cents. | getFeeConsumed(): ?int | setFeeConsumed(?int feeConsumed): void |
| `signature` | [`?int(TerminalTxnsSignatureEnum)`](../../doc/models/terminal-txns-signature-enum.md) | Optional | Whether a signature should be captured during this Transaction.<br><br>* You can set this field if you want the terminal to take a signature for the Transaction.<br>* The API also sets this field automatically if you associate a signature to the Transaction by creating a 'terminalTxnDatas' resource.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not captured.**<br>- `1` - **Captured.**<br></details><br> | getSignature(): ?int | setSignature(?int signature): void |
| `tmxSessionId` | `?string` | Optional | Threatmetrix session ID, used to trace the financial session and prevent possible frauds. | getTmxSessionId(): ?string | setTmxSessionId(?string tmxSessionId): void |
| `firstTxn` | `?string` | Optional | For external recurring systems, this is the first transaction ID related to this recurring payment. | getFirstTxn(): ?string | setFirstTxn(?string firstTxn): void |

## Example (as JSON)

```json
{
  "currency": "USD",
  "batch": "t1_bth_67b6129bcca1cbb7cdac000",
  "debtRepayment": 1,
  "processedSequence": 0,
  "funded": 623,
  "returned": "Returned Transaction",
  "fundingEnabled": 1,
  "requestSequence": 1,
  "token": "7f36eeabbdce941fb564243936402a00",
  "authTokenCustomer": "Customer Identifier",
  "channel": "LA",
  "clientIp": "216.80.4.000",
  "signature": 1,
  "tmxSessionId": "Threatmetrix session ID",
  "firstTxn": "t1_txn_67b6129bcca1cbb7cdac001"
}
```

