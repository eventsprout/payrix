# Fee Rules

```php
$feeRulesController = $client->getFeeRulesController();
```

## Class Name

`FeeRulesController`

## Methods

* [Get Fee Rules Id](../../doc/controllers/fee-rules.md#get-fee-rules-id)
* [Put Fee Rules Id](../../doc/controllers/fee-rules.md#put-fee-rules-id)
* [Delete Fee Rules Id](../../doc/controllers/fee-rules.md#delete-fee-rules-id)
* [Get Fee Rules](../../doc/controllers/fee-rules.md#get-fee-rules)
* [Post Fee Rules](../../doc/controllers/fee-rules.md#post-fee-rules)


# Get Fee Rules Id

Query a Fee Rule that makes a Fee apply only in certain circumstances, such as applying an administration charge if a payment is under $50.

```php
function getFeeRulesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): FeeRulesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this fee rule. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`FeeRulesResponseResult`](../../doc/models/fee-rules-response-result.md)

## Example Usage

```php
$id = 't1_frl_67ce8623bc70042ef58f400';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $feeRulesController->getFeeRulesId(
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
        "id": "t1_frl_67ce8623bc70042ef58f400",
        "created": "2025-03-10 02:26:43.7799",
        "modified": "2025-03-10 02:26:43.7799",
        "creator": "t1_log_6653ed35b0d6b78d0d02a4d",
        "modifier": "t1_log_6653ed35b0d6b78d0d02a4d",
        "fee": "t1_fee_67ce8623b048d0d5284a886",
        "name": "test1",
        "description": "test1 description",
        "type": "METHOD",
        "application": "both",
        "value": "1",
        "inactive": 0,
        "frozen": 0,
        "grouping": "Fee Rule Group1"
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


# Put Fee Rules Id

Update a Fee Rule that makes a Fee apply only in certain circumstances, for example, applying an administration charge if a payment is under $50.

```php
function putFeeRulesId(
    string $id,
    FeeRulesPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): FeeRulesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this fee rule. |
| `body` | [`FeeRulesPutRequest`](../../doc/models/fee-rules-put-request.md) | Body, Required | Update Fee Rule Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`FeeRulesResponseResult`](../../doc/models/fee-rules-response-result.md)

## Example Usage

```php
$id = 't1_frl_67ce8623bc70042ef58f400';

$body = FeeRulesPutRequestBuilder::init()
    ->fee('t1_fee_67ce8623b048d0d5284a886')
    ->name('Fee Rule1')
    ->description('Fee Rule')
    ->type(FeeRuleTypeEnum::CVVRESULT)
    ->application(FeeApplicationEnum::BOTH)
    ->value('1')
    ->grouping('Fee Rule Group1')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $feeRulesController->putFeeRulesId(
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
        "id": "t1_frl_67ce8623bc70042ef58f400",
        "created": "2025-03-10 02:26:43.7799",
        "modified": "2025-03-10 02:26:43.7799",
        "creator": "t1_log_6653ed35b0d6b78d0d02a4d",
        "modifier": "t1_log_6653ed35b0d6b78d0d02a4d",
        "fee": "t1_fee_67ce8623b048d0d5284a886",
        "name": "test1",
        "description": "test1 description",
        "type": "METHOD",
        "application": "both",
        "value": "1",
        "inactive": 0,
        "frozen": 0,
        "grouping": "Fee Rule Group1"
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


# Delete Fee Rules Id

Delete a Fee Rule that makes a Fee apply only in certain circumstances, such as applying an administration charge if a payment is under $50.

```php
function deleteFeeRulesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): FeeRulesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this fee rule. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`FeeRulesResponseResult`](../../doc/models/fee-rules-response-result.md)

## Example Usage

```php
$id = 't1_frl_67ce8623bc70042ef58f400';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $feeRulesController->deleteFeeRulesId(
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
        "id": "t1_frl_67ce8623bc70042ef58f400",
        "created": "2025-03-10 02:26:43.7799",
        "modified": "2025-03-10 02:26:43.7799",
        "creator": "t1_log_6653ed35b0d6b78d0d02a4d",
        "modifier": "t1_log_6653ed35b0d6b78d0d02a4d",
        "fee": "t1_fee_67ce8623b048d0d5284a886",
        "name": "test1",
        "description": "test1 description",
        "type": "METHOD",
        "application": "both",
        "value": "1",
        "inactive": 0,
        "frozen": 0,
        "grouping": "Fee Rule Group1"
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


# Get Fee Rules

Query a Fee Rule that makes a Fee apply only in certain circumstances, such as applying an administration charge if a payment is under $50.

```php
function getFeeRules(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): FeeRulesResponseResult
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

[`FeeRulesResponseResult`](../../doc/models/fee-rules-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $feeRulesController->getFeeRules(
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
        "id": "t1_frl_67ce8623bc70042ef58f400",
        "created": "2025-03-10 02:26:43.7799",
        "modified": "2025-03-10 02:26:43.7799",
        "creator": "t1_log_6653ed35b0d6b78d0d02a4d",
        "modifier": "t1_log_6653ed35b0d6b78d0d02a4d",
        "fee": "t1_fee_67ce8623b048d0d5284a886",
        "name": "test1",
        "description": "test1 description",
        "type": "METHOD",
        "application": "both",
        "value": "1",
        "inactive": 0,
        "frozen": 0,
        "grouping": "Fee Rule Group1"
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


# Post Fee Rules

Create a conditional Fee Rule that makes fees apply only in certain circumstances, such as applying an administration charge if a payment is under $50.

```php
function postFeeRules(
    FeeRulesPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): FeeRulesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`FeeRulesPostRequest`](../../doc/models/fee-rules-post-request.md) | Body, Required | Create Fee Rule Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`FeeRulesResponseResult`](../../doc/models/fee-rules-response-result.md)

## Example Usage

```php
$body = FeeRulesPostRequestBuilder::init(
    't1_fee_67ce8623b048d0d5284a886',
    FeeRuleTypeEnum::AVSRESULT,
    '1'
)
    ->name('Fee Rule1')
    ->description('Fee Rule')
    ->application(FeeApplicationEnum::BOTH)
    ->grouping('Fee Rule Group1')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $feeRulesController->postFeeRules(
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
        "id": "t1_frl_67ce8623bc70042ef58f400",
        "created": "2025-03-10 02:26:43.7799",
        "modified": "2025-03-10 02:26:43.7799",
        "creator": "t1_log_6653ed35b0d6b78d0d02a4d",
        "modifier": "t1_log_6653ed35b0d6b78d0d02a4d",
        "fee": "t1_fee_67ce8623b048d0d5284a886",
        "name": "test1",
        "description": "test1 description",
        "type": "METHOD",
        "application": "both",
        "value": "1",
        "inactive": 0,
        "frozen": 0,
        "grouping": "Fee Rule Group1"
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

