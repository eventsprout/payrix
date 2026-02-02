# Alert Actions

```php
$alertActionsController = $client->getAlertActionsController();
```

## Class Name

`AlertActionsController`

## Methods

* [Get Alert Actions Id](../../doc/controllers/alert-actions.md#get-alert-actions-id)
* [Put Alert Actions Id](../../doc/controllers/alert-actions.md#put-alert-actions-id)
* [Delete Alert Actions Id](../../doc/controllers/alert-actions.md#delete-alert-actions-id)
* [Get Alert Actions](../../doc/controllers/alert-actions.md#get-alert-actions)
* [Post Alert Actions](../../doc/controllers/alert-actions.md#post-alert-actions)


# Get Alert Actions Id

Query an alertAction; An alertAction resource represents a particular instance of an Alert that is sent out through one particular channel, for example, SMS, mobile application notification, or email, each alertAction being associated with an Alert resource.

```php
function getAlertActionsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): AlertActionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Alert Action ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`AlertActionsResponseResult`](../../doc/models/alert-actions-response-result.md)

## Example Usage

```php
$id = 't1_ala_67d0924f1919ec362341d00';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $alertActionsController->getAlertActionsId(
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
        "id": "t1_ala_67d0924f1919ec362341d00",
        "created": "2025-03-11 15:43:11.1194",
        "modified": "2025-03-11 15:43:11.1194",
        "creator": "t1_log_65b2c883d793216616f16ab",
        "modifier": "t1_log_65b2c883d793216616f16ab",
        "type": "web",
        "options": "JSON",
        "value": "https://test.payrix.com/apix/test/t1",
        "alert": "t1_alt_65fddb118236188e055d54c",
        "retries": 3,
        "headerName": "Authorization",
        "headerValue": "SecretToken123!",
        "maxAttemptsTempDisabled": 0,
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


# Put Alert Actions Id

Update an alertAction representing a particular instance of an Alert that is sent out through one particular channel, for example, SMS, mobile application notification, or email, each being associated with an Alert resource.

```php
function putAlertActionsId(
    string $id,
    AlertActionsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): AlertActionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Alert Action ID. |
| `body` | [`AlertActionsPutRequest`](../../doc/models/alert-actions-put-request.md) | Body, Required | Update Alert Action Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`AlertActionsResponseResult`](../../doc/models/alert-actions-response-result.md)

## Example Usage

```php
$id = 't1_ala_67d0924f1919ec362341d00';

$body = AlertActionsPutRequestBuilder::init()
    ->alert('t1_alt_65fddb118236188e055d54c')
    ->headerName('Authorization')
    ->headerValue('SecrtToken1234!')
    ->options('JSON')
    ->value('https://test.payrix.com/apix/test/t1')
    ->retries(3)
    ->maxAttemptsTempDisabled(AlertActionsMaxAttemptsTempDisabledEnum::NOTTEMPORARILYDISABLED)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $alertActionsController->putAlertActionsId(
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
        "id": "t1_ala_67d0924f1919ec362341d00",
        "created": "2025-03-11 15:43:11.1194",
        "modified": "2025-03-11 15:43:11.1194",
        "creator": "t1_log_65b2c883d793216616f16ab",
        "modifier": "t1_log_65b2c883d793216616f16ab",
        "type": "web",
        "options": "JSON",
        "value": "https://test.payrix.com/apix/test/t1",
        "alert": "t1_alt_65fddb118236188e055d54c",
        "retries": 3,
        "headerName": "Authorization",
        "headerValue": "SecretToken123!",
        "maxAttemptsTempDisabled": 0,
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


# Delete Alert Actions Id

Delete an alertAction.

```php
function deleteAlertActionsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): AlertActionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Alert Action ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`AlertActionsResponseResult`](../../doc/models/alert-actions-response-result.md)

## Example Usage

```php
$id = 't1_ala_67d0924f1919ec362341d00';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $alertActionsController->deleteAlertActionsId(
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
        "id": "t1_ala_67d0924f1919ec362341d00",
        "created": "2025-03-11 15:43:11.1194",
        "modified": "2025-03-11 15:43:11.1194",
        "creator": "t1_log_65b2c883d793216616f16ab",
        "modifier": "t1_log_65b2c883d793216616f16ab",
        "type": "web",
        "options": "JSON",
        "value": "https://test.payrix.com/apix/test/t1",
        "alert": "t1_alt_65fddb118236188e055d54c",
        "retries": 3,
        "headerName": "Authorization",
        "headerValue": "SecretToken123!",
        "maxAttemptsTempDisabled": 0,
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


# Get Alert Actions

Query an alertAction representing a particular instance of an Alert that is sent out through one particular channel. For example, SMS, mobile application notification, or email, each being associated with an Alert resource.

```php
function getAlertActions(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): AlertActionsResponseResult
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

[`AlertActionsResponseResult`](../../doc/models/alert-actions-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $alertActionsController->getAlertActions(
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
        "id": "t1_ala_67d0924f1919ec362341d00",
        "created": "2025-03-11 15:43:11.1194",
        "modified": "2025-03-11 15:43:11.1194",
        "creator": "t1_log_65b2c883d793216616f16ab",
        "modifier": "t1_log_65b2c883d793216616f16ab",
        "type": "web",
        "options": "JSON",
        "value": "https://test.payrix.com/apix/test/t1",
        "alert": "t1_alt_65fddb118236188e055d54c",
        "retries": 3,
        "headerName": "Authorization",
        "headerValue": "SecretToken123!",
        "maxAttemptsTempDisabled": 0,
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


# Post Alert Actions

Create an alertAction, which represents a particular instance of an Alert sent out through one particular channel, such as SMS, mobile application notification, or email, and each alertAction is associated with an Alert resource.

```php
function postAlertActions(
    AlertActionsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): AlertActionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`AlertActionsPostRequest`](../../doc/models/alert-actions-post-request.md) | Body, Required | Create Alert Action Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`AlertActionsResponseResult`](../../doc/models/alert-actions-response-result.md)

## Example Usage

```php
$body = AlertActionsPostRequestBuilder::init(
    't1_alt_65fddb118236188e055d54c',
    AlertActionTypeEnum::WEB,
    'JSON',
    'https://test.payrix.com/apix/test/t1'
)
    ->headerName('Authorization')
    ->headerValue('SecretToken123!')
    ->retries(3)
    ->maxAttemptsTempDisabled(AlertActionsMaxAttemptsTempDisabledEnum::NOTTEMPORARILYDISABLED)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $alertActionsController->postAlertActions(
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
        "id": "t1_ala_67d0924f1919ec362341d00",
        "created": "2025-03-11 15:43:11.1194",
        "modified": "2025-03-11 15:43:11.1194",
        "creator": "t1_log_65b2c883d793216616f16ab",
        "modifier": "t1_log_65b2c883d793216616f16ab",
        "type": "web",
        "options": "JSON",
        "value": "https://test.payrix.com/apix/test/t1",
        "alert": "t1_alt_65fddb118236188e055d54c",
        "retries": 3,
        "headerName": "Authorization",
        "headerValue": "SecretToken123!",
        "maxAttemptsTempDisabled": 0,
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

