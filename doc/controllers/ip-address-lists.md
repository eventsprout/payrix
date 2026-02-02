# IP Address Lists

```php
$iPAddressListsController = $client->getIPAddressListsController();
```

## Class Name

`IPAddressListsController`

## Methods

* [Get Iplists Id](../../doc/controllers/ip-address-lists.md#get-iplists-id)
* [Put Iplists Id](../../doc/controllers/ip-address-lists.md#put-iplists-id)
* [Delete Iplists Id](../../doc/controllers/ip-address-lists.md#delete-iplists-id)
* [Get Iplists](../../doc/controllers/ip-address-lists.md#get-iplists)
* [Post Iplists](../../doc/controllers/ip-address-lists.md#post-iplists)


# Get Iplists Id

Query an iplist resource that represents a list of IP addresses stored as a range between the lowest and highest IP addresses, which can be used to whitelist or blacklist particular incoming IP addresses for a given Login.

```php
function getIplistsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): IplistsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The IP Address List ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`IplistsResponseResult`](../../doc/models/iplists-response-result.md)

## Example Usage

```php
$id = 't1_ipl_67d42f7567ea0e8f1b43e0z';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $iPAddressListsController->getIplistsId(
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
        "id": "t1_ipl_67d42f7567ea0e8f1b43e0z",
        "created": "2025-03-14 09:30:29.4334",
        "modified": "2025-03-14 09:30:29.4334",
        "creator": "t1_log_61d874fe8b166d56672d0f9",
        "modifier": "t1_log_61d874fe8b166d56672d0f9",
        "login": "t1_log_61d874fe8b166d56672d0f9",
        "version": 4,
        "type": 1,
        "start": "1.1.1.1",
        "finish": "1.1.1.89",
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


# Put Iplists Id

_CONFLICT Update an iplist resource that represents a list of IP addresses stored as a range between the lowest and highest IP addresses, which can be used to whitelist or blacklist particular incoming IP addresses for a given Login.

```php
function putIplistsId(
    string $id,
    IplistsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): IplistsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The IP Address List ID. |
| `body` | [`IplistsPutRequest`](../../doc/models/iplists-put-request.md) | Body, Required | Update IP Address List Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`IplistsResponseResult`](../../doc/models/iplists-response-result.md)

## Example Usage

```php
$id = 't1_ipl_67d42f7567ea0e8f1b43e0z';

$body = IplistsPutRequestBuilder::init()
    ->login('t1_log_61d874fe8b166d56672d0f9')
    ->type(IplistTypeEnum::WHITELIST)
    ->start('1.1.1.1')
    ->finish('1.1.1.89')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $iPAddressListsController->putIplistsId(
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
        "id": "t1_ipl_67d42f7567ea0e8f1b43e0z",
        "created": "2025-03-14 09:30:29.4334",
        "modified": "2025-03-14 09:30:29.4334",
        "creator": "t1_log_61d874fe8b166d56672d0f9",
        "modifier": "t1_log_61d874fe8b166d56672d0f9",
        "login": "t1_log_61d874fe8b166d56672d0f9",
        "version": 4,
        "type": 1,
        "start": "1.1.1.1",
        "finish": "1.1.1.89",
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


# Delete Iplists Id

Delete an IP lists resource that represents a list of IP addresses, stored as a range between the lowest and highest IP addresses that should be included.

```php
function deleteIplistsId(string $id, ?string $token = null, ?string $requestToken = null): IplistsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The IP Address List ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`IplistsResponseResult`](../../doc/models/iplists-response-result.md)

## Example Usage

```php
$id = 't1_ipl_67d42f7567ea0e8f1b43e0z';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $iPAddressListsController->deleteIplistsId(
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
        "id": "t1_ipl_67d42f7567ea0e8f1b43e0z",
        "created": "2025-03-14 09:30:29.4334",
        "modified": "2025-03-14 09:30:29.4334",
        "creator": "t1_log_61d874fe8b166d56672d0f9",
        "modifier": "t1_log_61d874fe8b166d56672d0f9",
        "login": "t1_log_61d874fe8b166d56672d0f9",
        "version": 4,
        "type": 1,
        "start": "1.1.1.1",
        "finish": "1.1.1.89",
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


# Get Iplists

Query an iplist resource representing a list of IP addresses stored as a range between the lowest and highest IP addresses that should be included, which you can use to whitelist or blacklist particular incoming IP addresses for a given Login.

```php
function getIplists(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): IplistsResponseResult
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

[`IplistsResponseResult`](../../doc/models/iplists-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $iPAddressListsController->getIplists(
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
        "id": "t1_ipl_67d42f7567ea0e8f1b43e0z",
        "created": "2025-03-14 09:30:29.4334",
        "modified": "2025-03-14 09:30:29.4334",
        "creator": "t1_log_61d874fe8b166d56672d0f9",
        "modifier": "t1_log_61d874fe8b166d56672d0f9",
        "login": "t1_log_61d874fe8b166d56672d0f9",
        "version": 4,
        "type": 1,
        "start": "1.1.1.1",
        "finish": "1.1.1.89",
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


# Post Iplists

Create an iplists resource. An IP List represents a list of IP (Internet Protocol) addresses, stored as a range between the lowest and highest IP addresses that should be included.
You can use an IP List to whitelist (allow) or blacklist (deny) particular incoming IP addresses for a given Login. If you set up a whitelist for a Login, then the only allowed IP addresses are those in the whitelist, minus any blacklisted IP addresses. If you do not set up a whitelist for a Login, then all IP addresses are allowed, except for those explicitly blacklisted.
You can select whether to store IPv4 or IPv6 addresses in an IP list.

```php
function postIplists(
    IplistsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): IplistsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`IplistsPostRequest`](../../doc/models/iplists-post-request.md) | Body, Required | Create IP Address List Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`IplistsResponseResult`](../../doc/models/iplists-response-result.md)

## Example Usage

```php
$body = IplistsPostRequestBuilder::init(
    't1_log_61d874fe8b166d56672d0f9',
    '1.1.1.1'
)
    ->version(IplistsVersionEnum::IPV4)
    ->type(IplistTypeEnum::WHITELIST)
    ->finish('1.1.1.89')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $iPAddressListsController->postIplists(
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
        "id": "t1_ipl_67d42f7567ea0e8f1b43e0z",
        "created": "2025-03-14 09:30:29.4334",
        "modified": "2025-03-14 09:30:29.4334",
        "creator": "t1_log_61d874fe8b166d56672d0f9",
        "modifier": "t1_log_61d874fe8b166d56672d0f9",
        "login": "t1_log_61d874fe8b166d56672d0f9",
        "version": 4,
        "type": 1,
        "start": "1.1.1.1",
        "finish": "1.1.1.89",
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

