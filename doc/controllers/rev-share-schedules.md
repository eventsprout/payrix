# Rev Share Schedules

```php
$revShareSchedulesController = $client->getRevShareSchedulesController();
```

## Class Name

`RevShareSchedulesController`

## Methods

* [Get Rev Share Schedules Id](../../doc/controllers/rev-share-schedules.md#get-rev-share-schedules-id)
* [Put Rev Share Schedules Id](../../doc/controllers/rev-share-schedules.md#put-rev-share-schedules-id)
* [Delete Rev Share Schedules Id](../../doc/controllers/rev-share-schedules.md#delete-rev-share-schedules-id)
* [Get Rev Share Schedules](../../doc/controllers/rev-share-schedules.md#get-rev-share-schedules)
* [Post Rev Share Schedules](../../doc/controllers/rev-share-schedules.md#post-rev-share-schedules)


# Get Rev Share Schedules Id

Query a revShareSchedule.

```php
function getRevShareSchedulesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): RevShareSchedulesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`RevShareSchedulesResponseResult`](../../doc/models/rev-share-schedules-response-result.md)

## Example Usage

```php
$id = 't1_rsc_6800f8590a3fc6c0caed9zz';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $revShareSchedulesController->getRevShareSchedulesId(
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
        "id": "t1_rsc_6800f8590a3fc6c0caed9zz",
        "created": "2025-04-17 08:47:21.0625",
        "modified": "2025-04-17 08:47:21.0625",
        "creator": "t1_log_670d8844ef246e80758e762",
        "modifier": "t1_log_670d8844ef246e80758e762",
        "entity": "g157715bca1f55c",
        "forentity": "t1_ent_67c96d183e9b9aa6c6f190c",
        "start": "2025-04-17 18:17:20",
        "end": "2025-04-17 18:17:20",
        "share": 2000,
        "event": 84,
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


# Put Rev Share Schedules Id

Update a revShareSchedule.

```php
function putRevShareSchedulesId(
    string $id,
    RevShareSchedulesPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): RevShareSchedulesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `body` | [`RevShareSchedulesPutRequest`](../../doc/models/rev-share-schedules-put-request.md) | Body, Required | - |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`RevShareSchedulesResponseResult`](../../doc/models/rev-share-schedules-response-result.md)

## Example Usage

```php
$id = 't1_rsc_6800f8590a3fc6c0caed9zz';

$body = RevShareSchedulesPutRequestBuilder::init()
    ->entity('t1_ent_5f9058fe8c8d21ead8f68dc')
    ->forentity('t1_ent_67c96d183e9b9aa6c6f190c')
    ->start('2025-04-17 18:17:20')
    ->end('2025-04-17 18:17:20')
    ->share(2000)
    ->event(RevShareScheduleEventEnum::REVSHARECARD)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $revShareSchedulesController->putRevShareSchedulesId(
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
        "id": "t1_rsc_6800f8590a3fc6c0caed9zz",
        "created": "2025-04-17 08:47:21.0625",
        "modified": "2025-04-17 08:47:21.0625",
        "creator": "t1_log_670d8844ef246e80758e762",
        "modifier": "t1_log_670d8844ef246e80758e762",
        "entity": "g157715bca1f55c",
        "forentity": "t1_ent_67c96d183e9b9aa6c6f190c",
        "start": "2025-04-17 18:17:20",
        "end": "2025-04-17 18:17:20",
        "share": 2000,
        "event": 84,
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


# Delete Rev Share Schedules Id

Delete a revShareSchedule.

```php
function deleteRevShareSchedulesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): RevShareSchedulesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`RevShareSchedulesResponseResult`](../../doc/models/rev-share-schedules-response-result.md)

## Example Usage

```php
$id = 't1_rsc_6800f8590a3fc6c0caed9zz';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $revShareSchedulesController->deleteRevShareSchedulesId(
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
        "id": "t1_rsc_6800f8590a3fc6c0caed9zz",
        "created": "2025-04-17 08:47:21.0625",
        "modified": "2025-04-17 08:47:21.0625",
        "creator": "t1_log_670d8844ef246e80758e762",
        "modifier": "t1_log_670d8844ef246e80758e762",
        "entity": "g157715bca1f55c",
        "forentity": "t1_ent_67c96d183e9b9aa6c6f190c",
        "start": "2025-04-17 18:17:20",
        "end": "2025-04-17 18:17:20",
        "share": 2000,
        "event": 84,
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


# Get Rev Share Schedules

Query revShareSchedules.

```php
function getRevShareSchedules(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): RevShareSchedulesResponseResult
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

[`RevShareSchedulesResponseResult`](../../doc/models/rev-share-schedules-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $revShareSchedulesController->getRevShareSchedules(
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
        "id": "t1_rsc_6800f8590a3fc6c0caed9zz",
        "created": "2025-04-17 08:47:21.0625",
        "modified": "2025-04-17 08:47:21.0625",
        "creator": "t1_log_670d8844ef246e80758e762",
        "modifier": "t1_log_670d8844ef246e80758e762",
        "entity": "g157715bca1f55c",
        "forentity": "t1_ent_67c96d183e9b9aa6c6f190c",
        "start": "2025-04-17 18:17:20",
        "end": "2025-04-17 18:17:20",
        "share": 2000,
        "event": 84,
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


# Post Rev Share Schedules

Create a revShareSchedules.

```php
function postRevShareSchedules(
    RevShareSchedulesPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): RevShareSchedulesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`RevShareSchedulesPostRequest`](../../doc/models/rev-share-schedules-post-request.md) | Body, Required | - |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`RevShareSchedulesResponseResult`](../../doc/models/rev-share-schedules-response-result.md)

## Example Usage

```php
$body = RevShareSchedulesPostRequestBuilder::init(
    't1_ent_5f9058fe8c8d21ead8f68dc',
    't1_ent_67c96d183e9b9aa6c6f190c',
    '2025-04-17 18:17:20',
    2000,
    RevShareScheduleEventEnum::REVSHARECARD
)
    ->end('2025-04-17 18:17:20')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $revShareSchedulesController->postRevShareSchedules(
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
        "id": "t1_rsc_6800f8590a3fc6c0caed9zz",
        "created": "2025-04-17 08:47:21.0625",
        "modified": "2025-04-17 08:47:21.0625",
        "creator": "t1_log_670d8844ef246e80758e762",
        "modifier": "t1_log_670d8844ef246e80758e762",
        "entity": "g157715bca1f55c",
        "forentity": "t1_ent_67c96d183e9b9aa6c6f190c",
        "start": "2025-04-17 18:17:20",
        "end": "2025-04-17 18:17:20",
        "share": 2000,
        "event": 84,
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

