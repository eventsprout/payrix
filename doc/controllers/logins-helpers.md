# Logins Helpers

```php
$loginsHelpersController = $client->getLoginsHelpersController();
```

## Class Name

`LoginsHelpersController`

## Methods

* [Get Logins Helpers Id](../../doc/controllers/logins-helpers.md#get-logins-helpers-id)
* [Put Logins Helpers Id](../../doc/controllers/logins-helpers.md#put-logins-helpers-id)
* [Get Logins Helpers](../../doc/controllers/logins-helpers.md#get-logins-helpers)


# Get Logins Helpers Id

Query a loginsHelper.

```php
function getLoginsHelpersId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): LoginsHelpersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`LoginsHelpersResponseResult`](../../doc/models/logins-helpers-response-result.md)

## Example Usage

```php
$id = 't1_lgh_67ee09c7402cff94765db3c';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $loginsHelpersController->getLoginsHelpersId(
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
        "id": "t1_lgh_67ee09c7402cff94765db3c",
        "created": "2025-04-03 00:08:39.2707",
        "modified": "2025-04-03 00:08:39.2707",
        "creator": "t1_log_65b2c8c108ac3cd41432a1e",
        "modifier": "t1_log_65b2c8c108ac3cd41432a1e",
        "login": "t1_log_67ee09bbc22011eaae4ddd9",
        "mfaSmsCode": "code",
        "mfaSmsCodeUnixTime": 623,
        "mfaSmsCodeAttempts": 0,
        "mfaSmsCodesCount": 0,
        "mfaSmsWindow": 0,
        "loginAsEnabled": 0
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


# Put Logins Helpers Id

Update a loginsHelper.

```php
function putLoginsHelpersId(
    string $id,
    LoginsHelpersPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): LoginsHelpersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `body` | [`LoginsHelpersPutRequest`](../../doc/models/logins-helpers-put-request.md) | Body, Required | - |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`LoginsHelpersResponseResult`](../../doc/models/logins-helpers-response-result.md)

## Example Usage

```php
$id = 't1_lgh_67ee09c7402cff94765db3c';

$body = LoginsHelpersPutRequestBuilder::init()
    ->loginAsEnabled(LoginHelpersLoginAsEnabledEnum::OFF)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $loginsHelpersController->putLoginsHelpersId(
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
        "id": "t1_lgh_67ee09c7402cff94765db3c",
        "created": "2025-04-03 00:08:39.2707",
        "modified": "2025-04-03 00:08:39.2707",
        "creator": "t1_log_65b2c8c108ac3cd41432a1e",
        "modifier": "t1_log_65b2c8c108ac3cd41432a1e",
        "login": "t1_log_67ee09bbc22011eaae4ddd9",
        "mfaSmsCode": "code",
        "mfaSmsCodeUnixTime": 623,
        "mfaSmsCodeAttempts": 0,
        "mfaSmsCodesCount": 0,
        "mfaSmsWindow": 0,
        "loginAsEnabled": 0
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


# Get Logins Helpers

Query loginsHelpers.

```php
function getLoginsHelpers(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): LoginsHelpersResponseResult
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

[`LoginsHelpersResponseResult`](../../doc/models/logins-helpers-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $loginsHelpersController->getLoginsHelpers(
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
        "id": "t1_lgh_67ee09c7402cff94765db3c",
        "created": "2025-04-03 00:08:39.2707",
        "modified": "2025-04-03 00:08:39.2707",
        "creator": "t1_log_65b2c8c108ac3cd41432a1e",
        "modifier": "t1_log_65b2c8c108ac3cd41432a1e",
        "login": "t1_log_67ee09bbc22011eaae4ddd9",
        "mfaSmsCode": "code",
        "mfaSmsCodeUnixTime": 623,
        "mfaSmsCodeAttempts": 0,
        "mfaSmsCodesCount": 0,
        "mfaSmsWindow": 0,
        "loginAsEnabled": 0
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

