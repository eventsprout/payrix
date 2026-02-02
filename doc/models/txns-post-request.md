
# Txns Post Request

## Structure

`TxnsPostRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `allowPartial` | [`int(TxnsAllowPartialEnum)`](../../doc/models/txns-allow-partial-enum.md) | Required | Whether to allow partial amount authorizations of this Transaction. For example, if the transaction amount is $1000 and the processor only authorizes a smaller amount, then enabling this field lets the Transaction proceed anyway.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Partial amount authorizations are not allowed.**<br>- `1` - **Partial amount authorizations are allowed.**<br><br></details><br> | getAllowPartial(): int | setAllowPartial(int allowPartial): void |
| `batch` | `?string` | Optional | If the Transaction is linked to a Batch, this field specifies the identifier of the Batch. | getBatch(): ?string | setBatch(?string batch): void |
| `authentication` | `string` | Required | Authentication token returned by the network in a 3DSecure txn. | getAuthentication(): string | setAuthentication(string authentication): void |
| `authenticationId` | `?string` | Optional | Optional transaction ID returned by the network in a 3DSecure txn. | getAuthenticationId(): ?string | setAuthenticationId(?string authenticationId): void |
| `cofType` | [`?string(TxnsCofTypeEnum)`](../../doc/models/txns-cof-type-enum.md) | Optional | The type of Card On File transaction when using a token is single, scheduled, or unscheduled.<br><br><details><br><summary>Valid Values</summary><br>- `single`  - **Individual Transaction.**<br>- `scheduled`  - **Scheduled Transaction.**<br>- `unscheduled`  - **Unscheduled sequential Transaction.**<br>- `installment`  - **Installment Transaction.**<br></details><br> | getCofType(): ?string | setCofType(?string cofType): void |
| `currencyConversion` | [`?string(CurrencyConversionEnum)`](../../doc/models/currency-conversion-enum.md) | Optional | The status of the currency conversion.<br><br><details><br><summary>Valid Values</summary><br>- `customerAccepted` - **The customer accepted the currency conversion rate.**<br>- `customerRejected` - **The customer rejected the currency conversion rate.**<br>- `notEligible` - **This transaction is not eligible for currency conversion.**<br></details><br> | getCurrencyConversion(): ?string | setCurrencyConversion(?string currencyConversion): void |
| `debtRepayment` | [`int(TxnsDebtRepaymentEnum)`](../../doc/models/txns-debt-repayment-enum.md) | Required | If this transaction is for debt repayment or not for debt repayment.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Transaction not for debt repayment.**<br>- `1` - **Transaction for debt repayment.**<br><br></details><br>**Default**: `TxnsDebtRepaymentEnum::OFF`<br> | getDebtRepayment(): int | setDebtRepayment(int debtRepayment): void |
| `expiration` | `?string` | Optional | The expiration date of this Transaction.<br>This field is stored as a text string in 'MMYY' format, where 'MM' is the number of a month and 'YY' is the last two digits of a year. For example, '0623' for June 2023.<br>The value must reflect a future date. | getExpiration(): ?string | setExpiration(?string expiration): void |
| `fortxn` | `string` | Required | If this Transaction is related to another Transaction, then this field is set to the identifier of the other Transaction.<br>For example, if this Transaction is a refund, this field could be set to the identifier of the original sale Transaction. | getFortxn(): string | setFortxn(string fortxn): void |
| `fromtxn` | `?string` | Optional | Reauthorize this referenced Transaction. For example, to process a resubmission of a declined Transaction or to reauthorize an expired Transaction. | getFromtxn(): ?string | setFromtxn(?string fromtxn): void |
| `copyReason` | [`?string(TxnsCopyReasonsEnum)`](../../doc/models/txns-copy-reasons-enum.md) | Optional | Reason for copying Transaction referenced in fromtxn field, which<br>can be either resubmission or reauthorization.<br><br><details><br><summary>Valid Values</summary><br>- `resubmission` - **Resubmission.**<br>- `reauthorization` - **Reauthorization.**<br></details><br> | getCopyReason(): ?string | setCopyReason(?string copyReason): void |
| `mobile` | [`?int(TxnsMobileEnum)`](../../doc/models/txns-mobile-enum.md) | Optional | Indicates if a transaction is being processed through a Mobile POS.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Non-mobile POS.**<br>- `1` - **Mobile POS.**<br><br></details><br> | getMobile(): ?int | setMobile(?int mobile): void |
| `origin` | [`int(TxnOriginEnum)`](../../doc/models/txn-origin-enum.md) | Required | The origin of the transaction.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Unknown.**<br>- `1` - **Originated at a credit card terminal.**<br><br>- `2` - **Originated through an eCommerce system.**<br><br>- `3` - **Originated as a mail order or telephone order transaction.**<br><br>- `4` - **Originated with Apple Pay.**<br><br>- `5` - **Originated as a Successful 3D Secure transaction.**<br><br>- `6` - **Originated as an Attempted 3D Secure transaction.**<br><br>- `7` - **Deprecated. Originated as a recurring transaction on a card.**<br><br>- `8` - **Originated in a PayFrame.**<br><br>- `9` - **Originated in writing.**<br><br></details><br> | getOrigin(): int | setOrigin(int origin): void |
| `pinEntryCapability` | [`?string(TxnsPinEntryCapabilityEnum)`](../../doc/models/txns-pin-entry-capability-enum.md) | Optional | Indicates the PIN entry capability of the device, which can be unknown, capable, notCapable, or pinPadDown.<br><br><details><br><summary>Valid Values</summary><br>- `unknown` - **Unknown PIN Entry Capability.**<br>- `capable` - **Terminal can accept PINs.**<br>- `notCapable` - **Terminal cannot accept entry of PINs.**<br>- `pinPadDown` - **Terminal PIN Pad is down.**<br></details><br> | getPinEntryCapability(): ?string | setPinEntryCapability(?string pinEntryCapability): void |
| `platform` | [`?string(TxnsPlatformEnum)`](../../doc/models/txns-platform-enum.md) | Optional | The platform used to process transactions.<br><br><details><br><summary>Valid Values</summary><br>- `APPLE` - **The Apple Payment Processor (Deprecated).**<br>- `ELAVON` - **The Elavon processor (Deprecated).**<br>- `FIRSTDATA` - **The FirstData processor (Deprecated).**<br>- `GOOGLE` - **The Google Payment Processor (Deprecated).**<br>- `VANTIV` - **The WorldPay (aka Vantiv or Litle) eComm (aka VAP) processor.**<br>- `VCORE` - **The WorldPay (aka Vantiv) Core processor.**<br>- `WELLSACH` - **The Wells Fargo ACH processor.**<br>- `WELLSFARGO` - **The Wells Fargo Merchant Services processor (Deprecated).**<br>- `WFSINGLE` - **The WFSINGLE processor (Deprecated).**<br></details><br> | getPlatform(): ?string | setPlatform(?string platform): void |
| `processedSequence` | `?int` | Optional | For entry creation and deletion job sequencing: the current processed sequence number for this transaction.<br><br>**Default**: `0` | getProcessedSequence(): ?int | setProcessedSequence(?int processedSequence): void |
| `funded` | `?int` | Optional | A date indicating when this Transaction was funded.<br>This field is set automatically. | getFunded(): ?int | setFunded(?int funded): void |
| `returned` | `?string` | Optional | The transaction has been returned by the receiver. | getReturned(): ?string | setReturned(?string returned): void |
| `fundingEnabled` | [`?int(TxnsFundingEnabledEnum)`](../../doc/models/txns-funding-enabled-enum.md) | Optional | Whether or not funding is enabled for this Transaction.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Disabled.**<br>- `1` - **Enabled.**<br><br></details><br> | getFundingEnabled(): ?int | setFundingEnabled(?int fundingEnabled): void |
| `fbo` | `?string` | Optional | FBO (for benefit of) in which each entry origin belongs to. | getFbo(): ?string | setFbo(?string fbo): void |
| `requestSequence` | `?int` | Optional | For entry creation and deletion job sequencing: the current processed sequence number for this transaction.<br><br>**Default**: `0` | getRequestSequence(): ?int | setRequestSequence(?int requestSequence): void |
| `statement` | `?string` | Optional | The statement ID for which this transaction is being processed as payment. | getStatement(): ?string | setStatement(?string statement): void |
| `token` | `?string` | Optional | The token of the Tokens resource this Transaction is associated with. | getToken(): ?string | setToken(?string token): void |
| `type` | [`int(TxnTypeEnum)`](../../doc/models/txn-type-enum.md) | Required | The type of Transaction.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Credit Card Only: Sale Transaction.** Processes a sale and charges the customer.<br>- `2` - **Credit Card Only: Auth Transaction.** Authorizes and holds the requested total on the credit card.<br>- `3` - **Credit Card Only: Capture Transaction.** Finalizes a prior Auth Transaction and charges the customer.<br>- `4` - **Credit Card Only: Reverse Authorization.** Reverses a prior Auth or Sale Transaction and releases the credit hold.<br>- `5` - **Credit Card Only: Refund Transaction.** Refunds a prior Capture or Sale Transaction (total may be specified for a partial refund).<br>- `7` - **Echeck Only: Echeck Sale Transaction.** Sale Transaction for ECheck payment.<br>- `8` - **Echeck Only: Echeck Refund Transaction.** Refund Transaction for prior ECheck Sale Transaction.<br>- `11` - **Echeck Only: Echeck Redeposit Transaction.** Attempt to redeposit a prior failed eCheck Sale Transaction.<br>- `12` - **Echeck Only: Echeck Account Verification Transaction.** Attempt to verify eCheck payment details.<br>- `14` - **Incremental Authorization.**<br></details><br> | getType(): int | setType(int type): void |
| `unauthReason` | [`string(UnauthReasonEnum)`](../../doc/models/unauth-reason-enum.md) | Required | The reason for the auth reversal.<br>This field is set to 'customerCancelled' by default.<br><br><details><br><summary>Valid Values</summary><br>- `incomplete` - **Transaction Incomplete.**<br>- `timeout` - **Transaction Timeout.**<br><br>- `clerkCancelled` - **Transaction Cancelled by Clerk.**<br><br>- `customerCancelled` - **Transaction Cancelled by Customer.**<br><br>- `misdispense` - **Misdispense.**<br><br>- `hardwareFailure` - **Hardware Failure.**<br><br>- `suspectedFraud` - **Suspected Fraud.**<br><br></details><br> | getUnauthReason(): string | setUnauthReason(string unauthReason): void |
| `authTokenCustomer` | `?string` | Optional | The customer identifier from the AuthToken used during authentication. | getAuthTokenCustomer(): ?string | setAuthTokenCustomer(?string authTokenCustomer): void |
| `channel` | `?string` | Optional | This field is stored as a text string and must be between 0 and 1000 characters long. | getChannel(): ?string | setChannel(?string channel): void |
| `cashback` | `?int` | Optional | The amount of the total sum of this Transaction that is given as cash back.<br>This field is specified as an integer in cents. | getCashback(): ?int | setCashback(?int cashback): void |
| `clientIp` | `?string` | Optional | The client ip address from which the Transaction was created.<br>Valid values are any Ipv4 or Ipv6 address. | getClientIp(): ?string | setClientIp(?string clientIp): void |
| `company` | `?string` | Optional | The name of the company associated with this Transaction.<br>Setting this field is especially important when processing an eCheck from a company. | getCompany(): ?string | setCompany(?string company): void |
| `currency` | [`?string(CurrencyEnum)`](../../doc/models/currency-enum.md) | Required | The currency for this transaction. See <a href="https://www.iban.com/currency-codes" target="_blank">Currency codes</a>  for all valid values.<br><br>**Default**: `CurrencyEnum::USD` | getCurrency(): ?string | setCurrency(?string currency): void |
| `fundingCurrency` | [`?string(CurrencyEnum)`](../../doc/models/currency-enum.md) | Required | The currency for which transaction was funded on. See <a href="https://www.iban.com/currency-codes" target="_blank">Currency codes</a>  for all valid values.<br><br>**Default**: `CurrencyEnum::USD` | getFundingCurrency(): ?string | setFundingCurrency(?string fundingCurrency): void |
| `cvvStatus` | [`?string(TerminalTxnsCvvStatusEnum)`](../../doc/models/terminal-txns-cvv-status-enum.md) | Optional | The status of the CVV on the card.<br><br><details><br><summary>Valid Values</summary><br>- `notPresent` - **CVV is not present.**<br>- `illegible` - **CVV is illegible.**<br>- `notProvided` - **CVV was not provided.**<br></details><br> | getCvvStatus(): ?string | setCvvStatus(?string cvvStatus): void |
| `description` | `?string` | Optional | A description of this Transaction.<br>This field is stored as a text string and must be between 0 and 1000 characters long. | getDescription(): ?string | setDescription(?string description): void |
| `discount` | `?int` | Optional | The customer discount, in cents, already applied to the total for this transaction. | getDiscount(): ?int | setDiscount(?int discount): void |
| `duty` | `?int` | Optional | The amount of the total, in cents, that represents the duties charged to the customer | getDuty(): ?int | setDuty(?int duty): void |
| `email` | `?string` | Optional | The email associated with this Transaction. | getEmail(): ?string | setEmail(?string email): void |
| `swiped` | [`int(TerminalTxnsSwipedEnum)`](../../doc/models/terminal-txns-swiped-enum.md) | Required | Whether the card was swiped during this Transaction.<br>This field is set to '1' automatically if 'track' data was received.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not Swiped.**<br>- `1` - **Swiped.**<br></details><br> | getSwiped(): int | setSwiped(int swiped): void |
| `entryMode` | [`?int(EntryModeEnum)`](../../doc/models/entry-mode-enum.md) | Optional | How payment information has been entered, including manually keyed entries, card swipes with track 1 or 2 data received, card dips with EMV chip data received, contactless card reads with track or EMV data received, and ApplePay read with cryptogram data received.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Manually keyed entry.**<br>- `2` - **Card swiped. Track 1 received.**<br>- `3` - **Card swiped. Track 2 received.**<br>- `4` - **Card swiped. Track 1 & 2 received.**<br>- `5` - **Card dipped. EMV chip received.**<br>- `6` - **Contactless card read. Track or EMV data received.**<br>- `7` - **Track Data from Card Swipe after EMV chip failure.**<br>- `8` - **Track Data from Manually keyed entry after EMV chip failure.**<br>- `9` - **ApplePay**<br>- `10` - **Google Pay.**<br>- `11` - **Merchant created transaction.**<br>- `12` - **Invoice payment.**<br>- `13` - **Merchant created transaction in payrix portal.**<br>- `14` - **Invoice payment from payrix portal.**<br></details><br> | getEntryMode(): ?int | setEntryMode(?int entryMode): void |
| `fee` | `?float` | Optional | Optional calculated fee amount indicator. This should be used in conjunction with txnFee setting on Fees resource,<br>This field is specified in cents(up to three decimal points) | getFee(): ?float | setFee(?float fee): void |
| `first` | `?string` | Optional | The first name associated with this Transaction. For eCheck transactions, either first or last is required. | getFirst(): ?string | setFirst(?string first): void |
| `last` | `?string` | Optional | The last name associated with this Transaction. For eCheck transactions, either first or last is required. | getLast(): ?string | setLast(?string last): void |
| `merchant` | `string` | Required | The identifier of the Merchant associated with this Transaction. | getMerchant(): string | setMerchant(string merchant): void |
| `mid` | `string` | Required | The Merchant ID as set by the processor.<br>This field is stored as a text string and must be between 0 and 50 characters long. | getMid(): string | setMid(string mid): void |
| `middle` | `?string` | Optional | The middle name associated with this Transaction. | getMiddle(): ?string | setMiddle(?string middle): void |
| `order` | `?string` | Optional | The identifier of the Order associated with this Transaction.<br>This field is stored as a text string and must be between 0 and 1000 characters long. | getOrder(): ?string | setOrder(?string order): void |
| `pin` | [`int(TerminalTxnsPinEnum)`](../../doc/models/terminal-txns-pin-enum.md) | Required | Whether this Transaction was verified with a PIN.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **No PIN verification.**<br>- `1` - **PIN verification.**<br><br></details><br> | getPin(): int | setPin(int pin): void |
| `shipping` | `?int` | Optional | The amount of the total, in cents, that represents the shipping cost charged to the customer | getShipping(): ?int | setShipping(?int shipping): void |
| `signature` | [`int(TerminalTxnsSignatureEnum)`](../../doc/models/terminal-txns-signature-enum.md) | Required | Whether a signature should be captured during this Transaction.<br><br>* You can set this field if you want the terminal to take a signature for the Transaction.<br>* The API also sets this field automatically if you associate a signature to the Transaction by creating a 'terminalTxnDatas' resource.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Not captured.**<br>- `1` - **Captured.**<br></details><br> | getSignature(): int | setSignature(int signature): void |
| `tax` | `?int` | Optional | The amount of the total sum of this Transaction that is made up of tax.<br>This field is specified as an integer in cents. | getTax(): ?int | setTax(?int tax): void |
| `surcharge` | `?int` | Optional | The amount of the total sum of this Transaction that is made up of surcharge.<br>This field is specified as an integer in cents. | getSurcharge(): ?int | setSurcharge(?int surcharge): void |
| `terminal` | `?string` | Optional | The identifier of the terminal that processed this Transaction.<br>The identifier is taken from the terminal system and varies in format according to the type of terminal.<br>This field is stored as a text string and must be between 0 and 50 characters long. | getTerminal(): ?string | setTerminal(?string terminal): void |
| `terminalCapability` | [`?int(TerminalTxnsTerminalCapabilityEnum)`](../../doc/models/terminal-txns-terminal-capability-enum.md) | Optional | Capabilities of the terminal device.<br><br><details><br><summary>Valid Values</summary><br>- `1` - **Key entry only terminal.**<br>- `2` - **Can read magnetic stripe.**<br>- `3` - **Integrated circuit reader.**<br>- `4` - **Can detect contactless payment.**<br></details><br> | getTerminalCapability(): ?int | setTerminalCapability(?int terminalCapability): void |
| `total` | `int` | Required | The total amount of this Transaction.<br>This field is specified as an integer in cents.For example, $10.15 would be entered as 1015. | getTotal(): int | setTotal(int total): void |
| `unattended` | [`int(TerminalTxnsUnattendedEnum)`](../../doc/models/terminal-txns-unattended-enum.md) | Required | Whether the card was swiped at an unattended terminal during this Transaction.<br>This field is set to '0' by default.<br><br><details><br><summary>Valid Values</summary><br>- `0` - **Attended terminal.**<br>- `1` - **Unattended terminal.**<br></details><br> | getUnattended(): int | setUnattended(int unattended): void |
| `address1` | `?string` | Optional | The first line of the address associated with this Transaction.<br>This field is stored as a text string and must be between 1 and 500 characters long. | getAddress1(): ?string | setAddress1(?string address1): void |
| `address2` | `?string` | Optional | The second line of the address associated with this Transaction.<br>This field is stored as a text string and must be between 1 and 500 characters long. | getAddress2(): ?string | setAddress2(?string address2): void |
| `city` | `?string` | Optional | The name of the city in the address associated with this Transaction.<br>This field is stored as a text string and must be between 1 and 500 characters long. | getCity(): ?string | setCity(?string city): void |
| `state` | `?string` | Optional | The U.S. state or Canadian province relevant to the address provided here. If the location is within the U.S. and Canada, specify the 2-character postal abbreviation for the state. If the location is outside of the U.S. and Canada, provide the full state name. This field is stored as a text string and must be between 2 and 100 characters long.<br><br><details><br><summary>U.S. States</summary><br> <br> - `AK` - **Alaska (US)**<br> <br> - `AR` - **Arkansas (US)**<br> <br> - `AL` - **Alabama (US)**<br> <br> - `AZ` - **Arizona (US)**<br> <br> - `CA` - **California (US)**<br> <br> - `CO` - **Colorado (US)**<br> <br> - `CT` - **Connecticut (US)**<br> <br> - `DE` - **Delaware (US)**<br> <br> - `FL` - **Florida (US)**<br> <br> - `GA` - **Georgia (US)**<br> <br> - `HI` - **Hawaii (US)**<br> <br> - `IA` - **Iowa (US)**<br> <br> - `ID` - **Idaho (US)**<br> <br> - `IL` - **Illinois (US)**<br> <br> - `IN` - **Indiana (US)**<br> <br> - `KY` - **Kentucky (US)**<br> <br> - `KS` - **Kansas (US)**<br> <br> - `LA` - **Louisiana (US)**<br> <br> - `MA` - **Massachusetts (US)**<br> <br> - `MD` - **Maryland (US)**<br> <br> - `ME` - **Maine (US)**<br> <br> - `MI` - **Michigan (US)**<br> <br> - `MN` - **Minnesota (US)**<br> <br> - `MO` - **Missouri (US)**<br> <br> - `MS` - **Mississippi (US)**<br> <br> - `MT` - **Montana (US)**<br> <br> - `NC` - **North Carolina (US)**<br> <br> - `ND` - **North Dakota (US)**<br> <br> - `NE` - **Nebraska (US)**<br> <br> - `NH` - **New Hampshire (US)**<br> <br> - `NJ` - **New Jersey (US)**<br> <br> - `NM` - **New Mexico (US)**<br> <br> - `NV` - **Nevada (US)**<br> <br> - `NY` - **New York (US)**<br> <br> - `OH` - **Ohio (US)**<br> <br> - `OK`- **Oklahoma (US)**<br> <br> - `OR` - **Oregon (US)**<br> <br> - `PA` - **Pennsylvania (US)**<br> <br> - `RI` - **Rhode Island (US)**<br> <br> - `SC`- **South Carolina (US)**<br> <br> - `SD` - **South Dakota (US)**<br> <br> - `TN` - **Tennessee (US)**<br> <br> - `TX` - **Texas (US)**<br> <br> - `UT` - **Utah (US)**<br> <br> - `VA` - **Virginia (US)**<br> <br> - `VT` - **Vermont (US)**<br> <br> - `WA` - **Washington (US)**<br> <br> - `WI` - **Wisconsin (US)**<br> <br> - `WV` - **West Virginia (US)**<br> <br> - `WY` - **Wyoming (US)**<br> </details><br> <details><br><summary>Canada Provinces and Territories</summary><br> <br> - `AB` - **Alberta (CAN)**<br> <br> - `BC` - **British Columbia (CAN)**<br> <br> - `MB` - **Manitoba (CAN)**<br> <br> - `ON` - **Ontario (CAN)**<br> <br> - `NS` - **Nova Scotia (CAN)**<br> <br> - `NB` - **New Brunswick (CAN)**<br> <br> - `NL` - **Newfoundland and Labrador (CAN)**<br> <br> - `NT` - **Northwest Territories (CAN)**<br> <br> - `NU` - **Nunavut (CAN)**<br> <br> - `PE` - **Prince Edward Island (CAN)**<br> <br> - `QC` - **Quebec (CAN)**<br> <br> - `SK` - **Saskatchewan (CAN)**<br> <br> - `YT` - **Yukon (CAN)**<br> </details><br> | getState(): ?string | setState(?string state): void |
| `zip` | `?string` | Optional | The ZIP code in the address associated with this Transaction.<br>This field is stored as a text string and must be between 1 and 20 characters long. | getZip(): ?string | setZip(?string zip): void |
| `country` | [`?string(CountryEnum)`](../../doc/models/country-enum.md) | Optional | The country associated with this transaction, valid values for this field are the 3-letter ISO code for the country. | getCountry(): ?string | setCountry(?string country): void |
| `phone` | `?string` | Optional | The phone number associated with this Transaction.<br>This field is stored as a text string and must be between 10 and 15 characters long. | getPhone(): ?string | setPhone(?string phone): void |
| `tmxSessionId` | `?string` | Optional | Threatmetrix session ID, used to trace the financial session and prevent possible frauds. | getTmxSessionId(): ?string | setTmxSessionId(?string tmxSessionId): void |
| `firstTxn` | `?string` | Optional | For external recurring systems, this is the first transaction ID related to this recurring payment. | getFirstTxn(): ?string | setFirstTxn(?string firstTxn): void |
| `payment` | [`TxnsPayment`](../../doc/models/txns-payment.md) | Required | The payment method associated with this Transaction, including the card details. | getPayment(): TxnsPayment | setPayment(TxnsPayment payment): void |

## Example (as JSON)

```json
{
  "allowPartial": 1,
  "batch": "t1_bth_67b6129bcca1cbb7cdac000",
  "authentication": "Authentication Token",
  "authenticationId": "Optional transaction ID",
  "cofType": "single",
  "currencyConversion": "customerAccepted",
  "debtRepayment": 1,
  "expiration": "0623",
  "fortxn": "t1_txn_67b5f9801e463c908f453oo",
  "fromtxn": "Reauthorize an expired Transaction",
  "copyReason": "resubmission",
  "mobile": 0,
  "origin": 4,
  "pinEntryCapability": "unknown",
  "platform": "VANTIV",
  "processedSequence": 0,
  "funded": 623,
  "returned": "Returned Transaction",
  "fundingEnabled": 0,
  "fbo": "WORLDPAY_FBO1",
  "requestSequence": 1,
  "statement": "statement ID",
  "token": "31b0ac1d55c898a7b6758ed2209fce00",
  "type": 3,
  "unauthReason": "customerCancelled",
  "authTokenCustomer": "Customer Identifier",
  "channel": "LA",
  "cashback": 0,
  "clientIp": "216.80.4.000",
  "company": "Hotdog Water",
  "currency": "DOP",
  "fundingCurrency": "BRL",
  "cvvStatus": "notPresent",
  "description": "Neon Test",
  "discount": 0,
  "duty": 0,
  "email": "robert.johnson@example.com",
  "swiped": 1,
  "entryMode": 1,
  "fee": 997,
  "first": "Robert",
  "middle": "John",
  "last": "Johnson",
  "merchant": "t1_mer_1344e1a5460f5cfdf21ce11",
  "mid": "11003321",
  "order": "identifier",
  "pin": 1,
  "shipping": 0,
  "signature": 1,
  "tax": 0,
  "surcharge": 0,
  "terminal": "Terminal Identifier",
  "terminalCapability": 1,
  "total": 1010,
  "unattended": 1,
  "address1": "708 Kunde Mission",
  "address2": "Apt 3g",
  "city": "New York",
  "state": "NY",
  "zip": "10001",
  "country": "USA",
  "phone": "1111111111",
  "tmxSessionId": "Threatmetrix session ID",
  "firstTxn": "t1_txn_67b6129bcca1cbb7cdac001",
  "payment": {
    "method": 2,
    "number": "1111",
    "routing": "code",
    "cvv": "111",
    "track": {
      "key1": "val1",
      "key2": "val2"
    },
    "expiration": "expiration0"
  }
}
```

