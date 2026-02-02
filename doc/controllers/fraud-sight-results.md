# Fraud Sight Results

```php
$fraudSightResultsController = $client->getFraudSightResultsController();
```

## Class Name

`FraudSightResultsController`

## Methods

* [Get Fraud Sight Results Id](../../doc/controllers/fraud-sight-results.md#get-fraud-sight-results-id)
* [Get Fraud Sight Results](../../doc/controllers/fraud-sight-results.md#get-fraud-sight-results)


# Get Fraud Sight Results Id

Query a fraudSightResults.

```php
function getFraudSightResultsId(
    string $id,
    ?string $requestToken = null,
    ?string $embed = null
): FraudSightResultsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this Fraud Sight Results. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`FraudSightResultsResponseResult`](../../doc/models/fraud-sight-results-response-result.md)

## Example Usage

```php
$id = 't1_vfr_67ea5cb2c4be3c25dbc1zz0';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $fraudSightResultsController->getFraudSightResultsId(
    $id,
    $requestToken
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_vfr_67ea5cb2c4be3c25dbc1zz0",
        "created": "2025-03-31 05:13:22.8143",
        "modified": "2025-03-31 05:13:22.9880",
        "creator": "t1_log_6705400bf224a9c0b4ee098",
        "modifier": "t1_log_6705400bf224a9c0b4ee098",
        "status": 0,
        "originalStatus": "pass",
        "txn": "t1_txn_678e56d221e81b116dbb452",
        "score": 988
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


# Get Fraud Sight Results

Query a fraudSightResults.

```php
function getFraudSightResults(
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): FraudSightResultsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `search` | `?string` | Header, Optional | Set this header to filter or sort the list of resources that the method returns.<br>See [Searches](page:welcome#searches) for detailed information and examples on how to use search header. |
| `totals` | `?string` | Header, Optional | To configure a request to return a total for all instances of a field in a result set,  use the totals header in the format `totals={operator}[]={key}`.  This will calculate the desired total and return it in the `details > totals` object of the response.  For instance, if you want to sum the `total` field of all transactions,  you would use the `sum` operator. The response will include the result set,  along with the calculated total in the `details` section. See [Collection Operators](page:welcome#collection-operators) for detailed information and examples on how to use totals header. |
| `pageNumber` | `?int` | Query, Optional | Set this path parameter to request a specific page of records.<br>For example, set `?page[number]=2` to retrieve the second page of records for this request. |
| `pageLimit` | `?int` | Query, Optional | Set this path parameter to request up to a specific amount of records. By default 30 records are retrieved per page. The maximum limit that can be set is 100.<br>For example, set `?page[limit]=50` to retrieve up to 50 records for this request. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`FraudSightResultsResponseResult`](../../doc/models/fraud-sight-results-response-result.md)

## Example Usage

```php
$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $fraudSightResultsController->getFraudSightResults(
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
        "id": "t1_vfr_67ea5cb2c4be3c25dbc1zz0",
        "created": "2025-03-31 05:13:22.8143",
        "modified": "2025-03-31 05:13:22.9880",
        "creator": "t1_log_6705400bf224a9c0b4ee098",
        "modifier": "t1_log_6705400bf224a9c0b4ee098",
        "status": 0,
        "originalStatus": "pass",
        "txn": "t1_txn_678e56d221e81b116dbb452",
        "score": 988
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

