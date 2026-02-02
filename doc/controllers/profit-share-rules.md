# Profit Share Rules

```php
$profitShareRulesController = $client->getProfitShareRulesController();
```

## Class Name

`ProfitShareRulesController`

## Methods

* [Get Profit Share Rules Id](../../doc/controllers/profit-share-rules.md#get-profit-share-rules-id)
* [Put Profit Share Rules Id](../../doc/controllers/profit-share-rules.md#put-profit-share-rules-id)
* [Delete Profit Share Rules Id](../../doc/controllers/profit-share-rules.md#delete-profit-share-rules-id)
* [Get Profit Share Rules](../../doc/controllers/profit-share-rules.md#get-profit-share-rules)
* [Post Profit Share Rules](../../doc/controllers/profit-share-rules.md#post-profit-share-rules)


# Get Profit Share Rules Id

Query a ProfitShare Rule, which is a piece of conditional logic that makes a ProfitShare apply only in certain circumstances.

```php
function getProfitShareRulesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): ProfitShareRulesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Profit Share Rule ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`ProfitShareRulesResponseResult`](../../doc/models/profit-share-rules-response-result.md)

## Example Usage

```php
$id = 't1_psl_63de0f98555d322f0513b00';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $profitShareRulesController->getProfitShareRulesId(
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
        "id": "t1_psl_63de0f98555d322f0513b00",
        "created": "2023-02-04 02:56:08.3497",
        "modified": "2023-02-04 02:56:08.3497",
        "creator": "t1_log_63d25f51ea7ddb271d78304",
        "modifier": "t1_log_63d25f51ea7ddb271d78304",
        "profitShare": "t1_psh_63de0ece4959d9de8194a4d",
        "name": "Test2",
        "description": "Test2",
        "type": "less",
        "value": "5",
        "grouping": "",
        "inactive": 0,
        "frozen": 0
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


# Put Profit Share Rules Id

Update a ProfitShare Rule, which is a piece of conditional logic that makes a ProfitShare apply only in certain circumstances.

```php
function putProfitShareRulesId(
    string $id,
    ProfitShareRulesPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): ProfitShareRulesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Profit Share Rule ID. |
| `body` | [`ProfitShareRulesPutRequest`](../../doc/models/profit-share-rules-put-request.md) | Body, Required | Update Profit Share Rule Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ProfitShareRulesResponseResult`](../../doc/models/profit-share-rules-response-result.md)

## Example Usage

```php
$id = 't1_psl_63de0f98555d322f0513b00';

$body = ProfitShareRulesPutRequestBuilder::init()
    ->profitShare('t1_psh_63de0ece4959d9de8194a4d')
    ->name('Test2')
    ->description('Test2')
    ->type(ProfitShareRuleTypeEnum::LESS)
    ->value('5')
    ->grouping('group1')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $profitShareRulesController->putProfitShareRulesId(
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
        "id": "t1_psl_63de0f98555d322f0513b00",
        "created": "2023-02-04 02:56:08.3497",
        "modified": "2023-02-04 02:56:08.3497",
        "creator": "t1_log_63d25f51ea7ddb271d78304",
        "modifier": "t1_log_63d25f51ea7ddb271d78304",
        "profitShare": "t1_psh_63de0ece4959d9de8194a4d",
        "name": "Test2",
        "description": "Test2",
        "type": "less",
        "value": "5",
        "grouping": "",
        "inactive": 0,
        "frozen": 0
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


# Delete Profit Share Rules Id

Delete a ProfitShare Rule, which is a piece of conditional logic that makes a ProfitShare apply only in certain circumstances.

```php
function deleteProfitShareRulesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): ProfitShareRulesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Profit Share Rule ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ProfitShareRulesResponseResult`](../../doc/models/profit-share-rules-response-result.md)

## Example Usage

```php
$id = 't1_psl_63de0f98555d322f0513b00';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $profitShareRulesController->deleteProfitShareRulesId(
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
        "id": "t1_psl_63de0f98555d322f0513b00",
        "created": "2023-02-04 02:56:08.3497",
        "modified": "2023-02-04 02:56:08.3497",
        "creator": "t1_log_63d25f51ea7ddb271d78304",
        "modifier": "t1_log_63d25f51ea7ddb271d78304",
        "profitShare": "t1_psh_63de0ece4959d9de8194a4d",
        "name": "Test2",
        "description": "Test2",
        "type": "less",
        "value": "5",
        "grouping": "",
        "inactive": 0,
        "frozen": 0
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


# Get Profit Share Rules

Query a ProfitShare Rule.
A ProfitShare Rule is a piece of conditional logic that makes a ProfitShare apply only in certain circumstances.

```php
function getProfitShareRules(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): ProfitShareRulesResponseResult
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

[`ProfitShareRulesResponseResult`](../../doc/models/profit-share-rules-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $profitShareRulesController->getProfitShareRules(
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
        "id": "t1_psl_63de0f98555d322f0513b00",
        "created": "2023-02-04 02:56:08.3497",
        "modified": "2023-02-04 02:56:08.3497",
        "creator": "t1_log_63d25f51ea7ddb271d78304",
        "modifier": "t1_log_63d25f51ea7ddb271d78304",
        "profitShare": "t1_psh_63de0ece4959d9de8194a4d",
        "name": "Test2",
        "description": "Test2",
        "type": "less",
        "value": "5",
        "grouping": "",
        "inactive": 0,
        "frozen": 0
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


# Post Profit Share Rules

Create a ProfitShare Rule.
A ProfitShare Rule is a piece of conditional logic that makes a ProfitShare apply only in certain circumstances.

```php
function postProfitShareRules(
    ProfitShareRulesPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): ProfitShareRulesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`ProfitShareRulesPostRequest`](../../doc/models/profit-share-rules-post-request.md) | Body, Required | Create Profit Share Rule Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ProfitShareRulesResponseResult`](../../doc/models/profit-share-rules-response-result.md)

## Example Usage

```php
$body = ProfitShareRulesPostRequestBuilder::init(
    't1_psh_63de0ece4959d9de8194a4d',
    ProfitShareRuleTypeEnum::LESS,
    '5'
)
    ->name('Test2')
    ->description('Test2')
    ->grouping('group1')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $profitShareRulesController->postProfitShareRules(
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
        "id": "t1_psl_63de0f98555d322f0513b00",
        "created": "2023-02-04 02:56:08.3497",
        "modified": "2023-02-04 02:56:08.3497",
        "creator": "t1_log_63d25f51ea7ddb271d78304",
        "modifier": "t1_log_63d25f51ea7ddb271d78304",
        "profitShare": "t1_psh_63de0ece4959d9de8194a4d",
        "name": "Test2",
        "description": "Test2",
        "type": "less",
        "value": "5",
        "grouping": "",
        "inactive": 0,
        "frozen": 0
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

