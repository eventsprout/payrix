# Aggregation Results

```php
$aggregationResultsController = $client->getAggregationResultsController();
```

## Class Name

`AggregationResultsController`

## Methods

* [Get Aggregation Results Id](../../doc/controllers/aggregation-results.md#get-aggregation-results-id)
* [Delete Aggregation Results Id](../../doc/controllers/aggregation-results.md#delete-aggregation-results-id)
* [Get Aggregation Results](../../doc/controllers/aggregation-results.md#get-aggregation-results)


# Get Aggregation Results Id

Query an AggregationResult.

```php
function getAggregationResultsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): AggregationResultsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource or The Aggregation Result ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`AggregationResultsResponseResult`](../../doc/models/aggregation-results-response-result.md)

## Example Usage

```php
$id = 't1_art_66ebb2d6c5b4a0212c1bd00';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $aggregationResultsController->getAggregationResultsId(
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
        "id": "t1_art_66ebb2d6c5b4a0212c1bd00",
        "created": "2024-09-19 01:12:54.8110",
        "modified": "2024-09-19 01:12:54.8110",
        "creator": "t1_log_0092b50e8812b18e41d511s",
        "modifier": "t1_log_0092b50e8812b18e41d511s",
        "aggregationResultGroup": "t1_arg_66ebb2d6c50b04f8956be40",
        "field": "id",
        "count": 0,
        "sum": 0,
        "min": 0,
        "max": 0,
        "grouping": ""
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


# Delete Aggregation Results Id

Delete an Aggregation Result that holds a field totals calculated when processing an aggregation.

```php
function deleteAggregationResultsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): AggregationResultsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource or The Aggregation Result ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`AggregationResultsResponseResult`](../../doc/models/aggregation-results-response-result.md)

## Example Usage

```php
$id = 't1_art_66ebb2d6c5b4a0212c1bd00';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $aggregationResultsController->deleteAggregationResultsId(
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
        "id": "t1_art_66ebb2d6c5b4a0212c1bd00",
        "created": "2024-09-19 01:12:54.8110",
        "modified": "2024-09-19 01:12:54.8110",
        "creator": "t1_log_0092b50e8812b18e41d511s",
        "modifier": "t1_log_0092b50e8812b18e41d511s",
        "aggregationResultGroup": "t1_arg_66ebb2d6c50b04f8956be40",
        "field": "id",
        "count": 0,
        "sum": 0,
        "min": 0,
        "max": 0,
        "grouping": ""
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


# Get Aggregation Results

Query an AggregationResult resource holding field totals calculated when processing an aggregation.

```php
function getAggregationResults(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): AggregationResultsResponseResult
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

[`AggregationResultsResponseResult`](../../doc/models/aggregation-results-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $aggregationResultsController->getAggregationResults(
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
        "id": "t1_art_66ebb2d6c5b4a0212c1bd00",
        "created": "2024-09-19 01:12:54.8110",
        "modified": "2024-09-19 01:12:54.8110",
        "creator": "t1_log_0092b50e8812b18e41d511s",
        "modifier": "t1_log_0092b50e8812b18e41d511s",
        "aggregationResultGroup": "t1_arg_66ebb2d6c50b04f8956be40",
        "field": "id",
        "count": 0,
        "sum": 0,
        "min": 0,
        "max": 0,
        "grouping": ""
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

