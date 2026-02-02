# Transaction Holds

```php
$transactionHoldsController = $client->getTransactionHoldsController();
```

## Class Name

`TransactionHoldsController`

## Methods

* [Get Holds Id](../../doc/controllers/transaction-holds.md#get-holds-id)
* [Put Holds Id](../../doc/controllers/transaction-holds.md#put-holds-id)
* [Get Holds](../../doc/controllers/transaction-holds.md#get-holds)
* [Post Holds](../../doc/controllers/transaction-holds.md#post-holds)


# Get Holds Id

Query a holds resource.
A holds resource represents a reviewable action taken on a Transaction.

```php
function getHoldsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): HoldsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`HoldsResponseResult`](../../doc/models/holds-response-result.md)

## Example Usage

```php
$id = 't1_hld_0000fc11df8e4c00000e00c';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $transactionHoldsController->getHoldsId(
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
        "id": "t1_hld_0000fc11df8e4c00000e00c",
        "created": "2025-01-31 08:42:16.7318",
        "modified": "2025-01-31 08:42:16.7318",
        "creator": "t1_log_123e1cbf1bcfe0d606bd000",
        "modifier": "t1_log_123e1cbf1bcfe0d606bd000",
        "login": "t1_log_123fc13e1234f8fd20e0fa0",
        "entity": "t1_ent_66d205375262ec0f0000000",
        "txn": "t1_txn_6729fc89898bbfaedc00ff0",
        "terminalTxn": "t1_xyz_12345e666662ddca123a0c0",
        "account": "t1_xyz_1234bff729db11267ad0000",
        "verification": "t1_xyz_1234567b000ebe0b0e0dfe0",
        "verificationRef": "t1_xyz_12345eb00f0cf1bfc00be0f",
        "decisionAction": "t1_xyz_00a005b3e000c0ce000e0a0",
        "action": 3,
        "released": "2025-01-31 08:42:16",
        "reviewed": "2025-02-02 08:50:16",
        "inactive": 0,
        "frozen": 0,
        "releaseAction": 2,
        "delayedFundingStartDate": "2025-02-03 08:42:16",
        "delayedFundingEndDate": "2025-02-04 08:42:16",
        "analyst": "t1_log_00aa000a888801466471d0z",
        "claimed": "2025-02-25 06:42:16",
        "holdSource": "API_DECISION",
        "holdSourceId": "5a9bba34-38eb-489e-abd8-765e18562a08",
        "division": "t1_div_00ea000e00e0eb1234c09e9"
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


# Put Holds Id

Details for update on holds

```php
function putHoldsId(
    string $id,
    HoldsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): HoldsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `body` | [`HoldsPutRequest`](../../doc/models/holds-put-request.md) | Body, Required | Update Transaction Hold Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`HoldsResponseResult`](../../doc/models/holds-response-result.md)

## Example Usage

```php
$id = 't1_hld_0000fc11df8e4c00000e00c';

$body = HoldsPutRequestBuilder::init()
    ->login('t1_hld_0000fc11df8e4c00000e00c')
    ->verificationRef('t1_xyz_12345eb00f0cf1bfc00be0f')
    ->released('2025-01-31 08:42:16')
    ->reviewed('2025-01-31 08:42:16')
    ->releaseAction(HoldsReleaseActionEnum::CANCELLED)
    ->holdSource(HoldsHoldSourceEnum::API_DECISION)
    ->holdSourceId('5a9bba34-38eb-489e-abd8-765e18562a08')
    ->delayedFundingStartDate('2025-01-31 08:42:16')
    ->delayedFundingEndDate('2025-01-31 08:42:16')
    ->analyst('name')
    ->claimed('2025-01-31 08:42:16')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $transactionHoldsController->putHoldsId(
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
        "id": "t1_hld_0000fc11df8e4c00000e00c",
        "created": "2025-01-31 08:42:16.7318",
        "modified": "2025-01-31 08:42:16.7318",
        "creator": "t1_log_123e1cbf1bcfe0d606bd000",
        "modifier": "t1_log_123e1cbf1bcfe0d606bd000",
        "login": "t1_log_123fc13e1234f8fd20e0fa0",
        "entity": "t1_ent_66d205375262ec0f0000000",
        "txn": "t1_txn_6729fc89898bbfaedc00ff0",
        "terminalTxn": "t1_xyz_12345e666662ddca123a0c0",
        "account": "t1_xyz_1234bff729db11267ad0000",
        "verification": "t1_xyz_1234567b000ebe0b0e0dfe0",
        "verificationRef": "t1_xyz_12345eb00f0cf1bfc00be0f",
        "decisionAction": "t1_xyz_00a005b3e000c0ce000e0a0",
        "action": 3,
        "released": "2025-01-31 08:42:16",
        "reviewed": "2025-02-02 08:50:16",
        "inactive": 0,
        "frozen": 0,
        "releaseAction": 2,
        "delayedFundingStartDate": "2025-02-03 08:42:16",
        "delayedFundingEndDate": "2025-02-04 08:42:16",
        "analyst": "t1_log_00aa000a888801466471d0z",
        "claimed": "2025-02-25 06:42:16",
        "holdSource": "API_DECISION",
        "holdSourceId": "5a9bba34-38eb-489e-abd8-765e18562a08",
        "division": "t1_div_00ea000e00e0eb1234c09e9"
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


# Get Holds

Query a holds resource.
A holds resource represents a reviewable action taken on a Transaction.

```php
function getHolds(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): HoldsResponseResult
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

[`HoldsResponseResult`](../../doc/models/holds-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $transactionHoldsController->getHolds(
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
        "id": "t1_hld_0000fc11df8e4c00000e00c",
        "created": "2025-01-31 08:42:16.7318",
        "modified": "2025-01-31 08:42:16.7318",
        "creator": "t1_log_123e1cbf1bcfe0d606bd000",
        "modifier": "t1_log_123e1cbf1bcfe0d606bd000",
        "login": "t1_log_123fc13e1234f8fd20e0fa0",
        "entity": "t1_ent_66d205375262ec0f0000000",
        "txn": "t1_txn_6729fc89898bbfaedc00ff0",
        "terminalTxn": "t1_xyz_12345e666662ddca123a0c0",
        "account": "t1_xyz_1234bff729db11267ad0000",
        "verification": "t1_xyz_1234567b000ebe0b0e0dfe0",
        "verificationRef": "t1_xyz_12345eb00f0cf1bfc00be0f",
        "decisionAction": "t1_xyz_00a005b3e000c0ce000e0a0",
        "action": 3,
        "released": "2025-01-31 08:42:16",
        "reviewed": "2025-02-02 08:50:16",
        "inactive": 0,
        "frozen": 0,
        "releaseAction": 2,
        "delayedFundingStartDate": "2025-02-03 08:42:16",
        "delayedFundingEndDate": "2025-02-04 08:42:16",
        "analyst": "t1_log_00aa000a888801466471d0z",
        "claimed": "2025-02-25 06:42:16",
        "holdSource": "API_DECISION",
        "holdSourceId": "5a9bba34-38eb-489e-abd8-765e18562a08",
        "division": "t1_div_00ea000e00e0eb1234c09e9"
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


# Post Holds

Create a holds resource.
A holds resource represents a reviewable action taken on a Transaction.

```php
function postHolds(
    HoldsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): HoldsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`HoldsPostRequest`](../../doc/models/holds-post-request.md) | Body, Required | Create a Transaction Hold Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`HoldsResponseResult`](../../doc/models/holds-response-result.md)

## Example Usage

```php
$body = HoldsPostRequestBuilder::init(
    't1_hld_0000fc11df8e4c00000e00c'
)
    ->verificationRef('t1_xyz_12345eb00f0cf1bfc00be0f')
    ->released('2025-01-31 08:42:16')
    ->reviewed('2025-01-31 08:42:16')
    ->releaseAction(HoldsReleaseActionEnum::CANCELLED)
    ->holdSource(HoldsHoldSourceEnum::API_DECISION)
    ->holdSourceId('5a9bba34-38eb-489e-abd8-765e18562a08')
    ->delayedFundingStartDate('2025-01-31 08:42:16')
    ->delayedFundingEndDate('2025-01-31 08:42:16')
    ->analyst('name')
    ->claimed('2025-01-31 08:42:16')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $transactionHoldsController->postHolds(
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
        "id": "t1_hld_0000fc11df8e4c00000e00c",
        "created": "2025-01-31 08:42:16.7318",
        "modified": "2025-01-31 08:42:16.7318",
        "creator": "t1_log_123e1cbf1bcfe0d606bd000",
        "modifier": "t1_log_123e1cbf1bcfe0d606bd000",
        "login": "t1_log_123fc13e1234f8fd20e0fa0",
        "entity": "t1_ent_66d205375262ec0f0000000",
        "txn": "t1_txn_6729fc89898bbfaedc00ff0",
        "terminalTxn": "t1_xyz_12345e666662ddca123a0c0",
        "account": "t1_xyz_1234bff729db11267ad0000",
        "verification": "t1_xyz_1234567b000ebe0b0e0dfe0",
        "verificationRef": "t1_xyz_12345eb00f0cf1bfc00be0f",
        "decisionAction": "t1_xyz_00a005b3e000c0ce000e0a0",
        "action": 3,
        "released": "2025-01-31 08:42:16",
        "reviewed": "2025-02-02 08:50:16",
        "inactive": 0,
        "frozen": 0,
        "releaseAction": 2,
        "delayedFundingStartDate": "2025-02-03 08:42:16",
        "delayedFundingEndDate": "2025-02-04 08:42:16",
        "analyst": "t1_log_00aa000a888801466471d0z",
        "claimed": "2025-02-25 06:42:16",
        "holdSource": "API_DECISION",
        "holdSourceId": "5a9bba34-38eb-489e-abd8-765e18562a08",
        "division": "t1_div_00ea000e00e0eb1234c09e9"
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

