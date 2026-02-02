
# Terminal Txns Post Request

## Structure

`TerminalTxnsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `binType` | [`string(TerminalTxnsBinTypeEnum)`](../../doc/models/terminal-txns-bin-type-enum.md) | Required | The type of bank issuer number (BIN) that allows for resulting transactions.<br><br><details><br><summary>Valid Values</summary><br>- `CREDIT` - **Credit BIN Type.**<br>- `DEBIT` - **Debit BIN Type.**<br>- `PREPAID` - **Prepaid BIN Type.**<br></details><br> | getBinType(): string | setBinType(string binType): void |
| `expiration` | `?string` | Optional | The expiration date of this Transaction. This field is stored as a text string in 'MMYY' format, where 'MM' is the number of a month and 'YY' is the last two digits of a year. For example, '0623' for June 2023. The value must reflect a future date. | getExpiration(): ?string | setExpiration(?string expiration): void |
| `forterminalTxn` | `?string` | Optional | If this Terminal Transaction is related to another Terminal Transaction, then this field is set to the identifier of the other Terminal Transaction. For example, if this Terminal Transaction is a Refund, this field could be set to the identifier of the original Sale Terminal Transaction. | getForterminalTxn(): ?string | setForterminalTxn(?string forterminalTxn): void |
| `origin` | [`int(TerminalTxnOriginEnum)`](../../doc/models/terminal-txn-origin-enum.md) | Required | The origin of this Transaction.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Credit Card Terminal.**<br>- `2` - **eCommerce System.**<br>- `3` - **Mail or Telephone Order Transaction.**<br>- `4` - **Apple Pay (deprecated).**<br>- `5` - **Successful 3D Secure Transaction.**<br>- `6` - **Attempted 3D Secure Transaction.**<br>- `7` - **Deprecated. Recurring Card Transaction.**<br>- `8` - **Payframe.**<br>- `9` - **Writing.**<br></details><br>**Default**: `TerminalTxnOriginEnum::TERMINAL`<br> | getOrigin(): int | setOrigin(int origin): void |
| `platform` | [`?string(PlatformModelEnum)`](../../doc/models/platform-model-enum.md) | Optional | The platform used to process this resource.<br><br><details><br><summary>Valid Values</summary><br>- `APPLE` - **The Apple Payment Processor.**<br>- `ELAVON` - **The Elavon processor.**<br>- `FIRSTDATA` - **The FirstData processor.**<br>- `GOOGLE` - **The Google Payment Processor.**<br>- `VANTIV` - **The WorldPay (aka Vantiv or Litle) eComm (aka VAP) processor.**<br>- `VCORE` - **The WorldPay (aka Vantiv) Core processor.**<br>- `TDBANKCA` - **External funding with TD Bank Canada via the Operating Account.**<br>- `WELLSACH` - **The Wells Fargo ACH processor.**<br>- `WELLSFARGO` - **The Wells Fargo Merchant Services processor.**<br>- `WFSINGLE` - **The WFSINGLE processor.**<br>- `WORLDPAY` - **The WORLDPAY processor.**<br></details><br> | getPlatform(): ?string | setPlatform(?string platform): void |
| `pos` | [`int(TerminalTxnsPosEnum)`](../../doc/models/terminal-txns-pos-enum.md) | Required | Whether the terminalTxn is coming from a POS system that needs terminal activation.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **POS Terminal Activation.** (Internal)<br>- `1` - **External Terminal Activation.**<br></details><br> | getPos(): int | setPos(int pos): void |
| `receipt` | [`?string(TerminalTxnsReceiptEnum)`](../../doc/models/terminal-txns-receipt-enum.md) | Optional | Whether the terminal should print a receipt or not.<br><br><details><br><summary>Valid Values</summary><br>- `noReceipt` - **No Receipt.**<br>- `merchant` - **Merchant copy only.**<br>- `customer` - **Customer copy only.**<br>- `both` - **Merchant and Customer copy.**<br></details><br> | getReceipt(): ?string | setReceipt(?string receipt): void |
| `tid` | `?string` | Optional | The Terminal ID as set by the platform activating the terminal. This field is stored as a text string and must be between 0 and 50 characters long. | getTid(): ?string | setTid(?string tid): void |
| `traceNumber` | `?int` | Optional | Sequencial number that uniquely identifies the terminalTxn. | getTraceNumber(): ?int | setTraceNumber(?int traceNumber): void |
| `txn` | `?string` | Optional | The related txn this terminalTxn belongs to. | getTxn(): ?string | setTxn(?string txn): void |
| `token` | string\|[TokenPostRequest](../../doc/models/token-post-request.md)\|null | Optional | The ID of the token record to associate with this terminal transaction request. | getToken(): | setToken( token): void |
| `paymentNumber` | `?int` | Optional | The last four numbers of the credit card associated with this Transaction. | getPaymentNumber(): ?int | setPaymentNumber(?int paymentNumber): void |
| `paymentMethod` | [`?int(TerminalTxnPaymentMethodEnum)`](../../doc/models/terminal-txn-payment-method-enum.md) | Optional | The payment method for this Transaction. | getPaymentMethod(): ?int | setPaymentMethod(?int paymentMethod): void |
| `type` | [`int(TerminalTxnTypeEnum)`](../../doc/models/terminal-txn-type-enum.md) | Required | The type of Transaction.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Credit Card Only: Sale Transaction.** This is the most common type of Transaction, it processes a sale and charges the customer.<br>- `2` - **Credit Card Only: Auth Transaction.** Authorizes and holds the requested total on the credit card.<br>- `4` - **Credit Card Only: Reverse Authorization.** Reverses a prior Auth or Sale Transaction and releases the credit hold.<br>- `5` - **Credit Card Only: Refund Transaction.** Refunds a prior Capture or Sale Transaction (total may be specified for a partial refund).<br>- `13` - **Batch out terminal.**<br></details><br> | getType(): int | setType(int type): void |
| `tip` | `?int` | Optional | This field indicates the tip amount associated with a transaction. This value is for reporting purposes only, because transaction amount includes this amount in the total. | getTip(): ?int | setTip(?int tip): void |
| `originatingApp` | `?string` | Optional | Field identifying Payrix PAX terminal originating app. | getOriginatingApp(): ?string | setOriginatingApp(?string originatingApp): void |
| `oEMTTxnRefNumber` | `?string` | Optional | Field identifying original Payrix Verifone transaction reference number, used for refunds and cancellation request. | getOEMTTxnRefNumber(): ?string | setOEMTTxnRefNumber(?string oEMTTxnRefNumber): void |
| `posApplicationId` | `?string` | Optional | Express assigned identifier i.e. Software Id being used in express terminal. | getPosApplicationId(): ?string | setPosApplicationId(?string posApplicationId): void |
| `posApplicationName` | `?string` | Optional | Software Name being used in express terminal. | getPosApplicationName(): ?string | setPosApplicationName(?string posApplicationName): void |
| `posApplicationVersion` | `?string` | Optional | Software version being used in express terminal. | getPosApplicationVersion(): ?string | setPosApplicationVersion(?string posApplicationVersion): void |
| `customerReferenceNumber` | `?string` | Optional | Express Reference Number. | getCustomerReferenceNumber(): ?string | setCustomerReferenceNumber(?string customerReferenceNumber): void |
| `gatewayTransactionId` | `?string` | Optional | The gateway transaction ID relates to Express Transaction ID. | getGatewayTransactionId(): ?string | setGatewayTransactionId(?string gatewayTransactionId): void |
| `customerTicketNumber` | `?string` | Optional | Express ticket Number. | getCustomerTicketNumber(): ?string | setCustomerTicketNumber(?string customerTicketNumber): void |
| `authCode` | `?string` | Optional | The authorization code for this Transaction. This field is stored as a text string and must be between 0 and 20 characters long. | getAuthCode(): ?string | setAuthCode(?string authCode): void |
| `authDate` | `?int` | Optional | The date on which the Transaction was authorized. The date is specified as an eight digit string in YYYYMMDD format, for example, '20160120' for January 20, 2016. The value of this field must represent a date in the past. | getAuthDate(): ?int | setAuthDate(?int authDate): void |
| `cashback` | `?int` | Optional | The amount of the total sum of this Transaction that is given as cash back. This field is specified as an integer in cents. | getCashback(): ?int | setCashback(?int cashback): void |
| `clientIp` | `?string` | Optional | The client IP address from which the Transaction was created. Valid values are any Ipv4 or Ipv6 address. | getClientIp(): ?string | setClientIp(?string clientIp): void |
| `company` | `?string` | Optional | The name of the company associated with this Transaction. nSetting this field is especially important when processing an eCheck from a company. | getCompany(): ?string | setCompany(?string company): void |
| `currency` | [`?string(CurrencyEnum)`](../../doc/models/currency-enum.md) | Required | The currency for this transaction. See <a href="https://www.iban.com/currency-codes" target="_blank">Currency codes</a>  for all valid values.<br><br>**Default**: `CurrencyEnum::USD` | getCurrency(): ?string | setCurrency(?string currency): void |
| `fundingCurrency` | [`?string(CurrencyEnum)`](../../doc/models/currency-enum.md) | Required | The currency for which this transaction was funded on. See <a href="https://www.iban.com/currency-codes" target="_blank">Currency codes</a>  for all valid values.<br><br>**Default**: `CurrencyEnum::USD` | getFundingCurrency(): ?string | setFundingCurrency(?string fundingCurrency): void |
| `cvvStatus` | [`?string(TerminalTxnsCvvStatusEnum)`](../../doc/models/terminal-txns-cvv-status-enum.md) | Optional | The status of the CVV on the card.<br><br><details><br><summary>Valid Values</summary><br>- `notPresent` - **CVV is not present.**<br>- `illegible` - **CVV is illegible.**<br>- `notProvided` - **CVV was not provided.**<br></details><br> | getCvvStatus(): ?string | setCvvStatus(?string cvvStatus): void |
| `description` | `?string` | Optional | A description of this Transaction. This field is stored as a text string and must be between 0 and 1000 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `discount` | `?int` | Optional | The discount applied to the transaction. | getDiscount(): ?int | setDiscount(?int discount): void |
| `duty` | `?int` | Optional | The duty fee applicable to this transaction. | getDuty(): ?int | setDuty(?int duty): void |
| `email` | `?string` | Optional | The email associated with this Transaction. | getEmail(): ?string | setEmail(?string email): void |
| `swiped` | [`int(TerminalTxnsSwipedEnum)`](../../doc/models/terminal-txns-swiped-enum.md) | Required | Whether the card was swiped during this Transaction.<br>This field is set to '1' automatically if 'track' data was received.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Swiped.**<br>- `1` - **Swiped.**<br></details><br> | getSwiped(): int | setSwiped(int swiped): void |
| `entryMode` | [`?int(EntryModeEnum)`](../../doc/models/entry-mode-enum.md) | Optional | How payment information has been entered, including manually keyed entries, card swipes with track 1 or 2 data received, card dips with EMV chip data received, contactless card reads with track or EMV data received, and ApplePay read with cryptogram data received.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Manually keyed entry.**<br>- `2` - **Card swiped. Track 1 received.**<br>- `3` - **Card swiped. Track 2 received.**<br>- `4` - **Card swiped. Track 1 & 2 received.**<br>- `5` - **Card dipped. EMV chip received.**<br>- `6` - **Contactless card read. Track or EMV data received.**<br>- `7` - **Track Data from Card Swipe after EMV chip failure.**<br>- `8` - **Track Data from Manually keyed entry after EMV chip failure.**<br>- `9` - **ApplePay**<br>- `10` - **Google Pay.**<br>- `11` - **Merchant created transaction.**<br>- `12` - **Invoice payment.**<br>- `13` - **Merchant created transaction in payrix portal.**<br>- `14` - **Invoice payment from payrix portal.**<br></details><br> | getEntryMode(): ?int | setEntryMode(?int entryMode): void |
| `fee` | `?float` | Optional | Optional calculated fee amount indicator. This should be used in conjunction with txnFee setting on Fees resource. This field is specified in cents(up to three decimal points). | getFee(): ?float | setFee(?float fee): void |
| `first` | `?string` | Optional | The first name associated with this Transaction. For eCheck transactions, either first or last is required. | getFirst(): ?string | setFirst(?string first): void |
| `last` | `?string` | Optional | The last name associated with this Transaction. For eCheck transactions, either first or last is required. | getLast(): ?string | setLast(?string last): void |
| `merchant` | `string` | Required | The identifier of the Merchant associated with this Transaction. | getMerchant(): string | setMerchant(string merchant): void |
| `mid` | `string` | Required | The Merchant ID as set by the processor. This field is stored as a text string and must be between 0 and 50 characters long. | getMid(): string | setMid(string mid): void |
| `middle` | `?string` | Optional | The middle name associated with this Transaction. | getMiddle(): ?string | setMiddle(?string middle): void |
| `order` | `?string` | Optional | The identifier of the Order associated with this Transaction. This field is stored as a text string and must be between 0 and 1000 characters long. | getOrder(): ?string | setOrder(?string order): void |
| `pin` | [`int(TerminalTxnsPinEnum)`](../../doc/models/terminal-txns-pin-enum.md) | Required | Whether this Transaction was verified with a PIN.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **No PIN verification.**<br>- `1` - **PIN verification.**<br><br></details><br> | getPin(): int | setPin(int pin): void |
| `reserved` | `int` | Required, Constant | Indicates whether the Transaction is reserved and the action that will be taken as a result.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **No reserve.**<br></details><br>**Value**: `0`<br> | getReserved(): int | setReserved(int reserved): void |
| `shipping` | `?int` | Optional | The shipping fee pertaining to this transaction. | getShipping(): ?int | setShipping(?int shipping): void |
| `signature` | [`int(TerminalTxnsSignatureEnum)`](../../doc/models/terminal-txns-signature-enum.md) | Required | Whether a signature should be captured during this Transaction.<br><br>* You can set this field if you want the terminal to take a signature for the Transaction.<br>* The API also sets this field automatically if you associate a signature to the Transaction by creating a 'terminalTxnDatas' resource.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not captured.**<br>- `1` - **Captured.**<br></details><br> | getSignature(): int | setSignature(int signature): void |
| `tax` | `?int` | Optional | The amount of the total sum of this Transaction that is made up of tax. This field is specified as an integer in cents. | getTax(): ?int | setTax(?int tax): void |
| `terminal` | `?string` | Optional | The identifier of the terminal that processed this Transaction. The identifier is taken from the terminal system and varies in format according to the type of terminal. This field is stored as a text string and must be between 0 and 50 characters long. | getTerminal(): ?string | setTerminal(?string terminal): void |
| `terminalCapability` | [`?int(TerminalTxnsTerminalCapabilityEnum)`](../../doc/models/terminal-txns-terminal-capability-enum.md) | Optional | Capabilities of the terminal device.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Key entry only terminal.**<br>- `2` - **Can read magnetic stripe.**<br>- `3` - **Integrated circuit reader.**<br>- `4` - **Can detect contactless payment.**<br></details><br> | getTerminalCapability(): ?int | setTerminalCapability(?int terminalCapability): void |
| `total` | `int` | Required | The total amount of this Transaction. This field is specified as an integer in cents. | getTotal(): int | setTotal(int total): void |
| `unattended` | [`?int(TerminalTxnsUnattendedEnum)`](../../doc/models/terminal-txns-unattended-enum.md) | Optional | Whether the card was swiped at an unattended terminal during this Transaction.<br>This field is set to '0' by default.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Attended terminal.**<br>- `1` - **Unattended terminal.**<br></details><br> | getUnattended(): ?int | setUnattended(?int unattended): void |
| `status` | [`int(TerminalTxnStatusEnum)`](../../doc/models/terminal-txn-status-enum.md) | Required | The status of the Transaction.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Pending.**<br>- `1` - **Approved.** Payments can be voided or cancelled.<br>- `2` - **Failed.**<br>- `3` - **Captured.** Payments can be refunded.<br>- `4` - **Settled.** Payments can be refunded.<br>- `5` - **Returned.** Payments have been successfully refunded.<br></details><br>**Default**: `TerminalTxnStatusEnum::PENDING`<br> | getStatus(): int | setStatus(int status): void |
| `address1` | `?string` | Optional | The first line of the address associated with this Transaction. This field is stored as a text string and must be between 1 and 500 characters long. | getAddress1(): ?string | setAddress1(?string address1): void |
| `address2` | `?string` | Optional | The second line of the address associated with this Transaction. This field is stored as a text string and must be between 1 and 500 characters long. | getAddress2(): ?string | setAddress2(?string address2): void |
| `city` | `?string` | Optional | The name of the city in the address associated with this Transaction. This field is stored as a text string and must be between 1 and 500 characters long. | getCity(): ?string | setCity(?string city): void |
| `state` | `?string` | Optional | The U.S. state or Canadian province relevant to the address provided here. If the location is within the U.S. and Canada, specify the 2-character postal abbreviation for the state. If the location is outside of the U.S. and Canada, provide the full state name. This field is stored as a text string and must be between 2 and 100 characters long.<br><br><details><br><summary>U.S. States</summary><br> <br> - `AK` - **Alaska (US)**<br> <br> - `AR` - **Arkansas (US)**<br> <br> - `AL` - **Alabama (US)**<br> <br> - `AZ` - **Arizona (US)**<br> <br> - `CA` - **California (US)**<br> <br> - `CO` - **Colorado (US)**<br> <br> - `CT` - **Connecticut (US)**<br> <br> - `DE` - **Delaware (US)**<br> <br> - `FL` - **Florida (US)**<br> <br> - `GA` - **Georgia (US)**<br> <br> - `HI` - **Hawaii (US)**<br> <br> - `IA` - **Iowa (US)**<br> <br> - `ID` - **Idaho (US)**<br> <br> - `IL` - **Illinois (US)**<br> <br> - `IN` - **Indiana (US)**<br> <br> - `KY` - **Kentucky (US)**<br> <br> - `KS` - **Kansas (US)**<br> <br> - `LA` - **Louisiana (US)**<br> <br> - `MA` - **Massachusetts (US)**<br> <br> - `MD` - **Maryland (US)**<br> <br> - `ME` - **Maine (US)**<br> <br> - `MI` - **Michigan (US)**<br> <br> - `MN` - **Minnesota (US)**<br> <br> - `MO` - **Missouri (US)**<br> <br> - `MS` - **Mississippi (US)**<br> <br> - `MT` - **Montana (US)**<br> <br> - `NC` - **North Carolina (US)**<br> <br> - `ND` - **North Dakota (US)**<br> <br> - `NE` - **Nebraska (US)**<br> <br> - `NH` - **New Hampshire (US)**<br> <br> - `NJ` - **New Jersey (US)**<br> <br> - `NM` - **New Mexico (US)**<br> <br> - `NV` - **Nevada (US)**<br> <br> - `NY` - **New York (US)**<br> <br> - `OH` - **Ohio (US)**<br> <br> - `OK`- **Oklahoma (US)**<br> <br> - `OR` - **Oregon (US)**<br> <br> - `PA` - **Pennsylvania (US)**<br> <br> - `RI` - **Rhode Island (US)**<br> <br> - `SC`- **South Carolina (US)**<br> <br> - `SD` - **South Dakota (US)**<br> <br> - `TN` - **Tennessee (US)**<br> <br> - `TX` - **Texas (US)**<br> <br> - `UT` - **Utah (US)**<br> <br> - `VA` - **Virginia (US)**<br> <br> - `VT` - **Vermont (US)**<br> <br> - `WA` - **Washington (US)**<br> <br> - `WI` - **Wisconsin (US)**<br> <br> - `WV` - **West Virginia (US)**<br> <br> - `WY` - **Wyoming (US)**<br> </details><br> <details><br><summary>Canada Provinces and Territories</summary><br> <br> - `AB` - **Alberta (CAN)**<br> <br> - `BC` - **British Columbia (CAN)**<br> <br> - `MB` - **Manitoba (CAN)**<br> <br> - `ON` - **Ontario (CAN)**<br> <br> - `NS` - **Nova Scotia (CAN)**<br> <br> - `NB` - **New Brunswick (CAN)**<br> <br> - `NL` - **Newfoundland and Labrador (CAN)**<br> <br> - `NT` - **Northwest Territories (CAN)**<br> <br> - `NU` - **Nunavut (CAN)**<br> <br> - `PE` - **Prince Edward Island (CAN)**<br> <br> - `QC` - **Quebec (CAN)**<br> <br> - `SK` - **Saskatchewan (CAN)**<br> <br> - `YT` - **Yukon (CAN)**<br> </details><br> | getState(): ?string | setState(?string state): void |
| `zip` | `?string` | Optional | The ZIP code in the address associated with this Transaction. This field is stored as a text string and must be between 1 and 20 characters long. | getZip(): ?string | setZip(?string zip): void |
| `country` | [`?string(CountryEnum)`](../../doc/models/country-enum.md) | Optional | The country associated with this transaction, valid values for this field are the 3-letter ISO code for the country. | getCountry(): ?string | setCountry(?string country): void |
| `phone` | `?string` | Optional | The phone number associated with this Transaction. This field is stored as a text string and must be between 10 and 15 characters long. | getPhone(): ?string | setPhone(?string phone): void |
| `inactive` | [`int(InactiveEnum)`](../../doc/models/inactive-enum.md) | Required | Whether this resource is marked as inactive.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Active**<br>- `1` - **Inactive**<br></details><br>**Default**: `InactiveEnum::ACTIVE`<br> | getInactive(): int | setInactive(int inactive): void |
| `frozen` | [`int(FrozenEnum)`](../../doc/models/frozen-enum.md) | Required | Whether this resource is marked as frozen.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Frozen**<br>- `1` - **Frozen**<br></details><br>**Default**: `FrozenEnum::NOTFROZEN`<br> | getFrozen(): int | setFrozen(int frozen): void |
| `terminalTxnData` | [`?TerminalTxnsDatasPostRequest`](../../doc/models/terminal-txns-datas-post-request.md) | Optional | - | getTerminalTxnData(): ?TerminalTxnsDatasPostRequest | setTerminalTxnData(?TerminalTxnsDatasPostRequest terminalTxnData): void |
| `notes` | [`?(NotesPostRequest[])`](../../doc/models/notes-post-request.md) | Optional | - | getNotes(): ?array | setNotes(?array notes): void |
| `terminalTxnMetadatas` | [`?(TerminalTxnsMetadatasPostRequest[])`](../../doc/models/terminal-txns-metadatas-post-request.md) | Optional | - | getTerminalTxnMetadatas(): ?array | setTerminalTxnMetadatas(?array terminalTxnMetadatas): void |
| `terminalTxnRefs` | [`?(TerminalTxnRefPostRequest[])`](../../doc/models/terminal-txn-ref-post-request.md) | Optional | - | getTerminalTxnRefs(): ?array | setTerminalTxnRefs(?array terminalTxnRefs): void |
| `terminalTxnResults` | [`?(TerminalTxnResultsPostRequest[])`](../../doc/models/terminal-txn-results-post-request.md) | Optional | - | getTerminalTxnResults(): ?array | setTerminalTxnResults(?array terminalTxnResults): void |

## Example (as JSON)

```json
{
  "binType": "DEBIT",
  "expiration": "1023",
  "forterminalTxn": "forterminalTxn",
  "origin": 1,
  "platform": "VCORE",
  "pos": 0,
  "receipt": "noReceipt",
  "tid": "Terminal ID",
  "traceNumber": 853202,
  "txn": "related txn",
  "token": "124f2d0efab0bcda46f2118d688bbf97",
  "paymentNumber": 7,
  "paymentMethod": 2,
  "type": 1,
  "tip": 0,
  "originatingApp": "originatingApp",
  "OEMTTxnRefNumber": "TxnRefNumber",
  "posApplicationId": "15668",
  "posApplicationName": "XML Test Example",
  "posApplicationVersion": "1.00",
  "customerReferenceNumber": "123456",
  "gatewayTransactionId": "486689252",
  "customerTicketNumber": "123456",
  "authCode": "authorization code",
  "authDate": 20160120,
  "cashback": 0,
  "clientIp": "Client IP address",
  "company": "company1",
  "currency": "USD",
  "fundingCurrency": "USD",
  "cvvStatus": "notPresent",
  "description": "description1",
  "discount": 0,
  "duty": 0,
  "email": "john.johnson@example.com",
  "swiped": 1,
  "entryMode": 1,
  "fee": 0,
  "first": "John",
  "last": "Doe",
  "merchant": "t1_mer_64415e89a919c1566a2b49b",
  "mid": "4445061378323",
  "middle": "M",
  "order": "orderId",
  "pin": 0,
  "reserved": 0,
  "shipping": 0,
  "signature": 0,
  "tax": 0,
  "terminal": "identifier of terminal",
  "terminalCapability": 1,
  "total": 8000,
  "unattended": 0,
  "status": 1,
  "address1": "address1",
  "address2": "address2",
  "city": "city1",
  "state": "AB",
  "zip": "ZIP code",
  "country": "CAN",
  "phone": "9999888888",
  "inactive": 0,
  "frozen": 0
}
```

