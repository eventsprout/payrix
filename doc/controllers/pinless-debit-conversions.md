# Pinless Debit Conversions

```php
$pinlessDebitConversionsController = $client->getPinlessDebitConversionsController();
```

## Class Name

`PinlessDebitConversionsController`

## Methods

* [Get Pinless Debit Conversions Id](../../doc/controllers/pinless-debit-conversions.md#get-pinless-debit-conversions-id)
* [Put Pinless Debit Conversions Id](../../doc/controllers/pinless-debit-conversions.md#put-pinless-debit-conversions-id)
* [Get Pinless Debit Conversions](../../doc/controllers/pinless-debit-conversions.md#get-pinless-debit-conversions)
* [Post Pinless Debit Conversions](../../doc/controllers/pinless-debit-conversions.md#post-pinless-debit-conversions)


# Get Pinless Debit Conversions Id

Query a pinlessDebitConversion.

```php
function getPinlessDebitConversionsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): PinlessDebitConversionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this pinlessDebitConversion. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`PinlessDebitConversionsResponseResult`](../../doc/models/pinless-debit-conversions-response-result.md)

## Example Usage

```php
$id = 't1_pdc_684c7ec770b6d462c4cd000';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $pinlessDebitConversionsController->getPinlessDebitConversionsId(
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
        "id": "t1_pdc_684c7ec770b6d462c4cd000",
        "entity": "t1_ent_684c79a47671985f15621c0",
        "created": "2025-06-13 15:40:55.4761",
        "modified": "2025-06-13 15:43:09.6391",
        "creator": "t1_log_67a4e72ad2ccca060a2fzzz",
        "modifier": "t1_log_67a4e72ad2ccca060a2fzzz",
        "enablementDate": "2025-06-16 11:15:47",
        "org": "t1_org_684c7ae33b2d4f98520a79a",
        "division": "t1_div_684c7ae33b2d4f98520a00b",
        "partition": "t1_ptn_666834d4d504f11234578f0",
        "platform": "VCORE",
        "inactive": 1,
        "frozen": 0,
        "deleted": "2025-06-13 15:43:09",
        "deleter": "t1_log_67a4e72ad2ccca060a2fcfb"
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


# Put Pinless Debit Conversions Id

Update a pinlessDebitConversion.

```php
function putPinlessDebitConversionsId(
    string $id,
    PinlessDebitConversionsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): PinlessDebitConversionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this Pinless Debit Conversions. |
| `body` | [`PinlessDebitConversionsPutRequest`](../../doc/models/pinless-debit-conversions-put-request.md) | Body, Required | Update Pinless Debit Conversions |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`PinlessDebitConversionsResponseResult`](../../doc/models/pinless-debit-conversions-response-result.md)

## Example Usage

```php
$id = 't1_pdc_684c7ec770b6d462c4cd000';

$body = PinlessDebitConversionsPutRequestBuilder::init()
    ->enablementDate('2023-06-01 01:00:00')
    ->org('t1_org_684c7ae33b2d4f98520a79a')
    ->division('t1_div_684c7ae33b2d4f98520a00b')
    ->partition('t1_ptn_666834d4d504f11234578f0')
    ->platform(PinlessDebitConversionsPlatformEnum::VCORE)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->deleted('2023-06-01 01:00:00')
    ->deleter('t1_log_67a4e72ad2ccca060a2fcfb')
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $pinlessDebitConversionsController->putPinlessDebitConversionsId(
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
        "id": "t1_pdc_684c7ec770b6d462c4cd000",
        "entity": "t1_ent_684c79a47671985f15621c0",
        "created": "2025-06-13 15:40:55.4761",
        "modified": "2025-06-13 15:43:09.6391",
        "creator": "t1_log_67a4e72ad2ccca060a2fzzz",
        "modifier": "t1_log_67a4e72ad2ccca060a2fzzz",
        "enablementDate": "2025-06-16 11:15:47",
        "org": "t1_org_684c7ae33b2d4f98520a79a",
        "division": "t1_div_684c7ae33b2d4f98520a00b",
        "partition": "t1_ptn_666834d4d504f11234578f0",
        "platform": "VCORE",
        "inactive": 1,
        "frozen": 0,
        "deleted": "2025-06-13 15:43:09",
        "deleter": "t1_log_67a4e72ad2ccca060a2fcfb"
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


# Get Pinless Debit Conversions

Query a pinlessDebitConversions.

```php
function getPinlessDebitConversions(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): PinlessDebitConversionsResponseResult
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

[`PinlessDebitConversionsResponseResult`](../../doc/models/pinless-debit-conversions-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $pinlessDebitConversionsController->getPinlessDebitConversions(
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
        "id": "t1_pdc_684c7ec770b6d462c4cd000",
        "entity": "t1_ent_684c79a47671985f15621c0",
        "created": "2025-06-13 15:40:55.4761",
        "modified": "2025-06-13 15:43:09.6391",
        "creator": "t1_log_67a4e72ad2ccca060a2fzzz",
        "modifier": "t1_log_67a4e72ad2ccca060a2fzzz",
        "enablementDate": "2025-06-16 11:15:47",
        "org": "t1_org_684c7ae33b2d4f98520a79a",
        "division": "t1_div_684c7ae33b2d4f98520a00b",
        "partition": "t1_ptn_666834d4d504f11234578f0",
        "platform": "VCORE",
        "inactive": 1,
        "frozen": 0,
        "deleted": "2025-06-13 15:43:09",
        "deleter": "t1_log_67a4e72ad2ccca060a2fcfb"
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


# Post Pinless Debit Conversions

Create a pinlessDebitConversions.

```php
function postPinlessDebitConversions(
    PinlessDebitConversionsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): PinlessDebitConversionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PinlessDebitConversionsPostRequest`](../../doc/models/pinless-debit-conversions-post-request.md) | Body, Required | Create Pinless Debit Conversions Request. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`PinlessDebitConversionsResponseResult`](../../doc/models/pinless-debit-conversions-response-result.md)

## Example Usage

```php
$body = PinlessDebitConversionsPostRequestBuilder::init()
    ->enablementDate('2023-06-01 01:00:00')
    ->org('t1_org_684c7ae33b2d4f98520a79a')
    ->division('t1_div_684c7ae33b2d4f98520a00b')
    ->partition('t1_ptn_666834d4d504f11234578f0')
    ->platform(PinlessDebitConversionsPlatformEnum::VCORE)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->deleted('2023-06-01 01:00:00')
    ->deleter('t1_log_67a4e72ad2ccca060a2fcfb')
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $pinlessDebitConversionsController->postPinlessDebitConversions(
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
        "id": "t1_pdc_684c7ec770b6d462c4cd000",
        "entity": "t1_ent_684c79a47671985f15621c0",
        "created": "2025-06-13 15:40:55.4761",
        "modified": "2025-06-13 15:43:09.6391",
        "creator": "t1_log_67a4e72ad2ccca060a2fzzz",
        "modifier": "t1_log_67a4e72ad2ccca060a2fzzz",
        "enablementDate": "2025-06-16 11:15:47",
        "org": "t1_org_684c7ae33b2d4f98520a79a",
        "division": "t1_div_684c7ae33b2d4f98520a00b",
        "partition": "t1_ptn_666834d4d504f11234578f0",
        "platform": "VCORE",
        "inactive": 1,
        "frozen": 0,
        "deleted": "2025-06-13 15:43:09",
        "deleter": "t1_log_67a4e72ad2ccca060a2fcfb"
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

