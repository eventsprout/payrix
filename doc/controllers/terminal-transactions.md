# Terminal Transactions

```php
$terminalTransactionsController = $client->getTerminalTransactionsController();
```

## Class Name

`TerminalTransactionsController`

## Methods

* [Get Terminal Txns by Id](../../doc/controllers/terminal-transactions.md#get-terminal-txns-by-id)
* [Update Terminal Txns by Id](../../doc/controllers/terminal-transactions.md#update-terminal-txns-by-id)
* [Delete Terminal Txns by Id](../../doc/controllers/terminal-transactions.md#delete-terminal-txns-by-id)
* [Get Terminal Txns](../../doc/controllers/terminal-transactions.md#get-terminal-txns)
* [Post Terminal Txns](../../doc/controllers/terminal-transactions.md#post-terminal-txns)


# Get Terminal Txns by Id

Query a TerminalTxn holds all of the information to a related final transaction, which they are used to be reconciled with that actual, final transaction.

```php
function getTerminalTxnsById(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): TerminalTxnsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Terminal Transaction ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`TerminalTxnsResponseResult`](../../doc/models/terminal-txns-response-result.md)

## Example Usage

```php
$id = 't1_ttx_67c76e07ebc6fbbbd476ee0';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $terminalTransactionsController->getTerminalTxnsById(
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
        "id": "t1_ttx_67c76e07ebc6fbbbd476ee0",
        "created": "2025-03-04 14:40:26.0000",
        "modified": "2025-03-04 16:17:59.9960",
        "creator": "t1_log_62fd0aa37c3d8ec3a9dcea0",
        "modifier": "t1_log_62fd0aa37c3d8ec3a9dcea0",
        "ipCreated": "3.90.49.108",
        "ipModified": "3.90.49.108",
        "merchant": "t1_mer_64415e89a919c1566a2b49b",
        "mid": "4445061378323",
        "txn": "",
        "type": 4,
        "expiration": "0623",
        "currency": "CAD",
        "fundingCurrency": "CAD",
        "fee": 0,
        "platform": "VCORE",
        "authDate": 20160120,
        "authCode": "",
        "order": "",
        "description": "",
        "traceNumber": 853202,
        "discount": 0,
        "shipping": 0,
        "duty": 0,
        "terminal": "",
        "terminalCapability": 1,
        "entryMode": 1,
        "origin": 1,
        "tax": 0,
        "total": 8000,
        "cashback": 0,
        "authorization": "422301",
        "approved": 8000,
        "cvv": 0,
        "cvvStatus": "notPresent",
        "swiped": 0,
        "emv": 0,
        "signature": 0,
        "pin": 0,
        "unattended": 0,
        "pos": 0,
        "receipt": "noReceipt",
        "clientIp": "",
        "first": "",
        "middle": "",
        "last": "",
        "company": "",
        "email": "",
        "address1": "",
        "address2": "",
        "city": "",
        "state": "AB",
        "zip": "",
        "country": "CAN",
        "phone": "",
        "status": 1,
        "reserved": 0,
        "checkStage": "",
        "inactive": 0,
        "frozen": 0,
        "tid": "",
        "forterminalTxn": "",
        "token": "124f2d0efab0bcda46f2118d688bbf97",
        "binType": "CREDIT",
        "tip": 0,
        "paymentNumber": 7,
        "paymentMethod": 2,
        "originatingApp": "",
        "OEMTTxnRefNumber": "",
        "posApplicationId": "15668",
        "posApplicationName": "XML Test Example",
        "posApplicationVersion": "1.00",
        "customerReferenceNumber": "123456",
        "gatewayTransactionId": "486689252",
        "customerTicketNumber": "123456",
        "cardNetworkTransactionId": "250630144026744",
        "omnitoken": "4445223322990007",
        "convenienceFee": 0,
        "surcharge": 0,
        "softPosDeviceTypeIndicator": "",
        "terminalClassificationCode": "",
        "softPosId": "",
        "hsaFsaCardIndicator": 0,
        "gatewayTerminalId": "11",
        "descriptor": "",
        "cardNetworkBankNetReferenceNumber": "",
        "cardNetworkBankNetSettlementDate": "1123"
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


# Update Terminal Txns by Id

Update a TerminalTxn holds all of the information to a related final transaction and is used to be reconciled with that actual, final transaction.

```php
function updateTerminalTxnsById(
    string $id,
    TerminalTxnsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): TerminalTxnsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Terminal Transaction ID. |
| `body` | [`TerminalTxnsPutRequest`](../../doc/models/terminal-txns-put-request.md) | Body, Required | Update Terminal Transaction Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`TerminalTxnsResponseResult`](../../doc/models/terminal-txns-response-result.md)

## Example Usage

```php
$id = 't1_ttx_67c76e07ebc6fbbbd476ee0';

$body = TerminalTxnsPutRequestBuilder::init()
    ->binType(TerminalTxnsBinTypeEnum::DEBIT)
    ->expiration('1123')
    ->payment(
        TerminalTxnsPaymentBuilder::init()
            ->method(TerminalTxnPaymentMethodEnum::AMEX)
            ->number('2222')
            ->routing('1')
            ->expiration('0623')
            ->cvv(123)
            ->track('Track 1')
            ->build()
    )
    ->traceNumber(853202)
    ->txn('related txn')
    ->token('124f2d0efab0bcda46f2118d688bbf97')
    ->paymentNumber(7)
    ->paymentMethod(TerminalTxnPaymentMethodEnum::VISA)
    ->tip(0)
    ->originatingApp('originatingApp')
    ->oEMTTxnRefNumber('TxnRefNumber')
    ->posApplicationId('15668')
    ->unattended(TerminalTxnsUnattendedEnum::ATTENDEDTERMINAL)
    ->posApplicationName('XML Test Example')
    ->posApplicationVersion('1.00')
    ->customerReferenceNumber('123456')
    ->gatewayTransactionId('486689252')
    ->customerTicketNumber('123456')
    ->clientIp('Client IP address')
    ->description('Transaction1')
    ->swiped(TerminalTxnsSwipedEnum::SWIPED)
    ->emv(TerminalTxnsEmvEnum::DIPPED)
    ->entryMode(EntryModeEnum::KEYED)
    ->first('John')
    ->last('Doe')
    ->middle('M')
    ->order('orderId')
    ->reserved(TerminalTxnReservedEnum::NONE)
    ->signature(TerminalTxnsSignatureEnum::CAPTURED)
    ->total(8000)
    ->status(TerminalTxnStatusEnum::CAPTURED)
    ->cardNetworkTransactionId('250630144026744')
    ->omnitoken('4445223322990007')
    ->convenienceFee(0)
    ->surcharge(0)
    ->softPosDeviceTypeIndicator('device type indicator')
    ->softPosId('software POS ID')
    ->hsaFsaCardIndicator(TerminalTxnsHsaFsaCardIndicatorEnum::NOTHSAFSA)
    ->gatewayTerminalId('12')
    ->descriptor('billing Descriptor')
    ->cardNetworkBankNetReferenceNumber('cardNetworkBankNetReferenceNumber')
    ->cardNetworkBankNetSettlementDate('1123')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $terminalTransactionsController->updateTerminalTxnsById(
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
        "id": "t1_ttx_67c76e07ebc6fbbbd476ee0",
        "created": "2025-03-04 14:40:26.0000",
        "modified": "2025-03-04 16:17:59.9960",
        "creator": "t1_log_62fd0aa37c3d8ec3a9dcea0",
        "modifier": "t1_log_62fd0aa37c3d8ec3a9dcea0",
        "ipCreated": "3.90.49.108",
        "ipModified": "3.90.49.108",
        "merchant": "t1_mer_64415e89a919c1566a2b49b",
        "mid": "4445061378323",
        "txn": "",
        "type": 4,
        "expiration": "0623",
        "currency": "CAD",
        "fundingCurrency": "CAD",
        "fee": 0,
        "platform": "VCORE",
        "authDate": 20160120,
        "authCode": "",
        "order": "",
        "description": "",
        "traceNumber": 853202,
        "discount": 0,
        "shipping": 0,
        "duty": 0,
        "terminal": "",
        "terminalCapability": 1,
        "entryMode": 1,
        "origin": 1,
        "tax": 0,
        "total": 8000,
        "cashback": 0,
        "authorization": "422301",
        "approved": 8000,
        "cvv": 0,
        "cvvStatus": "notPresent",
        "swiped": 0,
        "emv": 0,
        "signature": 0,
        "pin": 0,
        "unattended": 0,
        "pos": 0,
        "receipt": "noReceipt",
        "clientIp": "",
        "first": "",
        "middle": "",
        "last": "",
        "company": "",
        "email": "",
        "address1": "",
        "address2": "",
        "city": "",
        "state": "AB",
        "zip": "",
        "country": "CAN",
        "phone": "",
        "status": 1,
        "reserved": 0,
        "checkStage": "",
        "inactive": 0,
        "frozen": 0,
        "tid": "",
        "forterminalTxn": "",
        "token": "124f2d0efab0bcda46f2118d688bbf97",
        "binType": "CREDIT",
        "tip": 0,
        "paymentNumber": 7,
        "paymentMethod": 2,
        "originatingApp": "",
        "OEMTTxnRefNumber": "",
        "posApplicationId": "15668",
        "posApplicationName": "XML Test Example",
        "posApplicationVersion": "1.00",
        "customerReferenceNumber": "123456",
        "gatewayTransactionId": "486689252",
        "customerTicketNumber": "123456",
        "cardNetworkTransactionId": "250630144026744",
        "omnitoken": "4445223322990007",
        "convenienceFee": 0,
        "surcharge": 0,
        "softPosDeviceTypeIndicator": "",
        "terminalClassificationCode": "",
        "softPosId": "",
        "hsaFsaCardIndicator": 0,
        "gatewayTerminalId": "11",
        "descriptor": "",
        "cardNetworkBankNetReferenceNumber": "",
        "cardNetworkBankNetSettlementDate": "1123"
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


# Delete Terminal Txns by Id

Delete a TerminalTxn that holds all of the information to a related final transaction and is used to be reconciled with that actual, final transaction.

```php
function deleteTerminalTxnsById(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): TerminalTxnsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Terminal Transaction ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`TerminalTxnsResponseResult`](../../doc/models/terminal-txns-response-result.md)

## Example Usage

```php
$id = 't1_ttx_67c76e07ebc6fbbbd476ee0';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $terminalTransactionsController->deleteTerminalTxnsById(
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
        "id": "t1_ttx_67c76e07ebc6fbbbd476ee0",
        "created": "2025-03-04 14:40:26.0000",
        "modified": "2025-03-04 16:17:59.9960",
        "creator": "t1_log_62fd0aa37c3d8ec3a9dcea0",
        "modifier": "t1_log_62fd0aa37c3d8ec3a9dcea0",
        "ipCreated": "3.90.49.108",
        "ipModified": "3.90.49.108",
        "merchant": "t1_mer_64415e89a919c1566a2b49b",
        "mid": "4445061378323",
        "txn": "",
        "type": 4,
        "expiration": "0623",
        "currency": "CAD",
        "fundingCurrency": "CAD",
        "fee": 0,
        "platform": "VCORE",
        "authDate": 20160120,
        "authCode": "",
        "order": "",
        "description": "",
        "traceNumber": 853202,
        "discount": 0,
        "shipping": 0,
        "duty": 0,
        "terminal": "",
        "terminalCapability": 1,
        "entryMode": 1,
        "origin": 1,
        "tax": 0,
        "total": 8000,
        "cashback": 0,
        "authorization": "422301",
        "approved": 8000,
        "cvv": 0,
        "cvvStatus": "notPresent",
        "swiped": 0,
        "emv": 0,
        "signature": 0,
        "pin": 0,
        "unattended": 0,
        "pos": 0,
        "receipt": "noReceipt",
        "clientIp": "",
        "first": "",
        "middle": "",
        "last": "",
        "company": "",
        "email": "",
        "address1": "",
        "address2": "",
        "city": "",
        "state": "AB",
        "zip": "",
        "country": "CAN",
        "phone": "",
        "status": 1,
        "reserved": 0,
        "checkStage": "",
        "inactive": 0,
        "frozen": 0,
        "tid": "",
        "forterminalTxn": "",
        "token": "124f2d0efab0bcda46f2118d688bbf97",
        "binType": "CREDIT",
        "tip": 0,
        "paymentNumber": 7,
        "paymentMethod": 2,
        "originatingApp": "",
        "OEMTTxnRefNumber": "",
        "posApplicationId": "15668",
        "posApplicationName": "XML Test Example",
        "posApplicationVersion": "1.00",
        "customerReferenceNumber": "123456",
        "gatewayTransactionId": "486689252",
        "customerTicketNumber": "123456",
        "cardNetworkTransactionId": "250630144026744",
        "omnitoken": "4445223322990007",
        "convenienceFee": 0,
        "surcharge": 0,
        "softPosDeviceTypeIndicator": "",
        "terminalClassificationCode": "",
        "softPosId": "",
        "hsaFsaCardIndicator": 0,
        "gatewayTerminalId": "11",
        "descriptor": "",
        "cardNetworkBankNetReferenceNumber": "",
        "cardNetworkBankNetSettlementDate": "1123"
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


# Get Terminal Txns

Query a TerminalTxn, which holds all of the information to a related final transaction and is used to reconcile with the actual, final transaction.

```php
function getTerminalTxns(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): TerminalTxnsResponseResult
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

[`TerminalTxnsResponseResult`](../../doc/models/terminal-txns-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $terminalTransactionsController->getTerminalTxns(
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
        "id": "t1_ttx_67c76e07ebc6fbbbd476ee0",
        "created": "2025-03-04 14:40:26.0000",
        "modified": "2025-03-04 16:17:59.9960",
        "creator": "t1_log_62fd0aa37c3d8ec3a9dcea0",
        "modifier": "t1_log_62fd0aa37c3d8ec3a9dcea0",
        "ipCreated": "3.90.49.108",
        "ipModified": "3.90.49.108",
        "merchant": "t1_mer_64415e89a919c1566a2b49b",
        "mid": "4445061378323",
        "txn": "",
        "type": 4,
        "expiration": "0623",
        "currency": "CAD",
        "fundingCurrency": "CAD",
        "fee": 0,
        "platform": "VCORE",
        "authDate": 20160120,
        "authCode": "",
        "order": "",
        "description": "",
        "traceNumber": 853202,
        "discount": 0,
        "shipping": 0,
        "duty": 0,
        "terminal": "",
        "terminalCapability": 1,
        "entryMode": 1,
        "origin": 1,
        "tax": 0,
        "total": 8000,
        "cashback": 0,
        "authorization": "422301",
        "approved": 8000,
        "cvv": 0,
        "cvvStatus": "notPresent",
        "swiped": 0,
        "emv": 0,
        "signature": 0,
        "pin": 0,
        "unattended": 0,
        "pos": 0,
        "receipt": "noReceipt",
        "clientIp": "",
        "first": "",
        "middle": "",
        "last": "",
        "company": "",
        "email": "",
        "address1": "",
        "address2": "",
        "city": "",
        "state": "AB",
        "zip": "",
        "country": "CAN",
        "phone": "",
        "status": 1,
        "reserved": 0,
        "checkStage": "",
        "inactive": 0,
        "frozen": 0,
        "tid": "",
        "forterminalTxn": "",
        "token": "124f2d0efab0bcda46f2118d688bbf97",
        "binType": "CREDIT",
        "tip": 0,
        "paymentNumber": 7,
        "paymentMethod": 2,
        "originatingApp": "",
        "OEMTTxnRefNumber": "",
        "posApplicationId": "15668",
        "posApplicationName": "XML Test Example",
        "posApplicationVersion": "1.00",
        "customerReferenceNumber": "123456",
        "gatewayTransactionId": "486689252",
        "customerTicketNumber": "123456",
        "cardNetworkTransactionId": "250630144026744",
        "omnitoken": "4445223322990007",
        "convenienceFee": 0,
        "surcharge": 0,
        "softPosDeviceTypeIndicator": "",
        "terminalClassificationCode": "",
        "softPosId": "",
        "hsaFsaCardIndicator": 0,
        "gatewayTerminalId": "11",
        "descriptor": "",
        "cardNetworkBankNetReferenceNumber": "",
        "cardNetworkBankNetSettlementDate": "1123"
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


# Post Terminal Txns

Create a TerminalTxn.
TerminalTxns hold all of the information to a related final transaction. They are used to be reconcilliated with that actual, final transaction.

```php
function postTerminalTxns(
    TerminalTxnsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): TerminalTxnsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`TerminalTxnsPostRequest`](../../doc/models/terminal-txns-post-request.md) | Body, Required | Create Terminal Transaction Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`TerminalTxnsResponseResult`](../../doc/models/terminal-txns-response-result.md)

## Example Usage

```php
$body = TerminalTxnsPostRequestBuilder::init(
    TerminalTxnsBinTypeEnum::DEBIT,
    TerminalTxnOriginEnum::TERMINAL,
    TerminalTxnsPosEnum::POSACTIVATION,
    TerminalTxnTypeEnum::SALE,
    TerminalTxnsSwipedEnum::SWIPED,
    't1_mer_64415e89a919c1566a2b49b',
    '4445061378323',
    TerminalTxnsPinEnum::NOPIN,
    TerminalTxnsSignatureEnum::NOTCAPTURED,
    8000,
    TerminalTxnStatusEnum::APPROVED,
    InactiveEnum::ACTIVE,
    FrozenEnum::NOTFROZEN
)
    ->expiration('1023')
    ->forterminalTxn('forterminalTxn')
    ->platform(PlatformModelEnum::VCORE)
    ->receipt(TerminalTxnsReceiptEnum::NORECEIPT)
    ->tid('Terminal ID')
    ->traceNumber(853202)
    ->txn('related txn')
    ->token(
        '124f2d0efab0bcda46f2118d688bbf97'
    )
    ->paymentNumber(7)
    ->paymentMethod(TerminalTxnPaymentMethodEnum::VISA)
    ->tip(0)
    ->originatingApp('originatingApp')
    ->oEMTTxnRefNumber('TxnRefNumber')
    ->posApplicationId('15668')
    ->posApplicationName('XML Test Example')
    ->posApplicationVersion('1.00')
    ->customerReferenceNumber('123456')
    ->gatewayTransactionId('486689252')
    ->customerTicketNumber('123456')
    ->authCode('authorization code')
    ->authDate(20160120)
    ->cashback(0)
    ->clientIp('Client IP address')
    ->company('company1')
    ->currency(CurrencyEnum::USD)
    ->fundingCurrency(CurrencyEnum::USD)
    ->cvvStatus(TerminalTxnsCvvStatusEnum::NOTPRESENT)
    ->description('description1')
    ->discount(0)
    ->duty(0)
    ->email('john.johnson@example.com')
    ->entryMode(EntryModeEnum::KEYED)
    ->fee(0)
    ->first('John')
    ->last('Doe')
    ->middle('M')
    ->order('orderId')
    ->shipping(0)
    ->tax(0)
    ->terminal('identifier of terminal')
    ->terminalCapability(TerminalTxnsTerminalCapabilityEnum::KEYED)
    ->unattended(TerminalTxnsUnattendedEnum::ATTENDEDTERMINAL)
    ->address1('address1')
    ->address2('address2')
    ->city('city1')
    ->state('AB')
    ->zip('ZIP code')
    ->country(CountryEnum::CAN)
    ->phone('9999888888')
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $terminalTransactionsController->postTerminalTxns(
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
        "id": "t1_ttx_67c76e07ebc6fbbbd476ee0",
        "created": "2025-03-04 14:40:26.0000",
        "modified": "2025-03-04 16:17:59.9960",
        "creator": "t1_log_62fd0aa37c3d8ec3a9dcea0",
        "modifier": "t1_log_62fd0aa37c3d8ec3a9dcea0",
        "ipCreated": "3.90.49.108",
        "ipModified": "3.90.49.108",
        "merchant": "t1_mer_64415e89a919c1566a2b49b",
        "mid": "4445061378323",
        "txn": "",
        "type": 4,
        "expiration": "0623",
        "currency": "CAD",
        "fundingCurrency": "CAD",
        "fee": 0,
        "platform": "VCORE",
        "authDate": 20160120,
        "authCode": "",
        "order": "",
        "description": "",
        "traceNumber": 853202,
        "discount": 0,
        "shipping": 0,
        "duty": 0,
        "terminal": "",
        "terminalCapability": 1,
        "entryMode": 1,
        "origin": 1,
        "tax": 0,
        "total": 8000,
        "cashback": 0,
        "authorization": "422301",
        "approved": 8000,
        "cvv": 0,
        "cvvStatus": "notPresent",
        "swiped": 0,
        "emv": 0,
        "signature": 0,
        "pin": 0,
        "unattended": 0,
        "pos": 0,
        "receipt": "noReceipt",
        "clientIp": "",
        "first": "",
        "middle": "",
        "last": "",
        "company": "",
        "email": "",
        "address1": "",
        "address2": "",
        "city": "",
        "state": "AB",
        "zip": "",
        "country": "CAN",
        "phone": "",
        "status": 1,
        "reserved": 0,
        "checkStage": "",
        "inactive": 0,
        "frozen": 0,
        "tid": "",
        "forterminalTxn": "",
        "token": "124f2d0efab0bcda46f2118d688bbf97",
        "binType": "CREDIT",
        "tip": 0,
        "paymentNumber": 7,
        "paymentMethod": 2,
        "originatingApp": "",
        "OEMTTxnRefNumber": "",
        "posApplicationId": "15668",
        "posApplicationName": "XML Test Example",
        "posApplicationVersion": "1.00",
        "customerReferenceNumber": "123456",
        "gatewayTransactionId": "486689252",
        "customerTicketNumber": "123456",
        "cardNetworkTransactionId": "250630144026744",
        "omnitoken": "4445223322990007",
        "convenienceFee": 0,
        "surcharge": 0,
        "softPosDeviceTypeIndicator": "",
        "terminalClassificationCode": "",
        "softPosId": "",
        "hsaFsaCardIndicator": 0,
        "gatewayTerminalId": "11",
        "descriptor": "",
        "cardNetworkBankNetReferenceNumber": "",
        "cardNetworkBankNetSettlementDate": "1123"
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

