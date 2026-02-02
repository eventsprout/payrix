
# Terminal Txns Put Request

## Structure

`TerminalTxnsPutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `binType` | [`?string(TerminalTxnsBinTypeEnum)`](../../doc/models/terminal-txns-bin-type-enum.md) | Optional | The type of bank issuer number (BIN) that allows for resulting transactions.<br><br><details><br><summary>Valid Values</summary><br>- `CREDIT` - **Credit BIN Type.**<br>- `DEBIT` - **Debit BIN Type.**<br>- `PREPAID` - **Prepaid BIN Type.**<br></details><br> | getBinType(): ?string | setBinType(?string binType): void |
| `expiration` | `?string` | Optional | The expiration date of this Transaction. This field is stored as a text string in 'MMYY' format, where 'MM' is the number of a month and 'YY' is the last two digits of a year. For example, '0623' for June 2023. The value must reflect a future date. | getExpiration(): ?string | setExpiration(?string expiration): void |
| `payment` | [`?TerminalTxnsPayment`](../../doc/models/terminal-txns-payment.md) | Optional | The payment method associated with this Transaction, including the card details. | getPayment(): ?TerminalTxnsPayment | setPayment(?TerminalTxnsPayment payment): void |
| `traceNumber` | `?int` | Optional | Sequencial number that uniquely identifies the terminalTxn. | getTraceNumber(): ?int | setTraceNumber(?int traceNumber): void |
| `txn` | `?string` | Optional | The related txn this terminalTxn belongs to. | getTxn(): ?string | setTxn(?string txn): void |
| `token` | `?string` | Optional | The ID of the token record to associate with this terminal transaction request. | getToken(): ?string | setToken(?string token): void |
| `paymentNumber` | `?int` | Optional | The last four numbers of the credit card associated with this Transaction. | getPaymentNumber(): ?int | setPaymentNumber(?int paymentNumber): void |
| `paymentMethod` | [`?int(TerminalTxnPaymentMethodEnum)`](../../doc/models/terminal-txn-payment-method-enum.md) | Optional | The payment method for this Transaction. | getPaymentMethod(): ?int | setPaymentMethod(?int paymentMethod): void |
| `tip` | `?int` | Optional | This field indicates the tip amount associated with a transaction. This value is for reporting purposes only, because transaction amount includes this amount in the total. | getTip(): ?int | setTip(?int tip): void |
| `originatingApp` | `?string` | Optional | Field identifying Payrix PAX terminal originating app. | getOriginatingApp(): ?string | setOriginatingApp(?string originatingApp): void |
| `oEMTTxnRefNumber` | `?string` | Optional | Field identifying original Payrix Verifone transaction reference number, used for refunds and cancellation request. | getOEMTTxnRefNumber(): ?string | setOEMTTxnRefNumber(?string oEMTTxnRefNumber): void |
| `posApplicationId` | `?string` | Optional | Express assigned identifier i.e. Software Id being used in express terminal. | getPosApplicationId(): ?string | setPosApplicationId(?string posApplicationId): void |
| `unattended` | [`?int(TerminalTxnsUnattendedEnum)`](../../doc/models/terminal-txns-unattended-enum.md) | Optional | Whether the card was swiped at an unattended terminal during this Transaction.<br>This field is set to '0' by default.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Attended terminal.**<br>- `1` - **Unattended terminal.**<br></details><br> | getUnattended(): ?int | setUnattended(?int unattended): void |
| `posApplicationName` | `?string` | Optional | Software Name being used in express terminal. | getPosApplicationName(): ?string | setPosApplicationName(?string posApplicationName): void |
| `posApplicationVersion` | `?string` | Optional | Software version being used in express terminal. | getPosApplicationVersion(): ?string | setPosApplicationVersion(?string posApplicationVersion): void |
| `customerReferenceNumber` | `?string` | Optional | Express Reference Number. | getCustomerReferenceNumber(): ?string | setCustomerReferenceNumber(?string customerReferenceNumber): void |
| `gatewayTransactionId` | `?string` | Optional | The gateway transaction ID relates to Express Transaction ID. | getGatewayTransactionId(): ?string | setGatewayTransactionId(?string gatewayTransactionId): void |
| `customerTicketNumber` | `?string` | Optional | Express ticket Number. | getCustomerTicketNumber(): ?string | setCustomerTicketNumber(?string customerTicketNumber): void |
| `clientIp` | `?string` | Optional | The client IP address from which the transaction was created, valid values are any IPv4 or IPv6 address. | getClientIp(): ?string | setClientIp(?string clientIp): void |
| `description` | `?string` | Optional | A description of this Transaction. This field is stored as a text string and must be between 0 and 1000 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `swiped` | [`?int(TerminalTxnsSwipedEnum)`](../../doc/models/terminal-txns-swiped-enum.md) | Optional | Whether the card was swiped during this Transaction.<br>This field is set to '1' automatically if 'track' data was received.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Swiped.**<br>- `1` - **Swiped.**<br></details><br> | getSwiped(): ?int | setSwiped(?int swiped): void |
| `emv` | [`?int(TerminalTxnsEmvEnum)`](../../doc/models/terminal-txns-emv-enum.md) | Optional | Whether the card was dipped (using the EMV chip) during this Transaction.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not dipped.**<br>- `1` - **Dipped.**<br></details><br> | getEmv(): ?int | setEmv(?int emv): void |
| `entryMode` | [`?int(EntryModeEnum)`](../../doc/models/entry-mode-enum.md) | Optional | How payment information has been entered, including manually keyed entries, card swipes with track 1 or 2 data received, card dips with EMV chip data received, contactless card reads with track or EMV data received, and ApplePay read with cryptogram data received.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Manually keyed entry.**<br>- `2` - **Card swiped. Track 1 received.**<br>- `3` - **Card swiped. Track 2 received.**<br>- `4` - **Card swiped. Track 1 & 2 received.**<br>- `5` - **Card dipped. EMV chip received.**<br>- `6` - **Contactless card read. Track or EMV data received.**<br>- `7` - **Track Data from Card Swipe after EMV chip failure.**<br>- `8` - **Track Data from Manually keyed entry after EMV chip failure.**<br>- `9` - **ApplePay**<br>- `10` - **Google Pay.**<br>- `11` - **Merchant created transaction.**<br>- `12` - **Invoice payment.**<br>- `13` - **Merchant created transaction in payrix portal.**<br>- `14` - **Invoice payment from payrix portal.**<br></details><br> | getEntryMode(): ?int | setEntryMode(?int entryMode): void |
| `first` | `?string` | Optional | The first name associated with this Transaction. For eCheck transactions, either first or last is required. | getFirst(): ?string | setFirst(?string first): void |
| `last` | `?string` | Optional | The last name associated with this Transaction. For eCheck transactions, either first or last is required. | getLast(): ?string | setLast(?string last): void |
| `middle` | `?string` | Optional | The middle name associated with this Transaction. | getMiddle(): ?string | setMiddle(?string middle): void |
| `order` | `?string` | Optional | The identifier of the Order associated with this Transaction, This field is stored as a text string and must be between 0 and 1000 characters long. | getOrder(): ?string | setOrder(?string order): void |
| `reserved` | [`?int(TerminalTxnReservedEnum)`](../../doc/models/terminal-txn-reserved-enum.md) | Optional | Indicates whether the Transaction is reserved and the action that will be taken as a result.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **No reserve.**<br></details><br> | getReserved(): ?int | setReserved(?int reserved): void |
| `signature` | [`?int(TerminalTxnsSignatureEnum)`](../../doc/models/terminal-txns-signature-enum.md) | Optional | Whether a signature should be captured during this Transaction.<br><br>* You can set this field if you want the terminal to take a signature for the Transaction.<br>* The API also sets this field automatically if you associate a signature to the Transaction by creating a 'terminalTxnDatas' resource.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not captured.**<br>- `1` - **Captured.**<br></details><br> | getSignature(): ?int | setSignature(?int signature): void |
| `total` | `?int` | Optional | The total amount of this Transaction, This field is specified as an integer in cents. | getTotal(): ?int | setTotal(?int total): void |
| `status` | [`?int(TerminalTxnStatusEnum)`](../../doc/models/terminal-txn-status-enum.md) | Optional | The status of the Transaction.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Pending.**<br>- `1` - **Approved.** Payments can be voided or cancelled.<br>- `2` - **Failed.**<br>- `3` - **Captured.** Payments can be refunded.<br>- `4` - **Settled.** Payments can be refunded.<br>- `5` - **Returned.** Payments have been successfully refunded.<br></details><br>**Default**: `TerminalTxnStatusEnum::PENDING`<br> | getStatus(): ?int | setStatus(?int status): void |
| `cardNetworkTransactionId` | `?string` | Optional | Card network transaction ID associated with this transaction. | getCardNetworkTransactionId(): ?string | setCardNetworkTransactionId(?string cardNetworkTransactionId): void |
| `omnitoken` | `?string` | Optional | The OmniToken associated with this Transaction. | getOmnitoken(): ?string | setOmnitoken(?string omnitoken): void |
| `convenienceFee` | `?int` | Optional | The amount of the total sum of this Transaction that is made up of convenience fee. Fee charged when card payment is an alternative form of payment not ordinarily accepted by a merchant or service provider. This field is specified as an integer in cents. [currently not active] | getConvenienceFee(): ?int | setConvenienceFee(?int convenienceFee): void |
| `surcharge` | `?int` | Optional | Surcharge amount included in the total amount of the transaction. A surcharge fee is an additional charge added to the price of a purchase when a customer pays with a credit card. This field is specified as an integer in cents. | getSurcharge(): ?int | setSurcharge(?int surcharge): void |
| `softPosDeviceTypeIndicator` | `?string` | Optional | The device type indicator for the terminal.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Apple (Worldpay as PSP)**<br>- `2` - **Android (Worldpay as PSP)**<br>- `3` - **Apple (Worldpay not PSP)**<br>- `4` - **Android (Worldpay not PSP)**<br></details><br> | getSoftPosDeviceTypeIndicator(): ?string | setSoftPosDeviceTypeIndicator(?string softPosDeviceTypeIndicator): void |
| `softPosId` | `?string` | Optional | The software POS ID. | getSoftPosId(): ?string | setSoftPosId(?string softPosId): void |
| `hsaFsaCardIndicator` | [`?int(TerminalTxnsHsaFsaCardIndicatorEnum)`](../../doc/models/terminal-txns-hsa-fsa-card-indicator-enum.md) | Optional | Indicates if the card is a Flexible Spending Account (FSA) or Health Savings Account (HSA) card.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not an HSA/FSA card.**<br>- `1` - **HSA/FSA card.**<br></details><br> | getHsaFsaCardIndicator(): ?int | setHsaFsaCardIndicator(?int hsaFsaCardIndicator): void |
| `gatewayTerminalId` | `?string` | Optional | The gateway terminal ID. | getGatewayTerminalId(): ?string | setGatewayTerminalId(?string gatewayTerminalId): void |
| `descriptor` | `?string` | Optional | The billing Descriptor that is used when the transaction is part of a subscription. | getDescriptor(): ?string | setDescriptor(?string descriptor): void |
| `cardNetworkBankNetReferenceNumber` | `?string` | Optional | The reference number associated with the card network. | getCardNetworkBankNetReferenceNumber(): ?string | setCardNetworkBankNetReferenceNumber(?string cardNetworkBankNetReferenceNumber): void |
| `cardNetworkBankNetSettlementDate` | `?string` | Optional | The settlement date associated with the card network. | getCardNetworkBankNetSettlementDate(): ?string | setCardNetworkBankNetSettlementDate(?string cardNetworkBankNetSettlementDate): void |
| `inactive` | [`?int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Optional | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): ?int | setInactive(?int inactive): void |
| `frozen` | [`?int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Optional | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): ?int | setFrozen(?int frozen): void |

## Example (as JSON)

```json
{
  "binType": "DEBIT",
  "expiration": "1123",
  "payment": {
    "method": 1,
    "number": "2222",
    "routing": "1",
    "expiration": "0623",
    "cvv": 123,
    "track": "Track 1"
  },
  "traceNumber": 853202,
  "txn": "related txn",
  "token": "124f2d0efab0bcda46f2118d688bbf97",
  "paymentNumber": 7,
  "paymentMethod": 2,
  "tip": 0,
  "originatingApp": "originatingApp",
  "OEMTTxnRefNumber": "TxnRefNumber",
  "posApplicationId": "15668",
  "unattended": 0,
  "posApplicationName": "XML Test Example",
  "posApplicationVersion": "1.00",
  "customerReferenceNumber": "123456",
  "gatewayTransactionId": "486689252",
  "customerTicketNumber": "123456",
  "clientIp": "Client IP address",
  "description": "Transaction1",
  "swiped": 1,
  "emv": 1,
  "entryMode": 1,
  "first": "John",
  "last": "Doe",
  "middle": "M",
  "order": "orderId",
  "reserved": 0,
  "signature": 1,
  "total": 8000,
  "status": 3,
  "cardNetworkTransactionId": "250630144026744",
  "omnitoken": "4445223322990007",
  "convenienceFee": 0,
  "surcharge": 0,
  "softPosDeviceTypeIndicator": "device type indicator",
  "softPosId": "software POS ID",
  "hsaFsaCardIndicator": 0,
  "gatewayTerminalId": "12",
  "descriptor": "billing Descriptor",
  "cardNetworkBankNetReferenceNumber": "cardNetworkBankNetReferenceNumber",
  "cardNetworkBankNetSettlementDate": "1123",
  "inactive": 0,
  "frozen": 0
}
```

