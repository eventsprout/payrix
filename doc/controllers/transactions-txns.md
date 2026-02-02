# Transactions Txns

```php
$transactionsTxnsController = $client->getTransactionsTxnsController();
```

## Class Name

`TransactionsTxnsController`

## Methods

* [Get Txns Id](../../doc/controllers/transactions-txns.md#get-txns-id)
* [Put Txns Id](../../doc/controllers/transactions-txns.md#put-txns-id)
* [Get Txns](../../doc/controllers/transactions-txns.md#get-txns)
* [Post Txns](../../doc/controllers/transactions-txns.md#post-txns)


# Get Txns Id

Query a Transaction.
Transactions hold all of the information relating to a particular credit card transaction, including the merchant, token, subscription, customer and card information.

```php
function getTxnsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): TxnsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this transaction. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`TxnsResponseResult`](../../doc/models/txns-response-result.md)

## Example Usage

```php
$id = 'p1_txn_5a1ef5e55658af7cf012866';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $transactionsTxnsController->getTxnsId(
    $id,
    $token,
    $requestToken
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "p1_txn_5a1ef5e55658af7cf010000",
        "created": "2025-02-20 09:01:14.8325",
        "modified": "2025-02-20 09:01:14.8325",
        "creator": "p1_log_5a1ef5e55653ed720159d00",
        "modifier": "p1_log_5a1ef5e55653ed720159d00",
        "ipCreated": "8.8.8.8",
        "ipModified": "8.8.8.8",
        "merchant": "p1_mer_5a1ef5e55656a739a85da00",
        "token": "e41272ec5464d9ec81cc85c854837400",
        "payment": "g157b215cd94000",
        "fortxn": "t1_txn_67b5f9801e463c908f453oo",
        "fromtxn": "Reauthorize Transaction",
        "batch": "p1_bth_5a1ef5e55655f49b141d313",
        "subscription": "Identifier of Subscription",
        "statement": "Statement ID",
        "type": 1,
        "expiration": "1123",
        "serviceCode": "Code",
        "funded": 1123,
        "returned": "Transaction Returned",
        "currency": "USD",
        "fundingCurrency": "USD",
        "currencyConversion": "customerAccepted",
        "convenienceFee": 0,
        "fee": 342,
        "platform": "VANTIV",
        "authDate": 20160120,
        "authCode": "95834A",
        "captured": "2025-02-19 13:28:42",
        "settled": "2025-02-19 13:28:42",
        "settledCurrency": "USD",
        "settledTotal": 0,
        "allowPartial": 0,
        "order": "00b5f97feb5bc9bcbd9a92fz",
        "description": "$10.00 to Bergstrom and Sons",
        "descriptor": "illinois",
        "traceNumber": 0,
        "discount": 0,
        "shipping": 0,
        "duty": 0,
        "terminal": "Terminal Identifier",
        "terminalCapability": 1,
        "entryMode": 1,
        "origin": 2,
        "mobile": 0,
        "tax": 195,
        "surcharge": 0,
        "total": 20365,
        "cashback": 0,
        "authorization": "52703",
        "originalApproved": 0,
        "approved": 20365,
        "authentication": "Authentication token",
        "authenticationId": "Optional transaction ID",
        "cvv": 0,
        "cvvStatus": "notPresent",
        "swiped": 0,
        "emv": 0,
        "signature": 0,
        "pin": 1,
        "pinEntryCapability": "unknown",
        "unattended": 0,
        "cofType": "single",
        "copyReason": "resubmission",
        "clientIp": "1.1.1.1",
        "first": "Robert",
        "middle": "John",
        "last": "Johnson",
        "company": "Company Name",
        "email": "robert.johnson@example.com",
        "address1": "123 Example St.",
        "address2": "Suite 403",
        "city": "New York",
        "state": "NY",
        "zip": "10001",
        "country": "USA",
        "phone": "1111111111",
        "mid": "01170981",
        "status": 0,
        "refunded": 0,
        "misused": 0,
        "checkStage": "activation",
        "unauthReason": "incomplete",
        "authTokenCustomer": "Customer Identifier",
        "channel": "",
        "imported": 1,
        "requestSequence": 1,
        "processedSequence": 1,
        "debtRepayment": 0,
        "fundingEnabled": 0,
        "fbo": "WORLDPAY_FBO1",
        "txnsession": "t1_tss_67b000bfd6fa9af5775a3dc",
        "reserved": 0,
        "inactive": 1,
        "frozen": 0,
        "tip": 0,
        "softPosId": "POS ID",
        "softPosDeviceTypeIndicator": "Indicator",
        "networkTokenIndicator": 0,
        "pinlessDebitConversion": 0,
        "submittedMethod": 3,
        "processedMethod": 25
      }
    ],
    "details": {
      "requestId": 1,
      "totals": [],
      "page": {
        "current": 1,
        "last": 1,
        "hasMore": false
      }
    },
    "errors": []
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Error | [`ErrorFourHundredException`](../../doc/models/error-four-hundred-exception.md) |


# Put Txns Id

Update a Transaction.
Transactions hold all of the information relating to a particular credit card transaction, including the merchant, token, subscription, customer and card information.

```php
function putTxnsId(
    string $id,
    TxnsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): TxnsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this transaction. |
| `body` | [`TxnsPutRequest`](../../doc/models/txns-put-request.md) | Body, Required | Update txns Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`TxnsResponseResult`](../../doc/models/txns-response-result.md)

## Example Usage

```php
$id = 'p1_txn_5a1ef5e55658af7cf012866';

$body = TxnsPutRequestBuilder::init()->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $transactionsTxnsController->putTxnsId(
    $id,
    $body,
    $token,
    $requestToken
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "p1_txn_5a1ef5e55658af7cf010000",
        "created": "2025-02-20 09:01:14.8325",
        "modified": "2025-02-20 09:01:14.8325",
        "creator": "p1_log_5a1ef5e55653ed720159d00",
        "modifier": "p1_log_5a1ef5e55653ed720159d00",
        "ipCreated": "8.8.8.8",
        "ipModified": "8.8.8.8",
        "merchant": "p1_mer_5a1ef5e55656a739a85da00",
        "token": "e41272ec5464d9ec81cc85c854837400",
        "payment": "g157b215cd94000",
        "fortxn": "t1_txn_67b5f9801e463c908f453oo",
        "fromtxn": "Reauthorize Transaction",
        "batch": "p1_bth_5a1ef5e55655f49b141d313",
        "subscription": "Identifier of Subscription",
        "statement": "Statement ID",
        "type": 1,
        "expiration": "1123",
        "serviceCode": "Code",
        "funded": 1123,
        "returned": "Transaction Returned",
        "currency": "USD",
        "fundingCurrency": "USD",
        "currencyConversion": "customerAccepted",
        "convenienceFee": 0,
        "fee": 342,
        "platform": "VANTIV",
        "authDate": 20160120,
        "authCode": "95834A",
        "captured": "2025-02-19 13:28:42",
        "settled": "2025-02-19 13:28:42",
        "settledCurrency": "USD",
        "settledTotal": 0,
        "allowPartial": 0,
        "order": "00b5f97feb5bc9bcbd9a92fz",
        "description": "$10.00 to Bergstrom and Sons",
        "descriptor": "illinois",
        "traceNumber": 0,
        "discount": 0,
        "shipping": 0,
        "duty": 0,
        "terminal": "Terminal Identifier",
        "terminalCapability": 1,
        "entryMode": 1,
        "origin": 2,
        "mobile": 0,
        "tax": 195,
        "surcharge": 0,
        "total": 20365,
        "cashback": 0,
        "authorization": "52703",
        "originalApproved": 0,
        "approved": 20365,
        "authentication": "Authentication token",
        "authenticationId": "Optional transaction ID",
        "cvv": 0,
        "cvvStatus": "notPresent",
        "swiped": 0,
        "emv": 0,
        "signature": 0,
        "pin": 1,
        "pinEntryCapability": "unknown",
        "unattended": 0,
        "cofType": "single",
        "copyReason": "resubmission",
        "clientIp": "1.1.1.1",
        "first": "Robert",
        "middle": "John",
        "last": "Johnson",
        "company": "Company Name",
        "email": "robert.johnson@example.com",
        "address1": "123 Example St.",
        "address2": "Suite 403",
        "city": "New York",
        "state": "NY",
        "zip": "10001",
        "country": "USA",
        "phone": "1111111111",
        "mid": "01170981",
        "status": 0,
        "refunded": 0,
        "misused": 0,
        "checkStage": "activation",
        "unauthReason": "incomplete",
        "authTokenCustomer": "Customer Identifier",
        "channel": "",
        "imported": 1,
        "requestSequence": 1,
        "processedSequence": 1,
        "debtRepayment": 0,
        "fundingEnabled": 0,
        "fbo": "WORLDPAY_FBO1",
        "txnsession": "t1_tss_67b000bfd6fa9af5775a3dc",
        "reserved": 0,
        "inactive": 1,
        "frozen": 0,
        "tip": 0,
        "softPosId": "POS ID",
        "softPosDeviceTypeIndicator": "Indicator",
        "networkTokenIndicator": 0,
        "pinlessDebitConversion": 0,
        "submittedMethod": 3,
        "processedMethod": 25
      }
    ],
    "details": {
      "requestId": 1,
      "totals": [],
      "page": {
        "current": 1,
        "last": 1,
        "hasMore": false
      }
    },
    "errors": []
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Error | [`ErrorFourHundredException`](../../doc/models/error-four-hundred-exception.md) |


# Get Txns

Query a Transaction.
Transactions hold all of the information relating to a particular credit card transaction, including the merchant, token, subscription, customer and card information.

```php
function getTxns(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): TxnsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `search` | `?string` | Header, Optional | Set this header to filter or sort the list of resources that the method returns.<br>See [Searches](page:welcome#searches) for detailed information and examples on how to use search header. |
| `totals` | `?string` | Header, Optional | To configure a request to return a total for all instances of a field in a result set,  use the totals header in the format `totals={operator}[]={key}`.  This will calculate the desired total and return it in the `details > totals` object of the response.  For instance, if you want to sum the `total` field of all transactions,  you would use the `sum` operator. The response will include the result set,  along with the calculated total in the `details` section. See [Collection Operators](page:welcome#collection-operators) for detailed information and examples on how to use totals header. |
| `pageNumber` | `?int` | Query, Optional | Set this path parameter to request a specific page of records.<br>For example, set `?page[number]=2` to retrieve the second page of records for this request. |
| `pageLimit` | `?int` | Query, Optional | Set this path parameter to request up to a specific amount of records. By default 30 records are retrieved per page. The maximum limit that can be set is 100.<br>For example, set `?page[limit]=50` to retrieve up to 50 records for this request. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`TxnsResponseResult`](../../doc/models/txns-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $transactionsTxnsController->getTxns(
    $token,
    $requestToken,
    $search,
    $totals,
    $pageNumber,
    $pageLimit
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "p1_txn_5a1ef5e55658af7cf010000",
        "created": "2025-02-20 09:01:14.8325",
        "modified": "2025-02-20 09:01:14.8325",
        "creator": "p1_log_5a1ef5e55653ed720159d00",
        "modifier": "p1_log_5a1ef5e55653ed720159d00",
        "ipCreated": "8.8.8.8",
        "ipModified": "8.8.8.8",
        "merchant": "p1_mer_5a1ef5e55656a739a85da00",
        "token": "e41272ec5464d9ec81cc85c854837400",
        "payment": "g157b215cd94000",
        "fortxn": "t1_txn_67b5f9801e463c908f453oo",
        "fromtxn": "Reauthorize Transaction",
        "batch": "p1_bth_5a1ef5e55655f49b141d313",
        "subscription": "Identifier of Subscription",
        "statement": "Statement ID",
        "type": 1,
        "expiration": "1123",
        "serviceCode": "Code",
        "funded": 1123,
        "returned": "Transaction Returned",
        "currency": "USD",
        "fundingCurrency": "USD",
        "currencyConversion": "customerAccepted",
        "convenienceFee": 0,
        "fee": 342,
        "platform": "VANTIV",
        "authDate": 20160120,
        "authCode": "95834A",
        "captured": "2025-02-19 13:28:42",
        "settled": "2025-02-19 13:28:42",
        "settledCurrency": "USD",
        "settledTotal": 0,
        "allowPartial": 0,
        "order": "00b5f97feb5bc9bcbd9a92fz",
        "description": "$10.00 to Bergstrom and Sons",
        "descriptor": "illinois",
        "traceNumber": 0,
        "discount": 0,
        "shipping": 0,
        "duty": 0,
        "terminal": "Terminal Identifier",
        "terminalCapability": 1,
        "entryMode": 1,
        "origin": 2,
        "mobile": 0,
        "tax": 195,
        "surcharge": 0,
        "total": 20365,
        "cashback": 0,
        "authorization": "52703",
        "originalApproved": 0,
        "approved": 20365,
        "authentication": "Authentication token",
        "authenticationId": "Optional transaction ID",
        "cvv": 0,
        "cvvStatus": "notPresent",
        "swiped": 0,
        "emv": 0,
        "signature": 0,
        "pin": 1,
        "pinEntryCapability": "unknown",
        "unattended": 0,
        "cofType": "single",
        "copyReason": "resubmission",
        "clientIp": "1.1.1.1",
        "first": "Robert",
        "middle": "John",
        "last": "Johnson",
        "company": "Company Name",
        "email": "robert.johnson@example.com",
        "address1": "123 Example St.",
        "address2": "Suite 403",
        "city": "New York",
        "state": "NY",
        "zip": "10001",
        "country": "USA",
        "phone": "1111111111",
        "mid": "01170981",
        "status": 0,
        "refunded": 0,
        "misused": 0,
        "checkStage": "activation",
        "unauthReason": "incomplete",
        "authTokenCustomer": "Customer Identifier",
        "channel": "",
        "imported": 1,
        "requestSequence": 1,
        "processedSequence": 1,
        "debtRepayment": 0,
        "fundingEnabled": 0,
        "fbo": "WORLDPAY_FBO1",
        "txnsession": "t1_tss_67b000bfd6fa9af5775a3dc",
        "reserved": 0,
        "inactive": 1,
        "frozen": 0,
        "tip": 0,
        "softPosId": "POS ID",
        "softPosDeviceTypeIndicator": "Indicator",
        "networkTokenIndicator": 0,
        "pinlessDebitConversion": 0,
        "submittedMethod": 3,
        "processedMethod": 25
      }
    ],
    "details": {
      "requestId": 1,
      "totals": [],
      "page": {
        "current": 1,
        "last": 1,
        "hasMore": false
      }
    },
    "errors": []
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Error | [`ErrorFourHundredException`](../../doc/models/error-four-hundred-exception.md) |


# Post Txns

Create a Transaction.
Transactions hold all of the information relating to a particular credit card transaction, including the merchant, token, subscription, customer and card information.

```php
function postTxns(
    TxnsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): TxnsPostResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`TxnsPostRequest`](../../doc/models/txns-post-request.md) | Body, Required | Create a new transaction. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`TxnsPostResponseResult`](../../doc/models/txns-post-response-result.md)

