# Batches Settlements

```php
$batchesSettlementsController = $client->getBatchesSettlementsController();
```

## Class Name

`BatchesSettlementsController`

## Methods

* [Get Batches Id](../../doc/controllers/batches-settlements.md#get-batches-id)
* [Put Batches Id](../../doc/controllers/batches-settlements.md#put-batches-id)
* [Get Batches](../../doc/controllers/batches-settlements.md#get-batches)
* [Post Batches](../../doc/controllers/batches-settlements.md#post-batches)


# Get Batches Id

Query a Batch, a Batch resource represents a group of Transactions that are sent together to the processor to be settled.

```php
function getBatchesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): BatchesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Batch ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`BatchesResponseResult`](../../doc/models/batches-response-result.md)

## Example Usage

```php
$id = 't1_bth_67d91c7aa2aa3800cb2be00';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $batchesSettlementsController->getBatchesId(
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
        "id": "t1_bth_67d91c7aa2aa3800cb2be00",
        "created": "2025-03-18 03:10:50.6861",
        "modified": "2025-03-18 03:10:50.6861",
        "creator": "t1_log_632c5bf8960c660a1750a4a",
        "modifier": "t1_log_632c5bf8960c660a1750a4a",
        "merchant": "t1_mer_63341144b40742676bea201",
        "date": "2025-03-18",
        "platform": "VANTIV",
        "status": "open",
        "ref": "",
        "clientRef": "",
        "inactive": 0,
        "frozen": 0,
        "processingDate": "2025-03-18",
        "processingId": "",
        "closeTime": "2025-03-18 03:30:00"
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


# Put Batches Id

Update a Batch. A Batch resource represents a group of Transactions that are sent together to the processor to be settled.

```php
function putBatchesId(
    string $id,
    BatchesPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): BatchesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Batch ID. |
| `body` | [`BatchesPutRequest`](../../doc/models/batches-put-request.md) | Body, Required | Update Batch Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`BatchesResponseResult`](../../doc/models/batches-response-result.md)

## Example Usage

```php
$id = 't1_bth_67d91c7aa2aa3800cb2be00';

$body = BatchesPutRequestBuilder::init()
    ->status(BatchStatusEnum::OPEN)
    ->ref('reference code of batch')
    ->clientRef('merchant\'s reference code')
    ->processingId('Internal ID')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $batchesSettlementsController->putBatchesId(
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
        "id": "t1_bth_67d91c7aa2aa3800cb2be00",
        "created": "2025-03-18 03:10:50.6861",
        "modified": "2025-03-18 03:10:50.6861",
        "creator": "t1_log_632c5bf8960c660a1750a4a",
        "modifier": "t1_log_632c5bf8960c660a1750a4a",
        "merchant": "t1_mer_63341144b40742676bea201",
        "date": "2025-03-18",
        "platform": "VANTIV",
        "status": "open",
        "ref": "",
        "clientRef": "",
        "inactive": 0,
        "frozen": 0,
        "processingDate": "2025-03-18",
        "processingId": "",
        "closeTime": "2025-03-18 03:30:00"
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


# Get Batches

Query a Batch, which represents a group of Transactions that are sent together to the processor to be settled.

```php
function getBatches(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): BatchesResponseResult
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

[`BatchesResponseResult`](../../doc/models/batches-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $batchesSettlementsController->getBatches(
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
        "id": "t1_bth_67d91c7aa2aa3800cb2be00",
        "created": "2025-03-18 03:10:50.6861",
        "modified": "2025-03-18 03:10:50.6861",
        "creator": "t1_log_632c5bf8960c660a1750a4a",
        "modifier": "t1_log_632c5bf8960c660a1750a4a",
        "merchant": "t1_mer_63341144b40742676bea201",
        "date": "2025-03-18",
        "platform": "VANTIV",
        "status": "open",
        "ref": "",
        "clientRef": "",
        "inactive": 0,
        "frozen": 0,
        "processingDate": "2025-03-18",
        "processingId": "",
        "closeTime": "2025-03-18 03:30:00"
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


# Post Batches

Create a Batch. A Batch resource represents a group of Transactions that are sent together to the processor to be settled.

```php
function postBatches(
    BatchesPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): BatchesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`BatchesPostRequest`](../../doc/models/batches-post-request.md) | Body, Required | Create Batch Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`BatchesResponseResult`](../../doc/models/batches-response-result.md)

## Example Usage

```php
$body = BatchesPostRequestBuilder::init(
    't1_mer_63341144b40742676bea201',
    PlatformModelEnum::VANTIV
)
    ->status(BatchStatusEnum::OPEN)
    ->ref('reference code of batch')
    ->clientRef('merchant\'s reference code')
    ->processingId('Internal ID')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $batchesSettlementsController->postBatches(
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
        "id": "t1_bth_67d91c7aa2aa3800cb2be00",
        "created": "2025-03-18 03:10:50.6861",
        "modified": "2025-03-18 03:10:50.6861",
        "creator": "t1_log_632c5bf8960c660a1750a4a",
        "modifier": "t1_log_632c5bf8960c660a1750a4a",
        "merchant": "t1_mer_63341144b40742676bea201",
        "date": "2025-03-18",
        "platform": "VANTIV",
        "status": "open",
        "ref": "",
        "clientRef": "",
        "inactive": 0,
        "frozen": 0,
        "processingDate": "2025-03-18",
        "processingId": "",
        "closeTime": "2025-03-18 03:30:00"
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

