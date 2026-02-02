# Decisions

Decisions deal with the schedule and rules for a check done on Transactions.

```php
$decisionsController = $client->getDecisionsController();
```

## Class Name

`DecisionsController`

## Methods

* [Get Decisions Id](../../doc/controllers/decisions.md#get-decisions-id)
* [Put Decisions Id](../../doc/controllers/decisions.md#put-decisions-id)
* [Delete Decisions Id](../../doc/controllers/decisions.md#delete-decisions-id)
* [Get Decisions](../../doc/controllers/decisions.md#get-decisions)
* [Post Decisions](../../doc/controllers/decisions.md#post-decisions)


# Get Decisions Id

Query a Decision's resource.

```php
function getDecisionsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): DecisionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Decision ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`DecisionsResponseResult`](../../doc/models/decisions-response-result.md)

## Example Usage

```php
$id = 't1_dcs_67ddb8ad653487caf88cc00';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $decisionsController->getDecisionsId(
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
        "id": "t1_dcs_67ddb8ad653487caf88cc00",
        "created": "2025-03-21 15:06:21.4313",
        "modified": "2025-03-21 15:06:21.4313",
        "creator": "t1_log_61e72ab44fd39df9483aa2c",
        "modifier": "t1_log_61e72ab44fd39df9483aa2c",
        "login": "t1_log_61e72ab44fd39df9483aa2c",
        "org": "t1_org_5fada4629c317f80bc9cb12",
        "entity": "",
        "decision": "",
        "type": "cvv",
        "target": "postauth",
        "action": 1,
        "sequence": 0,
        "amount": 0,
        "value": "1",
        "period": "days",
        "periodFactor": 1,
        "low": 1,
        "high": 2,
        "inactive": 0,
        "frozen": 0,
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_000111d4d504f21414978f0",
        "application": "txn",
        "options": 0,
        "errorMessage": "Unable to accept without CVV.",
        "reason": "",
        "additionalOptions": 0,
        "level": "partition",
        "schedule": "",
        "scheduleFactor": 1,
        "start": 20160120,
        "finish": 20160120,
        "useCache": 0,
        "cacheTime": 0
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


# Put Decisions Id

Update a Decisions resource, which represents the schedule and rules for a check done on Transactions.

```php
function putDecisionsId(
    string $id,
    DecisionsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): DecisionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Decision ID. |
| `body` | [`DecisionsPutRequest`](../../doc/models/decisions-put-request.md) | Body, Required | Update Decision Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`DecisionsResponseResult`](../../doc/models/decisions-response-result.md)

## Example Usage

```php
$id = 't1_dcs_67ddb8ad653487caf88cc00';

$body = DecisionsPutRequestBuilder::init()
    ->login('t1_log_61e72ab44fd39df9483aa2c')
    ->org('t1_org_5fada4629c317f80bc9cb12')
    ->entity('t1_ent_67d86dfd3442f3e2927ecbd')
    ->decision('t1_dcs_6789a1b36647513d66cf30a')
    ->division('t1_div_67c56806728fbbf0bae0b00')
    ->partition('t1_ptn_000111d4d504f21414978f0')
    ->application(DecisionActionsApplicationEnum::TXN)
    ->level('partition')
    ->type(DecisionTypeEnum::CVV)
    ->target(DecisionsTargetEnum::POSTAUTH)
    ->action(DescisionActionEnum::BLOCK)
    ->sequence(0)
    ->amount(1)
    ->value('1')
    ->period(DecisionsPeriodEnum::DAYS)
    ->periodFactor(1)
    ->scheduleFactor(1)
    ->start(20160120)
    ->finish(20160120)
    ->low(1)
    ->high(2)
    ->useCache(DecisionsUseCacheEnum::DISABLED)
    ->cacheTime(0)
    ->options(0)
    ->additionalOptions(0)
    ->errorMessage('Unable to accept without CVV')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $decisionsController->putDecisionsId(
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
        "id": "t1_dcs_67ddb8ad653487caf88cc00",
        "created": "2025-03-21 15:06:21.4313",
        "modified": "2025-03-21 15:06:21.4313",
        "creator": "t1_log_61e72ab44fd39df9483aa2c",
        "modifier": "t1_log_61e72ab44fd39df9483aa2c",
        "login": "t1_log_61e72ab44fd39df9483aa2c",
        "org": "t1_org_5fada4629c317f80bc9cb12",
        "entity": "",
        "decision": "",
        "type": "cvv",
        "target": "postauth",
        "action": 1,
        "sequence": 0,
        "amount": 0,
        "value": "1",
        "period": "days",
        "periodFactor": 1,
        "low": 1,
        "high": 2,
        "inactive": 0,
        "frozen": 0,
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_000111d4d504f21414978f0",
        "application": "txn",
        "options": 0,
        "errorMessage": "Unable to accept without CVV.",
        "reason": "",
        "additionalOptions": 0,
        "level": "partition",
        "schedule": "",
        "scheduleFactor": 1,
        "start": 20160120,
        "finish": 20160120,
        "useCache": 0,
        "cacheTime": 0
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


# Delete Decisions Id

Delete a Decision's resource, which represents the schedule and rules for a check done on Transactions.

```php
function deleteDecisionsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): DecisionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource, also known as The Decision ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`DecisionsResponseResult`](../../doc/models/decisions-response-result.md)

## Example Usage

```php
$id = 't1_dcs_67ddb8ad653487caf88cc00';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $decisionsController->deleteDecisionsId(
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
        "id": "t1_dcs_67ddb8ad653487caf88cc00",
        "created": "2025-03-21 15:06:21.4313",
        "modified": "2025-03-21 15:06:21.4313",
        "creator": "t1_log_61e72ab44fd39df9483aa2c",
        "modifier": "t1_log_61e72ab44fd39df9483aa2c",
        "login": "t1_log_61e72ab44fd39df9483aa2c",
        "org": "t1_org_5fada4629c317f80bc9cb12",
        "entity": "",
        "decision": "",
        "type": "cvv",
        "target": "postauth",
        "action": 1,
        "sequence": 0,
        "amount": 0,
        "value": "1",
        "period": "days",
        "periodFactor": 1,
        "low": 1,
        "high": 2,
        "inactive": 0,
        "frozen": 0,
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_000111d4d504f21414978f0",
        "application": "txn",
        "options": 0,
        "errorMessage": "Unable to accept without CVV.",
        "reason": "",
        "additionalOptions": 0,
        "level": "partition",
        "schedule": "",
        "scheduleFactor": 1,
        "start": 20160120,
        "finish": 20160120,
        "useCache": 0,
        "cacheTime": 0
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


# Get Decisions

Query a Decision's resource. A decisions resource represents the schedule and rules for a check done on Transactions.

```php
function getDecisions(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): DecisionsResponseResult
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

[`DecisionsResponseResult`](../../doc/models/decisions-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $decisionsController->getDecisions(
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
        "id": "t1_dcs_67ddb8ad653487caf88cc00",
        "created": "2025-03-21 15:06:21.4313",
        "modified": "2025-03-21 15:06:21.4313",
        "creator": "t1_log_61e72ab44fd39df9483aa2c",
        "modifier": "t1_log_61e72ab44fd39df9483aa2c",
        "login": "t1_log_61e72ab44fd39df9483aa2c",
        "org": "t1_org_5fada4629c317f80bc9cb12",
        "entity": "",
        "decision": "",
        "type": "cvv",
        "target": "postauth",
        "action": 1,
        "sequence": 0,
        "amount": 0,
        "value": "1",
        "period": "days",
        "periodFactor": 1,
        "low": 1,
        "high": 2,
        "inactive": 0,
        "frozen": 0,
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_000111d4d504f21414978f0",
        "application": "txn",
        "options": 0,
        "errorMessage": "Unable to accept without CVV.",
        "reason": "",
        "additionalOptions": 0,
        "level": "partition",
        "schedule": "",
        "scheduleFactor": 1,
        "start": 20160120,
        "finish": 20160120,
        "useCache": 0,
        "cacheTime": 0
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


# Post Decisions

Create a Decisions resource that represents the schedule and rules for a check done on Transactions.

```php
function postDecisions(
    DecisionsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): DecisionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`DecisionsPostRequest`](../../doc/models/decisions-post-request.md) | Body, Required | Create Decision Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`DecisionsResponseResult`](../../doc/models/decisions-response-result.md)

## Example Usage

```php
$body = DecisionsPostRequestBuilder::init(
    't1_log_61e72ab44fd39df9483aa2c',
    DecisionActionsApplicationEnum::TXN,
    'partition',
    DecisionTypeEnum::CVV,
    DecisionsTargetEnum::POSTAUTH,
    DescisionActionEnum::BLOCK,
    '1',
    DecisionsPeriodEnum::DAYS,
    20160120
)
    ->org(
        't1_org_5fada4629c317f80bc9cb12'
    )
    ->entity('t1_ent_67d86dfd3442f3e2927ecbd')
    ->decision('t1_dcs_6789a1b36647513d66cf30a')
    ->division('t1_div_67c56806728fbbf0bae0b00')
    ->partition('t1_ptn_000111d4d504f21414978f0')
    ->sequence(0)
    ->amount(1)
    ->periodFactor(1)
    ->scheduleFactor(1)
    ->finish(20160120)
    ->low(1)
    ->high(2)
    ->useCache(DecisionsUseCacheEnum::DISABLED)
    ->cacheTime(0)
    ->options(0)
    ->additionalOptions(0)
    ->errorMessage('Unable to accept without CVV')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $decisionsController->postDecisions(
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
        "id": "t1_dcs_67ddb8ad653487caf88cc00",
        "created": "2025-03-21 15:06:21.4313",
        "modified": "2025-03-21 15:06:21.4313",
        "creator": "t1_log_61e72ab44fd39df9483aa2c",
        "modifier": "t1_log_61e72ab44fd39df9483aa2c",
        "login": "t1_log_61e72ab44fd39df9483aa2c",
        "org": "t1_org_5fada4629c317f80bc9cb12",
        "entity": "",
        "decision": "",
        "type": "cvv",
        "target": "postauth",
        "action": 1,
        "sequence": 0,
        "amount": 0,
        "value": "1",
        "period": "days",
        "periodFactor": 1,
        "low": 1,
        "high": 2,
        "inactive": 0,
        "frozen": 0,
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_000111d4d504f21414978f0",
        "application": "txn",
        "options": 0,
        "errorMessage": "Unable to accept without CVV.",
        "reason": "",
        "additionalOptions": 0,
        "level": "partition",
        "schedule": "",
        "scheduleFactor": 1,
        "start": 20160120,
        "finish": 20160120,
        "useCache": 0,
        "cacheTime": 0
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

