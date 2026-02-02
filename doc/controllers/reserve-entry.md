# Reserve Entry

```php
$reserveEntryController = $client->getReserveEntryController();
```

## Class Name

`ReserveEntryController`

## Methods

* [Get Reserve Entries Id](../../doc/controllers/reserve-entry.md#get-reserve-entries-id)
* [Get Reserve Entries](../../doc/controllers/reserve-entry.md#get-reserve-entries)
* [Post Reserve Entries](../../doc/controllers/reserve-entry.md#post-reserve-entries)


# Get Reserve Entries Id

Query a Reserve Entry resource that describes a record of funds moving in or out of reserve and can be associated with either a Transaction, a Reserve, an entityReserve, or another reserveEntry resource.

```php
function getReserveEntriesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): ReserveEntriesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this reserve entry. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`ReserveEntriesResponseResult`](../../doc/models/reserve-entries-response-result.md)

## Example Usage

```php
$id = 't1_rer_6800d1df0a777412aa4c8c3';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $reserveEntryController->getReserveEntriesId(
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
        "id": "t1_rer_6800d1df0a777412aa4c8c3",
        "created": "2025-04-17 06:03:11.0593",
        "modified": "2025-04-17 06:03:11.1237",
        "creator": "t1_log_673245a79517f80bf2e7738",
        "modifier": "t1_log_673245a79517f80bf2e7738",
        "login": "t1_log_5d652e3c9bb91623e859e02",
        "fund": "t1_fun_5e6186054d4dbe2416bca5c",
        "txn": "t1_txn_67caef0a014c280a6caa5zz",
        "hold": "t1_hld_67ef5bad3be038935902200",
        "reserve": "t1_rsv_5e21064368e32ef4d38f8d4",
        "entityReserve": "",
        "reserveEntry": "",
        "description": "description1",
        "release": "20160120",
        "amount": 15,
        "onentity": "",
        "entry": "t1_etr_6800d1dee193517e5d6ce91",
        "event": 6,
        "eventId": "t1_txn_6800d1dd114238a04f4e608",
        "status": "processed",
        "statusMessage": "",
        "processed": "2025-04-17 06:03:11.1237",
        "processingId": "t1_rer_6800d1df1e3d47d69bd1cd4"
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


# Get Reserve Entries

Query a reserveEntry resource.
A reserveEntry resource describes a record of funds moving in or out of reserve. It can be associated with either a Transaction, a Reserve, an entityReserve, or another reserveEntry resource.

```php
function getReserveEntries(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): ReserveEntriesResponseResult
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

[`ReserveEntriesResponseResult`](../../doc/models/reserve-entries-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $reserveEntryController->getReserveEntries(
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
        "id": "t1_rer_6800d1df0a777412aa4c8c3",
        "created": "2025-04-17 06:03:11.0593",
        "modified": "2025-04-17 06:03:11.1237",
        "creator": "t1_log_673245a79517f80bf2e7738",
        "modifier": "t1_log_673245a79517f80bf2e7738",
        "login": "t1_log_5d652e3c9bb91623e859e02",
        "fund": "t1_fun_5e6186054d4dbe2416bca5c",
        "txn": "t1_txn_67caef0a014c280a6caa5zz",
        "hold": "t1_hld_67ef5bad3be038935902200",
        "reserve": "t1_rsv_5e21064368e32ef4d38f8d4",
        "entityReserve": "",
        "reserveEntry": "",
        "description": "description1",
        "release": "20160120",
        "amount": 15,
        "onentity": "",
        "entry": "t1_etr_6800d1dee193517e5d6ce91",
        "event": 6,
        "eventId": "t1_txn_6800d1dd114238a04f4e608",
        "status": "processed",
        "statusMessage": "",
        "processed": "2025-04-17 06:03:11.1237",
        "processingId": "t1_rer_6800d1df1e3d47d69bd1cd4"
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


# Post Reserve Entries

Create a Reserve Entry resource that describes a record of funds moving in or out of reserve and can be associated with either a Transaction, a Reserve, an entityReserve, or another reserveEntry resource.

```php
function postReserveEntries(
    ReserveEntriesPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): ReserveEntriesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`ReserveEntriesPostRequest`](../../doc/models/reserve-entries-post-request.md) | Body, Required | Create Reserve Entry Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ReserveEntriesResponseResult`](../../doc/models/reserve-entries-response-result.md)

## Example Usage

```php
$body = ReserveEntriesPostRequestBuilder::init(
    't1_log_5d652e3c9bb91623e859e02',
    't1_fun_5e6186054d4dbe2416bca5c',
    ReserveEntryEventEnum::AUTH,
    15
)
    ->entry('t1_etr_6800d1dee193517e5d6ce91')
    ->hold('t1_hld_67ef5bad3be038935902200')
    ->txn('t1_txn_67caef0a014c280a6caa5zz')
    ->reserve('t1_rsv_5e21064368e32ef4d38f8d4')
    ->entityReserve('identifier')
    ->reserveEntry('identifier')
    ->onentity('t1_ent_00c2b1a6102ffdd33f11000')
    ->eventId('t1_txn_6800d1dd114238a04f4e608')
    ->description('description1')
    ->release('20160120')
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $reserveEntryController->postReserveEntries(
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
        "id": "t1_rer_6800d1df0a777412aa4c8c3",
        "created": "2025-04-17 06:03:11.0593",
        "modified": "2025-04-17 06:03:11.1237",
        "creator": "t1_log_673245a79517f80bf2e7738",
        "modifier": "t1_log_673245a79517f80bf2e7738",
        "login": "t1_log_5d652e3c9bb91623e859e02",
        "fund": "t1_fun_5e6186054d4dbe2416bca5c",
        "txn": "t1_txn_67caef0a014c280a6caa5zz",
        "hold": "t1_hld_67ef5bad3be038935902200",
        "reserve": "t1_rsv_5e21064368e32ef4d38f8d4",
        "entityReserve": "",
        "reserveEntry": "",
        "description": "description1",
        "release": "20160120",
        "amount": 15,
        "onentity": "",
        "entry": "t1_etr_6800d1dee193517e5d6ce91",
        "event": 6,
        "eventId": "t1_txn_6800d1dd114238a04f4e608",
        "status": "processed",
        "statusMessage": "",
        "processed": "2025-04-17 06:03:11.1237",
        "processingId": "t1_rer_6800d1df1e3d47d69bd1cd4"
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

