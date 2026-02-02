# Alerts

Web alerts, also known as webhooks, are automated notifications sent from the API server when triggered by a specific action that occurs in your portfolio. You can configure the actions that trigger the alerts to notify you of any event that's important to your business model.

```php
$alertsController = $client->getAlertsController();
```

## Class Name

`AlertsController`

## Methods

* [Get Alerts Id](../../doc/controllers/alerts.md#get-alerts-id)
* [Put Alerts Id](../../doc/controllers/alerts.md#put-alerts-id)
* [Delete Alerts Id](../../doc/controllers/alerts.md#delete-alerts-id)
* [Get Alerts](../../doc/controllers/alerts.md#get-alerts)
* [Post Alerts](../../doc/controllers/alerts.md#post-alerts)


# Get Alerts Id

Query an Alert resource, which represents a particular event notification delivered to a user, and you can invoke alerts by setting up triggers in an alertTriggers resource.

```php
function getAlertsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): AlertsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this alert. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`AlertsResponseResult`](../../doc/models/alerts-response-result.md)

## Example Usage

```php
$id = 't1_alt_67d1a66d3af03677cdc7db0';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $alertsController->getAlertsId(
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
        "id": "t1_alt_67d1a66d3af03677cdc7db0",
        "created": "2025-03-12 11:21:17.2576",
        "modified": "2025-03-12 11:21:28.4944",
        "creator": "t1_log_61f2efc258eb7bf6d380000",
        "modifier": "t1_log_61f2efc258eb7bf6d380000",
        "login": "t1_log_61f2efc258eb7bf6d380000",
        "forlogin": "t1_log_61f2efc258eb7bf6d380000",
        "team": "t1_tem_67c202b908935b505104500",
        "name": "williamson",
        "description": "Used by the FrontDesk system to keep information up to date via webhook alerts",
        "inactive": 0,
        "frozen": 0,
        "division": "t1_div_67c56806728fbbf0bae0z00",
        "partition": "t1_ptn_666834d4d504f21414978f0"
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


# Put Alerts Id

Update an Alert resource, which represents a particular event notification delivered to a user, and you can invoke alerts by setting up triggers in an alertTriggers resource.

```php
function putAlertsId(
    string $id,
    AlertsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): AlertsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this alert. |
| `body` | [`AlertsPutRequest`](../../doc/models/alerts-put-request.md) | Body, Required | Update Alert Configuration Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`AlertsResponseResult`](../../doc/models/alerts-response-result.md)

## Example Usage

```php
$id = 't1_alt_67d1a66d3af03677cdc7db0';

$body = AlertsPutRequestBuilder::init()
    ->login('t1_log_61f2efc258eb7bf6d380000')
    ->forlogin('t1_log_61f2efc258eb7bf6d380000')
    ->team('t1_tem_67c202b908935b505104500')
    ->division('t1_div_67c56806728fbbf0bae0z00')
    ->partition('t1_ptn_666834d4d504f21414978f0')
    ->name('williamson')
    ->description('Used by the FrontDesk system to keep information up to date via webhook alerts')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $alertsController->putAlertsId(
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
        "id": "t1_alt_67d1a66d3af03677cdc7db0",
        "created": "2025-03-12 11:21:17.2576",
        "modified": "2025-03-12 11:21:28.4944",
        "creator": "t1_log_61f2efc258eb7bf6d380000",
        "modifier": "t1_log_61f2efc258eb7bf6d380000",
        "login": "t1_log_61f2efc258eb7bf6d380000",
        "forlogin": "t1_log_61f2efc258eb7bf6d380000",
        "team": "t1_tem_67c202b908935b505104500",
        "name": "williamson",
        "description": "Used by the FrontDesk system to keep information up to date via webhook alerts",
        "inactive": 0,
        "frozen": 0,
        "division": "t1_div_67c56806728fbbf0bae0z00",
        "partition": "t1_ptn_666834d4d504f21414978f0"
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


# Delete Alerts Id

Delete an Alert resource, which represents a particular event notification delivered to a user, and you can invoke alerts by setting up triggers in an alertTriggers resource.

```php
function deleteAlertsId(string $id, ?string $token = null, ?string $requestToken = null): AlertsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this alert. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`AlertsResponseResult`](../../doc/models/alerts-response-result.md)

## Example Usage

```php
$id = 't1_alt_67d1a66d3af03677cdc7db0';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $alertsController->deleteAlertsId(
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
        "id": "t1_alt_67d1a66d3af03677cdc7db0",
        "created": "2025-03-12 11:21:17.2576",
        "modified": "2025-03-12 11:21:28.4944",
        "creator": "t1_log_61f2efc258eb7bf6d380000",
        "modifier": "t1_log_61f2efc258eb7bf6d380000",
        "login": "t1_log_61f2efc258eb7bf6d380000",
        "forlogin": "t1_log_61f2efc258eb7bf6d380000",
        "team": "t1_tem_67c202b908935b505104500",
        "name": "williamson",
        "description": "Used by the FrontDesk system to keep information up to date via webhook alerts",
        "inactive": 0,
        "frozen": 0,
        "division": "t1_div_67c56806728fbbf0bae0z00",
        "partition": "t1_ptn_666834d4d504f21414978f0"
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


# Get Alerts

Query an Alert resource, which represents a particular event notification delivered to a user; you can invoke alerts by setting up triggers in an alertTriggers resource.

```php
function getAlerts(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): AlertsResponseResult
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

[`AlertsResponseResult`](../../doc/models/alerts-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $alertsController->getAlerts(
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
        "id": "t1_alt_67d1a66d3af03677cdc7db0",
        "created": "2025-03-12 11:21:17.2576",
        "modified": "2025-03-12 11:21:28.4944",
        "creator": "t1_log_61f2efc258eb7bf6d380000",
        "modifier": "t1_log_61f2efc258eb7bf6d380000",
        "login": "t1_log_61f2efc258eb7bf6d380000",
        "forlogin": "t1_log_61f2efc258eb7bf6d380000",
        "team": "t1_tem_67c202b908935b505104500",
        "name": "williamson",
        "description": "Used by the FrontDesk system to keep information up to date via webhook alerts",
        "inactive": 0,
        "frozen": 0,
        "division": "t1_div_67c56806728fbbf0bae0z00",
        "partition": "t1_ptn_666834d4d504f21414978f0"
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


# Post Alerts

Create an Alert resource, which represents a particular event notification delivered to a user. You can invoke alerts by setting up triggers in an [AlertTriggers](../../doc/controllers/alert-triggers.md#post-alert-triggers) resource and specify the delivery method through an alertActions resource. [Alert Actions]($h/Alert%20Actions/_overview) represent particular instances of an Alert sent out through specific channels, such as SMS, mobile application notifications, or email. Each Alert Action is associated with an Alert resource.

```php
function postAlerts(
    AlertsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): AlertsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`AlertsPostRequest`](../../doc/models/alerts-post-request.md) | Body, Required | Create Alert Configuration Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`AlertsResponseResult`](../../doc/models/alerts-response-result.md)

## Example Usage

```php
$body = AlertsPostRequestBuilder::init(
    't1_log_61f2efc258eb7bf6d380000'
)
    ->forlogin('t1_log_61f2efc258eb7bf6d380000')
    ->team(
        't1_tem_67c202b908935b505104500'
    )
    ->division('t1_div_67c56806728fbbf0bae0z00')
    ->partition('t1_ptn_666834d4d504f21414978f0')
    ->name('williamson')
    ->description('Used by the FrontDesk system to keep information up to date via webhook alerts')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $alertsController->postAlerts(
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
        "id": "t1_alt_67d1a66d3af03677cdc7db0",
        "created": "2025-03-12 11:21:17.2576",
        "modified": "2025-03-12 11:21:28.4944",
        "creator": "t1_log_61f2efc258eb7bf6d380000",
        "modifier": "t1_log_61f2efc258eb7bf6d380000",
        "login": "t1_log_61f2efc258eb7bf6d380000",
        "forlogin": "t1_log_61f2efc258eb7bf6d380000",
        "team": "t1_tem_67c202b908935b505104500",
        "name": "williamson",
        "description": "Used by the FrontDesk system to keep information up to date via webhook alerts",
        "inactive": 0,
        "frozen": 0,
        "division": "t1_div_67c56806728fbbf0bae0z00",
        "partition": "t1_ptn_666834d4d504f21414978f0"
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

