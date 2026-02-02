# Reserves

Resources that deals with reserve activity. Reserving means to withhold funds from an entity by removing the ability to extract the funds from the control of the financial institution.

```php
$reservesController = $client->getReservesController();
```

## Class Name

`ReservesController`

## Methods

* [Get Reserves Id](../../doc/controllers/reserves.md#get-reserves-id)
* [Put Reserves Id](../../doc/controllers/reserves.md#put-reserves-id)
* [Delete Reserves Id](../../doc/controllers/reserves.md#delete-reserves-id)
* [Get Reserves](../../doc/controllers/reserves.md#get-reserves)
* [Post Reserves](../../doc/controllers/reserves.md#post-reserves)


# Get Reserves Id

Query a Reserve resource that represents a way to reserve funds from an Entity or Org automatically and to release them automatically according to a pre-determined schedule.

```php
function getReservesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): ReservesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this reserve. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`ReservesResponseResult`](../../doc/models/reserves-response-result.md)

## Example Usage

```php
$id = 't1_rsv_66f27fca06f8a777998c000';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $reservesController->getReservesId(
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
        "id": "t1_rsv_66f27fca06f8a777998c000",
        "created": "2024-09-24 05:00:58.0528",
        "modified": "2024-09-24 05:00:58.0528",
        "creator": "t1_log_611e6ca320fae7afab2f000",
        "modifier": "t1_log_611e6ca320fae7afab2f000",
        "login": "t1_log_611e6ca320fae7afab2f256",
        "org": "t1_org_5fada4629c317f80bc9cb00",
        "entity": "t1_ent_5f9058fe8c8d21ead8f68dc",
        "name": "Additional Underwriting Review Required",
        "description": "Will release the reserve once all information is verified.",
        "percent": 10000,
        "release": "never",
        "releaseFactor": 1,
        "finish": 20160120,
        "inactive": 0,
        "frozen": 0,
        "max": 0,
        "start": 20160120,
        "hold": "t1_hld_66f27fca0236545c4f125d2",
        "division": "t1_div_67b51635da21f7399ce2az0",
        "partition": "t1_ptn_000834d4d504f11234578f0",
        "level": "merchant",
        "status": 1
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


# Put Reserves Id

Update a Reserves or Reserve resource, which represents a way to reserve funds from an Entity or Org automatically and to release them automatically according to a pre-determined schedule.

```php
function putReservesId(
    string $id,
    ReservesPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): ReservesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this reserve. |
| `body` | [`ReservesPutRequest`](../../doc/models/reserves-put-request.md) | Body, Required | Update a Reserve Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ReservesResponseResult`](../../doc/models/reserves-response-result.md)

## Example Usage

```php
$id = 't1_rsv_66f27fca06f8a777998c000';

$body = ReservesPutRequestBuilder::init()
    ->login('t1_log_611e6ca320fae7afab2f256')
    ->org('t1_org_5fada4629c317f80bc9cb00')
    ->division('t1_div_67b51635da21f7399ce2az0')
    ->partition('t1_ptn_000834d4d504f11234578f0')
    ->level(ReservesLevelEnum::MERCHANT)
    ->entity('t1_ent_5f9058fe8c8d21ead8f68dc')
    ->hold('t1_hld_66f27fca0236545c4f125d2')
    ->name('Additional Underwriting Review Required')
    ->description('Will release the reserve once all information is verified.')
    ->percent(10000)
    ->release(ReservesReleaseEnum::NEVER)
    ->releaseFactor(1)
    ->start(20160120)
    ->finish(20160120)
    ->max(0)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $reservesController->putReservesId(
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
        "id": "t1_rsv_66f27fca06f8a777998c000",
        "created": "2024-09-24 05:00:58.0528",
        "modified": "2024-09-24 05:00:58.0528",
        "creator": "t1_log_611e6ca320fae7afab2f000",
        "modifier": "t1_log_611e6ca320fae7afab2f000",
        "login": "t1_log_611e6ca320fae7afab2f256",
        "org": "t1_org_5fada4629c317f80bc9cb00",
        "entity": "t1_ent_5f9058fe8c8d21ead8f68dc",
        "name": "Additional Underwriting Review Required",
        "description": "Will release the reserve once all information is verified.",
        "percent": 10000,
        "release": "never",
        "releaseFactor": 1,
        "finish": 20160120,
        "inactive": 0,
        "frozen": 0,
        "max": 0,
        "start": 20160120,
        "hold": "t1_hld_66f27fca0236545c4f125d2",
        "division": "t1_div_67b51635da21f7399ce2az0",
        "partition": "t1_ptn_000834d4d504f11234578f0",
        "level": "merchant",
        "status": 1
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


# Delete Reserves Id

Delete a Reserves or Reserve resource that represents a way to reserve funds from an Entity or Org automatically and to release them automatically according to a pre-determined schedule.

```php
function deleteReservesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): ReservesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this reserve. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ReservesResponseResult`](../../doc/models/reserves-response-result.md)

## Example Usage

```php
$id = 't1_rsv_66f27fca06f8a777998c000';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $reservesController->deleteReservesId(
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
        "id": "t1_rsv_66f27fca06f8a777998c000",
        "created": "2024-09-24 05:00:58.0528",
        "modified": "2024-09-24 05:00:58.0528",
        "creator": "t1_log_611e6ca320fae7afab2f000",
        "modifier": "t1_log_611e6ca320fae7afab2f000",
        "login": "t1_log_611e6ca320fae7afab2f256",
        "org": "t1_org_5fada4629c317f80bc9cb00",
        "entity": "t1_ent_5f9058fe8c8d21ead8f68dc",
        "name": "Additional Underwriting Review Required",
        "description": "Will release the reserve once all information is verified.",
        "percent": 10000,
        "release": "never",
        "releaseFactor": 1,
        "finish": 20160120,
        "inactive": 0,
        "frozen": 0,
        "max": 0,
        "start": 20160120,
        "hold": "t1_hld_66f27fca0236545c4f125d2",
        "division": "t1_div_67b51635da21f7399ce2az0",
        "partition": "t1_ptn_000834d4d504f11234578f0",
        "level": "merchant",
        "status": 1
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


# Get Reserves

Query a Reserves resource.
A Reserves resource represents a way to reserve funds from an Entity or Org automatically and to release them automatically according to a pre-determined schedule.

```php
function getReserves(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): ReservesResponseResult
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

[`ReservesResponseResult`](../../doc/models/reserves-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $reservesController->getReserves(
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
        "id": "t1_rsv_66f27fca06f8a777998c000",
        "created": "2024-09-24 05:00:58.0528",
        "modified": "2024-09-24 05:00:58.0528",
        "creator": "t1_log_611e6ca320fae7afab2f000",
        "modifier": "t1_log_611e6ca320fae7afab2f000",
        "login": "t1_log_611e6ca320fae7afab2f256",
        "org": "t1_org_5fada4629c317f80bc9cb00",
        "entity": "t1_ent_5f9058fe8c8d21ead8f68dc",
        "name": "Additional Underwriting Review Required",
        "description": "Will release the reserve once all information is verified.",
        "percent": 10000,
        "release": "never",
        "releaseFactor": 1,
        "finish": 20160120,
        "inactive": 0,
        "frozen": 0,
        "max": 0,
        "start": 20160120,
        "hold": "t1_hld_66f27fca0236545c4f125d2",
        "division": "t1_div_67b51635da21f7399ce2az0",
        "partition": "t1_ptn_000834d4d504f11234578f0",
        "level": "merchant",
        "status": 1
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


# Post Reserves

Create a Reserves resource.
A Reserves resource represents a way to reserve funds from an Entity or Org automatically and to release them automatically according to a pre-determined schedule.

```php
function postReserves(
    ReservesPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): ReservesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`ReservesPostRequest`](../../doc/models/reserves-post-request.md) | Body, Required | Create Reserve Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ReservesResponseResult`](../../doc/models/reserves-response-result.md)

## Example Usage

```php
$body = ReservesPostRequestBuilder::init(
    't1_log_611e6ca320fae7afab2f256',
    10000
)
    ->org(
        't1_org_5fada4629c317f80bc9cb00'
    )
    ->division('t1_div_67b51635da21f7399ce2az0')
    ->partition('t1_ptn_000834d4d504f11234578f0')
    ->level(ReservesLevelEnum::MERCHANT)
    ->entity('t1_ent_5f9058fe8c8d21ead8f68dc')
    ->hold('t1_hld_66f27fca0236545c4f125d2')
    ->name('Additional Underwriting Review Required')
    ->description('Will release the reserve once all information is verified.')
    ->release(ReservesReleaseEnum::NEVER)
    ->releaseFactor(1)
    ->start(20160120)
    ->finish(20160120)
    ->max(0)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $reservesController->postReserves(
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
        "id": "t1_rsv_66f27fca06f8a777998c000",
        "created": "2024-09-24 05:00:58.0528",
        "modified": "2024-09-24 05:00:58.0528",
        "creator": "t1_log_611e6ca320fae7afab2f000",
        "modifier": "t1_log_611e6ca320fae7afab2f000",
        "login": "t1_log_611e6ca320fae7afab2f256",
        "org": "t1_org_5fada4629c317f80bc9cb00",
        "entity": "t1_ent_5f9058fe8c8d21ead8f68dc",
        "name": "Additional Underwriting Review Required",
        "description": "Will release the reserve once all information is verified.",
        "percent": 10000,
        "release": "never",
        "releaseFactor": 1,
        "finish": 20160120,
        "inactive": 0,
        "frozen": 0,
        "max": 0,
        "start": 20160120,
        "hold": "t1_hld_66f27fca0236545c4f125d2",
        "division": "t1_div_67b51635da21f7399ce2az0",
        "partition": "t1_ptn_000834d4d504f11234578f0",
        "level": "merchant",
        "status": 1
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

