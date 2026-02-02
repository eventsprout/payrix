# Alert Triggers

```php
$alertTriggersController = $client->getAlertTriggersController();
```

## Class Name

`AlertTriggersController`

## Methods

* [Get Alert Triggers Id](../../doc/controllers/alert-triggers.md#get-alert-triggers-id)
* [Put Alert Triggers Id](../../doc/controllers/alert-triggers.md#put-alert-triggers-id)
* [Delete Alert Triggers Id](../../doc/controllers/alert-triggers.md#delete-alert-triggers-id)
* [Get Alert Triggers](../../doc/controllers/alert-triggers.md#get-alert-triggers)
* [Post Alert Triggers](../../doc/controllers/alert-triggers.md#post-alert-triggers)


# Get Alert Triggers Id

Query an alertTrigger resource that represents a set of triggers causing an Alert to be sent, for example, the levying of a Fee or a Payout occurring, each linked to a particular Alert, with the action to take when triggered set up in the alertActions resource.

```php
function getAlertTriggersId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): AlertTriggersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this alert trigger. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`AlertTriggersResponseResult`](../../doc/models/alert-triggers-response-result.md)

## Example Usage

```php
$id = 't1_alr_67d489a76383d013e6295c0';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $alertTriggersController->getAlertTriggersId(
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
        "id": "t1_alr_67d489a76383d013e6295c0",
        "created": "2025-03-14 15:55:19.4151",
        "modified": "2025-03-14 15:55:19.4151",
        "creator": "t1_log_66b14333927997a2f3cf7b2",
        "modifier": "t1_log_66b14333927997a2f3cf7b2",
        "alert": "t1_alt_67d489a72e5e8fdec85a910",
        "event": "delete",
        "resource": 9,
        "name": "name of alertTrigger",
        "description": "description of alertTrigger",
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


# Put Alert Triggers Id

Update an alertTrigger resource that represents a set of triggers causing an Alert to be sent, for example levying a Fee or a Payout occurring, with each trigger linked to a particular Alert and the action taken when triggered set up in the alertActions resource.

```php
function putAlertTriggersId(
    string $id,
    AlertTriggersPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): AlertTriggersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this alert trigger. |
| `body` | [`AlertTriggersPutRequest`](../../doc/models/alert-triggers-put-request.md) | Body, Required | Update Alert Trigger Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`AlertTriggersResponseResult`](../../doc/models/alert-triggers-response-result.md)

## Example Usage

```php
$id = 't1_alr_67d489a76383d013e6295c0';

$body = AlertTriggersPutRequestBuilder::init()
    ->alert('t1_alt_67d489a72e5e8fdec85a910')
    ->event(AlertTriggerEventEnum::DELETE)
    ->resource(ResourceEnum::MERCHANTS)
    ->name('name of alertTrigger')
    ->description('description of alertTrigger')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $alertTriggersController->putAlertTriggersId(
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
        "id": "t1_alr_67d489a76383d013e6295c0",
        "created": "2025-03-14 15:55:19.4151",
        "modified": "2025-03-14 15:55:19.4151",
        "creator": "t1_log_66b14333927997a2f3cf7b2",
        "modifier": "t1_log_66b14333927997a2f3cf7b2",
        "alert": "t1_alt_67d489a72e5e8fdec85a910",
        "event": "delete",
        "resource": 9,
        "name": "name of alertTrigger",
        "description": "description of alertTrigger",
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


# Delete Alert Triggers Id

Delete an alertTrigger resource that represents a set of triggers causing an Alert to be sent, for example levying a Fee or a Payout occurring, each linked to a particular Alert with the action to take set up in the alertActions resource.

```php
function deleteAlertTriggersId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): AlertTriggersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this alert trigger. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`AlertTriggersResponseResult`](../../doc/models/alert-triggers-response-result.md)

## Example Usage

```php
$id = 't1_alr_67d489a76383d013e6295c0';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $alertTriggersController->deleteAlertTriggersId(
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
        "id": "t1_alr_67d489a76383d013e6295c0",
        "created": "2025-03-14 15:55:19.4151",
        "modified": "2025-03-14 15:55:19.4151",
        "creator": "t1_log_66b14333927997a2f3cf7b2",
        "modifier": "t1_log_66b14333927997a2f3cf7b2",
        "alert": "t1_alt_67d489a72e5e8fdec85a910",
        "event": "delete",
        "resource": 9,
        "name": "name of alertTrigger",
        "description": "description of alertTrigger",
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


# Get Alert Triggers

Query an alertTrigger resource that represents a set of triggers that cause an Alert to be sent, where for example this could be the levying of a Fee or a Payout occurring, and each alertTrigger is linked to a particular Alert, with the action to take when an Alert is triggered set up in the alertActions resource.

```php
function getAlertTriggers(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): AlertTriggersResponseResult
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

[`AlertTriggersResponseResult`](../../doc/models/alert-triggers-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $alertTriggersController->getAlertTriggers(
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
        "id": "t1_alr_67d489a76383d013e6295c0",
        "created": "2025-03-14 15:55:19.4151",
        "modified": "2025-03-14 15:55:19.4151",
        "creator": "t1_log_66b14333927997a2f3cf7b2",
        "modifier": "t1_log_66b14333927997a2f3cf7b2",
        "alert": "t1_alt_67d489a72e5e8fdec85a910",
        "event": "delete",
        "resource": 9,
        "name": "name of alertTrigger",
        "description": "description of alertTrigger",
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


# Post Alert Triggers

Create an alertTrigger resource that represents a set of triggers causing an Alert to be sent, such as the levying of a Fee or a Payout occurring, and each alertTrigger is linked to a particular Alert with actions set up in the alertActions resource.

```php
function postAlertTriggers(
    AlertTriggersPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): AlertTriggersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`AlertTriggersPostRequest`](../../doc/models/alert-triggers-post-request.md) | Body, Required | Create Alert Trigger Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`AlertTriggersResponseResult`](../../doc/models/alert-triggers-response-result.md)

## Example Usage

```php
$body = AlertTriggersPostRequestBuilder::init(
    't1_alt_67d489a72e5e8fdec85a910',
    AlertTriggerEventEnum::DELETE,
    ResourceEnum::MERCHANTS
)
    ->name('name of alertTrigger')
    ->description('description of alertTrigger')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $alertTriggersController->postAlertTriggers(
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
        "id": "t1_alr_67d489a76383d013e6295c0",
        "created": "2025-03-14 15:55:19.4151",
        "modified": "2025-03-14 15:55:19.4151",
        "creator": "t1_log_66b14333927997a2f3cf7b2",
        "modifier": "t1_log_66b14333927997a2f3cf7b2",
        "alert": "t1_alt_67d489a72e5e8fdec85a910",
        "event": "delete",
        "resource": 9,
        "name": "name of alertTrigger",
        "description": "description of alertTrigger",
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

