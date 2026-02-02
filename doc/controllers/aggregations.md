# Aggregations

Aggregations acts as a scheduler that contains the needed parameters to properly generate results containing the calculated totals and keep such records in the aggregation results resource.

```php
$aggregationsController = $client->getAggregationsController();
```

## Class Name

`AggregationsController`

## Methods

* [Get Aggregations Id](../../doc/controllers/aggregations.md#get-aggregations-id)
* [Put Aggregations Id](../../doc/controllers/aggregations.md#put-aggregations-id)
* [Delete Aggregations Id](../../doc/controllers/aggregations.md#delete-aggregations-id)
* [Get Aggregations](../../doc/controllers/aggregations.md#get-aggregations)
* [Post Aggregations](../../doc/controllers/aggregations.md#post-aggregations)


# Get Aggregations Id

Query an Aggregation resource that uses a search to query for records on the given resource and applies the desired calculations (count, sum, min, and/or max) to the field in question.

```php
function getAggregationsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null,
    ?string $searchFilter = null
): AggregationsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource or The Aggregation ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |
| `searchFilter` | `?string` | Header, Optional | Set this header to filter or sort the list of resources that the method returns.<br>For example, to find all resources that have a property of 'public' set to '1', set this header to 'public[equals]=1'. You can use the operators 'equals', 'greater', 'less', 'like', 'in' and 'sort'. To sort the resources, use the keywords 'asc' (for an ascending sort) or 'desc' (for a descending sort).<br>You may also use explicit 'and/or' querying by passing arrays of or and arrays of and parameters. For example, to find all resources that have a property of 'public' set to '1' or a property of 'active' set to '0', set this header to 'or[][public][equals]=1&or[][active][equals]=0'. |

## Response Type

[`AggregationsResponseResult`](../../doc/models/aggregations-response-result.md)

## Example Usage

```php
$id = 't1_agg_67b339d00940f0d12b000b7';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$searchFilter = 'created[equals]=2025-01-01';

$result = $aggregationsController->getAggregationsId(
    $id,
    $token,
    $requestToken,
    null,
    $searchFilter
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_agg_67b339d00940f0d12b000b7",
        "created": "2025-02-17 08:30:00.5718",
        "modified": "2025-02-17 08:30:00.5718",
        "creator": "t1_log_6279a44f109090941bbc4c0",
        "modifier": "t1_log_6279a44f109090941bbc4c0",
        "login": "t1_log_67b339d2dc878984b96b225",
        "name": "Default merchantTxnFailedAll",
        "description": "Automatically created aggregation",
        "resource": 18,
        "search": "status[equals]=2",
        "totals": "sum[0]=total&count[0]=id&groups[0]=merchant&groups[1]=type&groups[2][payment][0]=method",
        "status": "ready",
        "schedule": "days",
        "scheduleFactor": 1,
        "start": 202502180000,
        "inactive": 0,
        "frozen": 0,
        "entity": "t1_ent_676057654c1b7452e4884f0",
        "forlogin": "t1_log_67b339d2dc878984b96b225",
        "org": "t1_org_67b736ad7d05922343246cf",
        "team": "teamBoarding",
        "division": "t1_div_67b51635da21f7399ce2af1",
        "partition": "t1_ptn_666834d4d504f11234578f5",
        "type": "merchantTxnFailedAll",
        "level": "merchant",
        "default": 1,
        "degrouping": "groups[0]=merchant&groups[1][payment][0]=method"
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


# Put Aggregations Id

Update an Aggregation resource or Update an Aggregation.

```php
function putAggregationsId(
    string $id,
    AggregationsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $searchFilter = null
): AggregationsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource or The Aggregation ID. |
| `body` | [`AggregationsPutRequest`](../../doc/models/aggregations-put-request.md) | Body, Required | Update Aggregation Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `searchFilter` | `?string` | Header, Optional | Set this header to filter or sort the list of resources that the method returns.<br>For example, to find all resources that have a property of 'public' set to '1', set this header to 'public[equals]=1'. You can use the operators 'equals', 'greater', 'less', 'like', 'in' and 'sort'. To sort the resources, use the keywords 'asc' (for an ascending sort) or 'desc' (for a descending sort).<br>You may also use explicit 'and/or' querying by passing arrays of or and arrays of and parameters. For example, to find all resources that have a property of 'public' set to '1' or a property of 'active' set to '0', set this header to 'or[][public][equals]=1&or[][active][equals]=0'. |

## Response Type

[`AggregationsResponseResult`](../../doc/models/aggregations-response-result.md)

## Example Usage

```php
$id = 't1_agg_67b339d00940f0d12b000b7';

$body = AggregationsPutRequestBuilder::init()
    ->login('t1_log_67b5002a5de3b716ad97e07')
    ->entity('t1_ent_676057654c1b7452e4884f0')
    ->forlogin('t1_log_67b5002a5de3b716ad97e07')
    ->org('t1_org_67b736ad7d05922343246cf')
    ->team('teamBoarding')
    ->division('t1_div_67b51635da21f7399ce2af1')
    ->partition('t1_ptn_666834d4d504f11234578f5')
    ->type(AggregationTypeEnum::MERCHANTTXNFAILEDALL)
    ->level(AggregationsLevelEnum::MERCHANT)
    ->name('Default merchantTxnFailedAll')
    ->description('Automatically created aggregation')
    ->resource(ResourceEnum::TXNS)
    ->search('status[equals]=2&created[like]={{"expand": [{"type": "date","value": "-1 days","format": "Y-m-d","relativeTimestamp":":effective:"}]}}%')
    ->totals('sum[0]=total&count[0]=id&groups[0]=merchant&groups[1]=type&groups[2][payment][0]=method')
    ->degrouping('groups[0]=merchant&groups[1][payment][0]=method')
    ->status(AggregationStatusEnum::READY)
    ->schedule(AggregationScheduleEnum::DAYS)
    ->scheduleFactor(1)
    ->start(202502200000)
    ->default(AggregationDefaultEnum::AUTOMATICALLYCREATED)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$searchFilter = 'created[equals]=2025-01-01';

$result = $aggregationsController->putAggregationsId(
    $id,
    $body,
    $token,
    $requestToken,
    $searchFilter
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_agg_67b339d00940f0d12b000b7",
        "created": "2025-02-17 08:30:00.5718",
        "modified": "2025-02-17 08:30:00.5718",
        "creator": "t1_log_6279a44f109090941bbc4c0",
        "modifier": "t1_log_6279a44f109090941bbc4c0",
        "login": "t1_log_67b339d2dc878984b96b225",
        "name": "Default merchantTxnFailedAll",
        "description": "Automatically created aggregation",
        "resource": 18,
        "search": "status[equals]=2",
        "totals": "sum[0]=total&count[0]=id&groups[0]=merchant&groups[1]=type&groups[2][payment][0]=method",
        "status": "ready",
        "schedule": "days",
        "scheduleFactor": 1,
        "start": 202502180000,
        "inactive": 0,
        "frozen": 0,
        "entity": "t1_ent_676057654c1b7452e4884f0",
        "forlogin": "t1_log_67b339d2dc878984b96b225",
        "org": "t1_org_67b736ad7d05922343246cf",
        "team": "teamBoarding",
        "division": "t1_div_67b51635da21f7399ce2af1",
        "partition": "t1_ptn_666834d4d504f11234578f5",
        "type": "merchantTxnFailedAll",
        "level": "merchant",
        "default": 1,
        "degrouping": "groups[0]=merchant&groups[1][payment][0]=method"
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


# Delete Aggregations Id

Delete an Aggregation resource or an Aggregation.

```php
function deleteAggregationsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $searchFilter = null
): AggregationsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource or The Aggregation ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `searchFilter` | `?string` | Header, Optional | Set this header to filter or sort the list of resources that the method returns.<br>For example, to find all resources that have a property of 'public' set to '1', set this header to 'public[equals]=1'. You can use the operators 'equals', 'greater', 'less', 'like', 'in' and 'sort'. To sort the resources, use the keywords 'asc' (for an ascending sort) or 'desc' (for a descending sort).<br>You may also use explicit 'and/or' querying by passing arrays of or and arrays of and parameters. For example, to find all resources that have a property of 'public' set to '1' or a property of 'active' set to '0', set this header to 'or[][public][equals]=1&or[][active][equals]=0'. |

## Response Type

[`AggregationsResponseResult`](../../doc/models/aggregations-response-result.md)

## Example Usage

```php
$id = 't1_agg_67b339d00940f0d12b000b7';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$searchFilter = 'created[equals]=2025-01-01';

$result = $aggregationsController->deleteAggregationsId(
    $id,
    $token,
    $requestToken,
    $searchFilter
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_agg_67b339d00940f0d12b000b7",
        "created": "2025-02-17 08:30:00.5718",
        "modified": "2025-02-17 08:30:00.5718",
        "creator": "t1_log_6279a44f109090941bbc4c0",
        "modifier": "t1_log_6279a44f109090941bbc4c0",
        "login": "t1_log_67b339d2dc878984b96b225",
        "name": "Default merchantTxnFailedAll",
        "description": "Automatically created aggregation",
        "resource": 18,
        "search": "status[equals]=2",
        "totals": "sum[0]=total&count[0]=id&groups[0]=merchant&groups[1]=type&groups[2][payment][0]=method",
        "status": "ready",
        "schedule": "days",
        "scheduleFactor": 1,
        "start": 202502180000,
        "inactive": 0,
        "frozen": 0,
        "entity": "t1_ent_676057654c1b7452e4884f0",
        "forlogin": "t1_log_67b339d2dc878984b96b225",
        "org": "t1_org_67b736ad7d05922343246cf",
        "team": "teamBoarding",
        "division": "t1_div_67b51635da21f7399ce2af1",
        "partition": "t1_ptn_666834d4d504f11234578f5",
        "type": "merchantTxnFailedAll",
        "level": "merchant",
        "default": 1,
        "degrouping": "groups[0]=merchant&groups[1][payment][0]=method"
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


# Get Aggregations

Query an Aggregation resource using the search to query for records on the given resource and apply desired calculations (count, sum, min, and/or max) to the specified field.

```php
function getAggregations(
    ?string $token = null,
    ?string $requestToken = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null,
    ?string $searchFilter = null
): AggregationsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `pageNumber` | `?int` | Query, Optional | Set this path parameter to request a specific page of records.<br>For example, set `?page[number]=2` to retrieve the second page of records for this request. |
| `pageLimit` | `?int` | Query, Optional | Set this path parameter to request up to a specific amount of records. By default 30 records are retrieved per page. The maximum limit that can be set is 100.<br>For example, set `?page[limit]=50` to retrieve up to 50 records for this request. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |
| `searchFilter` | `?string` | Header, Optional | Set this header to filter or sort the list of resources that the method returns.<br>For example, to find all resources that have a property of 'public' set to '1', set this header to 'public[equals]=1'. You can use the operators 'equals', 'greater', 'less', 'like', 'in' and 'sort'. To sort the resources, use the keywords 'asc' (for an ascending sort) or 'desc' (for a descending sort).<br>You may also use explicit 'and/or' querying by passing arrays of or and arrays of and parameters. For example, to find all resources that have a property of 'public' set to '1' or a property of 'active' set to '0', set this header to 'or[][public][equals]=1&or[][active][equals]=0'. |

## Response Type

[`AggregationsResponseResult`](../../doc/models/aggregations-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$searchFilter = 'created[greater]=2024-01-01';

$result = $aggregationsController->getAggregations(
    $token,
    $requestToken,
    $pageNumber,
    $pageLimit,
    null,
    $searchFilter
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_agg_67b339d00940f0d12b000b7",
        "created": "2025-02-17 08:30:00.5718",
        "modified": "2025-02-17 08:30:00.5718",
        "creator": "t1_log_6279a44f109090941bbc4c0",
        "modifier": "t1_log_6279a44f109090941bbc4c0",
        "login": "t1_log_67b339d2dc878984b96b225",
        "name": "Default merchantTxnFailedAll",
        "description": "Automatically created aggregation",
        "resource": 18,
        "search": "status[equals]=2",
        "totals": "sum[0]=total&count[0]=id&groups[0]=merchant&groups[1]=type&groups[2][payment][0]=method",
        "status": "ready",
        "schedule": "days",
        "scheduleFactor": 1,
        "start": 202502180000,
        "inactive": 0,
        "frozen": 0,
        "entity": "t1_ent_676057654c1b7452e4884f0",
        "forlogin": "t1_log_67b339d2dc878984b96b225",
        "org": "t1_org_67b736ad7d05922343246cf",
        "team": "teamBoarding",
        "division": "t1_div_67b51635da21f7399ce2af1",
        "partition": "t1_ptn_666834d4d504f11234578f5",
        "type": "merchantTxnFailedAll",
        "level": "merchant",
        "default": 1,
        "degrouping": "groups[0]=merchant&groups[1][payment][0]=method"
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


# Post Aggregations

Create an Aggregation resource that uses the search to query for records on a given resource and applies the desired calculations (count, sum, min, and/or max) to the field in question.

```php
function postAggregations(
    AggregationsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): AggregationsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`AggregationsPostRequest`](../../doc/models/aggregations-post-request.md) | Body, Required | Create Aggregation Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`AggregationsResponseResult`](../../doc/models/aggregations-response-result.md)

## Example Usage

```php
$body = AggregationsPostRequestBuilder::init(
    't1_log_67b5002a5de3b716ad97e07',
    ResourceEnum::TXNS,
    'sum[0]=total&count[0]=id&groups[0]=merchant&groups[1]=type&groups[2][payment][0]=method',
    AggregationScheduleEnum::DAYS,
    202502200000
)
    ->entity('t1_ent_676057654c1b7452e4884f0')
    ->forlogin('t1_log_67b5002a5de3b716ad97e07')
    ->org('t1_org_67b736ad7d05922343246cf')
    ->team('teamBoarding')
    ->division('t1_div_67b51635da21f7399ce2af1')
    ->partition('t1_ptn_666834d4d504f11234578f5')
    ->type(AggregationTypeEnum::MERCHANTTXNFAILEDALL)
    ->level(AggregationsLevelEnum::MERCHANT)
    ->name('Default merchantTxnFailedAll')
    ->description('Automatically created aggregation')
    ->search('status[equals]=2&created[like]={{"expand": [{"type": "date","value": "-1 days","format": "Y-m-d","relativeTimestamp":":effective:"}]}}%')
    ->degrouping('groups[0]=merchant&groups[1][payment][0]=method')
    ->status(AggregationStatusEnum::READY)
    ->scheduleFactor(1)
    ->default(AggregationDefaultEnum::AUTOMATICALLYCREATED)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $aggregationsController->postAggregations(
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
        "id": "t1_agg_67b339d00940f0d12b000b7",
        "created": "2025-02-17 08:30:00.5718",
        "modified": "2025-02-17 08:30:00.5718",
        "creator": "t1_log_6279a44f109090941bbc4c0",
        "modifier": "t1_log_6279a44f109090941bbc4c0",
        "login": "t1_log_67b339d2dc878984b96b225",
        "name": "Default merchantTxnFailedAll",
        "description": "Automatically created aggregation",
        "resource": 18,
        "search": "status[equals]=2",
        "totals": "sum[0]=total&count[0]=id&groups[0]=merchant&groups[1]=type&groups[2][payment][0]=method",
        "status": "ready",
        "schedule": "days",
        "scheduleFactor": 1,
        "start": 202502180000,
        "inactive": 0,
        "frozen": 0,
        "entity": "t1_ent_676057654c1b7452e4884f0",
        "forlogin": "t1_log_67b339d2dc878984b96b225",
        "org": "t1_org_67b736ad7d05922343246cf",
        "team": "teamBoarding",
        "division": "t1_div_67b51635da21f7399ce2af1",
        "partition": "t1_ptn_666834d4d504f11234578f5",
        "type": "merchantTxnFailedAll",
        "level": "merchant",
        "default": 1,
        "degrouping": "groups[0]=merchant&groups[1][payment][0]=method"
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

