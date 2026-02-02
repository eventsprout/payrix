# Disbursement Entries

```php
$disbursementEntriesController = $client->getDisbursementEntriesController();
```

## Class Name

`DisbursementEntriesController`

## Methods

* [Get Disbursement Entries Id](../../doc/controllers/disbursement-entries.md#get-disbursement-entries-id)
* [Get Disbursement Entries](../../doc/controllers/disbursement-entries.md#get-disbursement-entries)


# Get Disbursement Entries Id

Query a Disbursement Entry that is a record of where a disbursement amount is coming from.

```php
function getDisbursementEntriesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): DisbursementEntriesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this disbursement entry. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`DisbursementEntriesResponseResult`](../../doc/models/disbursement-entries-response-result.md)

## Example Usage

```php
$id = 't1_dbe_672ebb36f08a2a1a6ecfdce';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $disbursementEntriesController->getDisbursementEntriesId(
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
        "id": "t1_dbe_672ebb36f08a2a1a6ecfdce",
        "created": "2024-11-11 12:03:56.5234",
        "modified": "2024-11-11 12:03:56.5234",
        "creator": "t1_log_5ed514b7edbf6f641b7c2f2",
        "modifier": "t1_log_5ed514b7edbf6f641b7c2f2",
        "disbursement": "t1_dbm_672e2fa70f484124eed2fdf",
        "entry": "t1_etr_672d7ed5ec259204656ab73",
        "pendingEntry": "t1_per_67b4fgt67uc4cf30f44fea5",
        "reserveEntry": "t1_rer_67bgh6797dbafac6fd255c0",
        "event": 40,
        "eventId": "t1_txn_672cc0c41a79e0c85240983",
        "amount": 51,
        "amountUsed": 0,
        "description": "Remaining available funds not disbursed in this disbursement"
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


# Get Disbursement Entries

Query DisbursementEntries to get records of where each disbursement amount is coming from.

```php
function getDisbursementEntries(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): DisbursementEntriesResponseResult
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

[`DisbursementEntriesResponseResult`](../../doc/models/disbursement-entries-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $disbursementEntriesController->getDisbursementEntries(
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
        "id": "t1_dbe_672ebb36f08a2a1a6ecfdce",
        "created": "2024-11-11 12:03:56.5234",
        "modified": "2024-11-11 12:03:56.5234",
        "creator": "t1_log_5ed514b7edbf6f641b7c2f2",
        "modifier": "t1_log_5ed514b7edbf6f641b7c2f2",
        "disbursement": "t1_dbm_672e2fa70f484124eed2fdf",
        "entry": "t1_etr_672d7ed5ec259204656ab73",
        "pendingEntry": "t1_per_67b4fgt67uc4cf30f44fea5",
        "reserveEntry": "t1_rer_67bgh6797dbafac6fd255c0",
        "event": 40,
        "eventId": "t1_txn_672cc0c41a79e0c85240983",
        "amount": 51,
        "amountUsed": 0,
        "description": "Remaining available funds not disbursed in this disbursement"
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

