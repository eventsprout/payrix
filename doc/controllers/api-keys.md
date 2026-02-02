# API Keys

```php
$aPIKeysController = $client->getAPIKeysController();
```

## Class Name

`APIKeysController`

## Methods

* [Get Apikeys Id](../../doc/controllers/api-keys.md#get-apikeys-id)
* [Put Apikeys Id](../../doc/controllers/api-keys.md#put-apikeys-id)
* [Delete Apikeys Id](../../doc/controllers/api-keys.md#delete-apikeys-id)
* [Get Apikeys](../../doc/controllers/api-keys.md#get-apikeys)
* [Post Apikeys](../../doc/controllers/api-keys.md#post-apikeys)


# Get Apikeys Id

Query an API key that represents a permanent method of authentication to the API, remaining active until marked as inactive or deleted.

```php
function getApikeysId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): ApikeysResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of the API Key. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`ApikeysResponseResult`](../../doc/models/apikeys-response-result.md)

## Example Usage

```php
$id = 't1_api_676a5353d67a6df2c47b198';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $aPIKeysController->getApikeysId(
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
        "id": "t1_api_676a5353d67a6df2c47b198",
        "created": "2024-12-24 01:23:15.8882",
        "modified": "2024-12-24 01:23:15.8882",
        "creator": "t1_log_651fec1e202e349386ba321",
        "modifier": "t1_log_651fec1e202e349386ba321",
        "login": "t1_log_651fec1e202e349386ba321",
        "key": "f0d9fd14f9795590c01dd2c8083a35d7",
        "name": "api",
        "description": "API KEYS",
        "public": 0,
        "inactive": 0,
        "frozen": 0,
        "token": 0
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


# Put Apikeys Id

Update an API key, which represents a permanent method of authentication to the API. Each API key remains active until you mark it as inactive or delete it.

```php
function putApikeysId(
    string $id,
    ApiKeysPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): ApikeysResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The API Key ID. |
| `body` | [`ApiKeysPutRequest`](../../doc/models/api-keys-put-request.md) | Body, Required | Update API Key Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ApikeysResponseResult`](../../doc/models/apikeys-response-result.md)

## Example Usage

```php
$id = 't1_api_676a5353d67a6df2c47b198';

$body = ApiKeysPutRequestBuilder::init()
    ->name('api')
    ->description('API KEYS')
    ->token(ApikeysTokenEnum::AUTHTOKENDISABLED)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $aPIKeysController->putApikeysId(
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
        "id": "t1_api_676a5353d67a6df2c47b198",
        "created": "2024-12-24 01:23:15.8882",
        "modified": "2024-12-24 01:23:15.8882",
        "creator": "t1_log_651fec1e202e349386ba321",
        "modifier": "t1_log_651fec1e202e349386ba321",
        "login": "t1_log_651fec1e202e349386ba321",
        "key": "f0d9fd14f9795590c01dd2c8083a35d7",
        "name": "api",
        "description": "API KEYS",
        "public": 0,
        "inactive": 0,
        "frozen": 0,
        "token": 0
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


# Delete Apikeys Id

Delete an API key that represents a permanent method of authentication to the API and remains active until marked as inactive or deleted.

```php
function deleteApikeysId(string $id, ?string $token = null, ?string $requestToken = null): ApikeysResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of the API Key. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ApikeysResponseResult`](../../doc/models/apikeys-response-result.md)

## Example Usage

```php
$id = 't1_api_676a5353d67a6df2c47b198';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $aPIKeysController->deleteApikeysId(
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
        "id": "t1_api_676a5353d67a6df2c47b198",
        "created": "2024-12-24 01:23:15.8882",
        "modified": "2024-12-24 01:23:15.8882",
        "creator": "t1_log_651fec1e202e349386ba321",
        "modifier": "t1_log_651fec1e202e349386ba321",
        "login": "t1_log_651fec1e202e349386ba321",
        "key": "f0d9fd14f9795590c01dd2c8083a35d7",
        "name": "api",
        "description": "API KEYS",
        "public": 0,
        "inactive": 0,
        "frozen": 0,
        "token": 0
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


# Get Apikeys

Query API keys that each represents a permanent method of authentication to the API and remains active until marked as inactive or deleted.

```php
function getApikeys(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): ApikeysResponseResult
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

[`ApikeysResponseResult`](../../doc/models/apikeys-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $aPIKeysController->getApikeys(
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
        "id": "t1_api_676a5353d67a6df2c47b198",
        "created": "2024-12-24 01:23:15.8882",
        "modified": "2024-12-24 01:23:15.8882",
        "creator": "t1_log_651fec1e202e349386ba321",
        "modifier": "t1_log_651fec1e202e349386ba321",
        "login": "t1_log_651fec1e202e349386ba321",
        "key": "f0d9fd14f9795590c01dd2c8083a35d7",
        "name": "api",
        "description": "API KEYS",
        "public": 0,
        "inactive": 0,
        "frozen": 0,
        "token": 0
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


# Post Apikeys

Create an API key that represents a permanent method of authentication to the API. The API key remains active until marked as inactive or deleted.

```php
function postApikeys(
    ApiKeysPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): ApikeysResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`ApiKeysPostRequest`](../../doc/models/api-keys-post-request.md) | Body, Required | Create API Key Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ApikeysResponseResult`](../../doc/models/apikeys-response-result.md)

## Example Usage

```php
$body = ApiKeysPostRequestBuilder::init(
    't1_log_651fec1e202e349386ba321'
)
    ->name('api')
    ->description('API KEYS')
    ->public(ApiKeyPublicEnum::PRIVATEACCESS)
    ->token(ApikeysTokenEnum::AUTHTOKENDISABLED)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $aPIKeysController->postApikeys(
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
        "id": "t1_api_676a5353d67a6df2c47b198",
        "created": "2024-12-24 01:23:15.8882",
        "modified": "2024-12-24 01:23:15.8882",
        "creator": "t1_log_651fec1e202e349386ba321",
        "modifier": "t1_log_651fec1e202e349386ba321",
        "login": "t1_log_651fec1e202e349386ba321",
        "key": "f0d9fd14f9795590c01dd2c8083a35d7",
        "name": "api",
        "description": "API KEYS",
        "public": 0,
        "inactive": 0,
        "frozen": 0,
        "token": 0
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