## Example Usage

```php
$body = TxnsPostRequestBuilder::init(
    TxnsAllowPartialEnum::ALLOWED,
    'Authentication Token',
    TxnsDebtRepaymentEnum::ON,
    't1_txn_67b5f9801e463c908f453oo',
    TxnOriginEnum::APPLE,
    TxnTypeEnum::CAPTURE,
    UnauthReasonEnum::CUSTOMERCANCELLED,
    TerminalTxnsSwipedEnum::SWIPED,
    't1_mer_1344e1a5460f5cfdf21ce11',
    '11003321',
    TerminalTxnsPinEnum::PIN,
    TerminalTxnsSignatureEnum::CAPTURED,
    1010,
    TerminalTxnsUnattendedEnum::UNATTENDEDTERMINAL,
    TxnsPaymentBuilder::init(
        TxnPaymentMethodEnum::VISA,
        '1111'
    )
        ->routing('code')
        ->cvv('111')
        ->track(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
        ->build()
)
    ->batch('t1_bth_67b6129bcca1cbb7cdac000')
    ->authenticationId('Optional transaction ID')
    ->cofType(TxnsCofTypeEnum::SINGLE)
    ->currencyConversion(CurrencyConversionEnum::CUSTOMERACCEPTED)
    ->expiration('0623')
    ->fromtxn('Reauthorize an expired Transaction')
    ->copyReason(TxnsCopyReasonsEnum::RESUBMISSION)
    ->mobile(TxnsMobileEnum::NONMOBILEPOS)
    ->pinEntryCapability(TxnsPinEntryCapabilityEnum::UNKNOWN)
    ->platform(TxnsPlatformEnum::VANTIV)
    ->processedSequence(0)
    ->funded(623)
    ->returned('Returned Transaction')
    ->fundingEnabled(TxnsFundingEnabledEnum::DISABLED)
    ->fbo('WORLDPAY_FBO1')
    ->requestSequence(1)
    ->statement('statement ID')
    ->token('31b0ac1d55c898a7b6758ed2209fce00')
    ->authTokenCustomer('Customer Identifier')
    ->channel('LA')
    ->cashback(0)
    ->clientIp('216.80.4.000')
    ->company('Hotdog Water')
    ->currency(CurrencyEnum::DOP)
    ->fundingCurrency(CurrencyEnum::BRL)
    ->cvvStatus(TerminalTxnsCvvStatusEnum::NOTPRESENT)
    ->description('Neon Test')
    ->discount(0)
    ->duty(0)
    ->email('robert.johnson@example.com')
    ->entryMode(EntryModeEnum::KEYED)
    ->fee(997)
    ->first('Robert')
    ->last('Johnson')
    ->middle('John')
    ->order('identifier')
    ->shipping(0)
    ->tax(0)
    ->surcharge(0)
    ->terminal('Terminal Identifier')
    ->terminalCapability(TerminalTxnsTerminalCapabilityEnum::KEYED)
    ->address1('708 Kunde Mission')
    ->address2('Apt 3g')
    ->city('New York')
    ->state('NY')
    ->zip('10001')
    ->country(CountryEnum::USA)
    ->phone('1111111111')
    ->tmxSessionId('Threatmetrix session ID')
    ->firstTxn('t1_txn_67b6129bcca1cbb7cdac001')
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $transactionsTxnsController->postTxns(
    $body,
    $token,
    $requestToken
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "p1_txn_5a1ef5e55658af7cf010000",
        "created": "2025-02-20 09:01:14.8325",
        "modified": "2025-02-20 09:01:14.8325",
        "creator": "p1_log_5a1ef5e55653ed720159d00",
        "modifier": "p1_log_5a1ef5e55653ed720159d00",
        "ipCreated": "8.8.8.8",
        "ipModified": "8.8.8.8",
        "merchant": "p1_mer_5a1ef5e55656a739a85da00",
        "token": "e41272ec5464d9ec81cc85c854837400",
        "payment": {
          "id": "t1_pmt_1a1ef5e55653ed720159d00",
          "method": 2,
          "number": "1111",
          "routing": "0022",
          "last4": "0123",
          "bin": "075000022",
          "payment": null,
          "lastChecked": null,
          "mask": null
        },
        "fortxn": "t1_txn_67b5f9801e463c908f453oo",
        "fromtxn": "Reauthorize Transaction",
        "batch": "p1_bth_5a1ef5e55655f49b141d313",
        "subscription": "Identifier of Subscription",
        "statement": "Statement ID",
        "type": "1",
        "expiration": "1123",
        "serviceCode": "Code",
        "funded": 1123,
        "returned": "Transaction Returned",
        "currency": "USD",
        "fundingCurrency": "USD",
        "currencyConversion": "customerAccepted",
        "convenienceFee": 0,
        "fee": 342,
        "platform": "VANTIV",
        "authDate": 20160120,
        "authCode": "95834A",
        "captured": "2025-02-19 13:28:42",
        "settled": "2025-02-19 13:28:42",
        "settledCurrency": "USD",
        "settledTotal": 0,
        "allowPartial": 0,
        "order": "00b5f97feb5bc9bcbd9a92fz",
        "description": "$10.00 to Bergstrom and Sons",
        "descriptor": "illinois",
        "traceNumber": 0,
        "discount": 0,
        "shipping": 0,
        "duty": 0,
        "terminal": "Terminal Identifier",
        "terminalCapability": 1,
        "entryMode": 1,
        "origin": 2,
        "mobile": 0,
        "tax": 195,
        "surcharge": 0,
        "total": 20365,
        "cashback": 0,
        "authorization": "52703",
        "originalApproved": 0,
        "approved": 20365,
        "authentication": "Authentication token",
        "authenticationId": "Optional transaction ID",
        "cvv": 0,
        "cvvStatus": "notPresent",
        "swiped": 0,
        "emv": 0,
        "signature": 0,
        "pin": 1,
        "pinEntryCapability": "unknown",
        "unattended": 0,
        "cofType": "single",
        "copyReason": "resubmission",
        "clientIp": "1.1.1.1",
        "first": "Robert",
        "middle": "John",
        "last": "Johnson",
        "company": "Company Name",
        "email": "robert.johnson@example.com",
        "address1": "123 Example St.",
        "address2": "Suite 403",
        "city": "New York",
        "state": "NY",
        "zip": "10001",
        "country": "USA",
        "phone": "1111111111",
        "mid": "01170981",
        "status": "0",
        "refunded": 0,
        "misused": 0,
        "checkStage": "activation",
        "unauthReason": "incomplete",
        "authTokenCustomer": "Customer Identifier",
        "channel": "",
        "imported": 1,
        "requestSequence": 1,
        "processedSequence": 1,
        "debtRepayment": 0,
        "fundingEnabled": "0",
        "fbo": "WORLDPAY_FBO1",
        "txnsession": "t1_tss_67b000bfd6fa9af5775a3dc",
        "reserved": 0,
        "inactive": 1,
        "frozen": 0,
        "tip": 0,
        "softPosId": "POS ID",
        "softPosDeviceTypeIndicator": "Indicator",
        "networkTokenIndicator": 0,
        "pinlessDebitConversion": 0
      }
    ],
    "details": {
      "requestId": 1,
      "totals": [],
      "page": {
        "current": 1,
        "last": 1,
        "hasMore": false
      }
    },
    "errors": []
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Error | [`ErrorFourHundredException`](../../doc/models/error-four-hundred-exception.md) |

