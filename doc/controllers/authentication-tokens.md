# Authentication Tokens

```php
$authenticationTokensController = $client->getAuthenticationTokensController();
```

## Class Name

`AuthenticationTokensController`

## Methods

* [Get Auth Tokens Id](../../doc/controllers/authentication-tokens.md#get-auth-tokens-id)
* [Put Auth Tokens Id](../../doc/controllers/authentication-tokens.md#put-auth-tokens-id)
* [Delete Auth Tokens Id](../../doc/controllers/authentication-tokens.md#delete-auth-tokens-id)
* [Get Auth Tokens](../../doc/controllers/authentication-tokens.md#get-auth-tokens)
* [Post Auth Tokens](../../doc/controllers/authentication-tokens.md#post-auth-tokens)


# Get Auth Tokens Id

Query an AuthToken, an AuthToken resource is an additional layer of authentication security and tracking for Apikeys and Sessions.

```php
function getAuthTokensId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): AuthTokensResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Authentication Token ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`AuthTokensResponseResult`](../../doc/models/auth-tokens-response-result.md)

## Example Usage

```php
$id = 't1_atk_67d4721def0c98ba2f417bz';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $authenticationTokensController->getAuthTokensId(
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
        "id": "t1_atk_67d4721def0c98ba2f417bz",
        "created": "2025-03-14 14:14:53.9897",
        "modified": "2025-03-14 14:14:54.5877",
        "creator": "t1_log_6372b01eed9b6a8c75ac8a3",
        "modifier": "t1_log_6372b01eed9b6a8c75ac8a3",
        "login": "t1_log_6372b01eed9b6a8c75ac8a3",
        "token": "261cf67bb2dc20f492abcdb39ecee847",
        "customer": "000a1eafdfdb335179adf94c1d8bc36d",
        "used": 202503141414,
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


# Put Auth Tokens Id

Update an AuthToken to add an additional layer of authentication security and tracking for Apikeys and Sessions.

```php
function putAuthTokensId(
    string $id,
    AuthTokensPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): AuthTokensResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Authentication Token ID. |
| `body` | [`AuthTokensPutRequest`](../../doc/models/auth-tokens-put-request.md) | Body, Required | Update Authentication Token Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`AuthTokensResponseResult`](../../doc/models/auth-tokens-response-result.md)

## Example Usage

```php
$id = 't1_atk_67d4721def0c98ba2f417bz';

$body = AuthTokensPutRequestBuilder::init()
    ->used(202503141414)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $authenticationTokensController->putAuthTokensId(
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
        "id": "t1_atk_67d4721def0c98ba2f417bz",
        "created": "2025-03-14 14:14:53.9897",
        "modified": "2025-03-14 14:14:54.5877",
        "creator": "t1_log_6372b01eed9b6a8c75ac8a3",
        "modifier": "t1_log_6372b01eed9b6a8c75ac8a3",
        "login": "t1_log_6372b01eed9b6a8c75ac8a3",
        "token": "261cf67bb2dc20f492abcdb39ecee847",
        "customer": "000a1eafdfdb335179adf94c1d8bc36d",
        "used": 202503141414,
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


# Delete Auth Tokens Id

Delete an AuthToken, which is an additional layer of authentication security and tracking for Apikeys and Sessions.

```php
function deleteAuthTokensId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): AuthTokensResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Authentication Token ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`AuthTokensResponseResult`](../../doc/models/auth-tokens-response-result.md)

## Example Usage

```php
$id = 't1_atk_67d4721def0c98ba2f417bz';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $authenticationTokensController->deleteAuthTokensId(
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
        "id": "t1_atk_67d4721def0c98ba2f417bz",
        "created": "2025-03-14 14:14:53.9897",
        "modified": "2025-03-14 14:14:54.5877",
        "creator": "t1_log_6372b01eed9b6a8c75ac8a3",
        "modifier": "t1_log_6372b01eed9b6a8c75ac8a3",
        "login": "t1_log_6372b01eed9b6a8c75ac8a3",
        "token": "261cf67bb2dc20f492abcdb39ecee847",
        "customer": "000a1eafdfdb335179adf94c1d8bc36d",
        "used": 202503141414,
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


# Get Auth Tokens

Query an AuthToken, which is an additional layer of authentication security and tracking for Apikeys and Sessions.

```php
function getAuthTokens(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): AuthTokensResponseResult
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

[`AuthTokensResponseResult`](../../doc/models/auth-tokens-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $authenticationTokensController->getAuthTokens(
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
        "id": "t1_atk_67d4721def0c98ba2f417bz",
        "created": "2025-03-14 14:14:53.9897",
        "modified": "2025-03-14 14:14:54.5877",
        "creator": "t1_log_6372b01eed9b6a8c75ac8a3",
        "modifier": "t1_log_6372b01eed9b6a8c75ac8a3",
        "login": "t1_log_6372b01eed9b6a8c75ac8a3",
        "token": "261cf67bb2dc20f492abcdb39ecee847",
        "customer": "000a1eafdfdb335179adf94c1d8bc36d",
        "used": 202503141414,
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
| 400 | ErrorError | [`ErrorFourHundredException`](../../doc/models/error-four-hundred-exception.md) |


# Post Auth Tokens

Create an AuthToken to add an additional layer of authentication, security, and tracking for Apikeys and Sessions.

```php
function postAuthTokens(
    AuthTokensPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): AuthTokensResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`AuthTokensPostRequest`](../../doc/models/auth-tokens-post-request.md) | Body, Required | Create Authentication Token Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`AuthTokensResponseResult`](../../doc/models/auth-tokens-response-result.md)

## Example Usage

```php
$body = AuthTokensPostRequestBuilder::init(
    't1_log_6372b01eed9b6a8c75ac8a3',
    '000a1eafdfdb335179adf94c1d8bc36d',
    '261cf67bb2dc20f492abcdb39ecee847'
)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $authenticationTokensController->postAuthTokens(
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
        "id": "t1_atk_67d4721def0c98ba2f417bz",
        "created": "2025-03-14 14:14:53.9897",
        "modified": "2025-03-14 14:14:54.5877",
        "creator": "t1_log_6372b01eed9b6a8c75ac8a3",
        "modifier": "t1_log_6372b01eed9b6a8c75ac8a3",
        "login": "t1_log_6372b01eed9b6a8c75ac8a3",
        "token": "261cf67bb2dc20f492abcdb39ecee847",
        "customer": "000a1eafdfdb335179adf94c1d8bc36d",
        "used": 202503141414,
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

