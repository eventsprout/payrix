# Entries

An entry record represents a credit or debit of funds for an entity, possibly part of a transfer of funds between two entities. Any monetary change for an entity in Payrix Pro is recorded in an entry. This serves as a ledger of financial activity for an entity.

```php
$entriesController = $client->getEntriesController();
```

## Class Name

`EntriesController`

## Methods

* [Get Entries Id](../../doc/controllers/entries.md#get-entries-id)
* [Get Entries](../../doc/controllers/entries.md#get-entries)


# Get Entries Id

Query an Entry resource.

```php
function getEntriesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): EntriesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Entry ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`EntriesResponseResult`](../../doc/models/entries-response-result.md)

## Example Usage

```php
$id = 't1_etr_00bec0c794be4453f0af5b0';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $entriesController->getEntriesId(
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
        "id": "t1_etr_00bec0c794be4453f0af5b0",
        "created": "2025-02-26 02:20:39.6114",
        "modified": "2025-02-26 02:20:39.6114",
        "creator": "t1_log_5d13d9c20a39da6f5030426",
        "modifier": "t1_log_5d13d9c20a39da6f5030426",
        "entity": "t1_ent_60e733ce0f66e73b1b7dd5z",
        "onentity": "t1_ent_60e733ce0f66e73b1b7dd5z",
        "fromentity": "t1_ent_5cd31628c78e5ab17b6212c",
        "opposingEntry": "t1_etr_67bec0c7931a622f7b44cez",
        "fund": "t1_fun_60e738089037530645049e6",
        "fee": "t1_fee_5cd3159e7b45182f3663a6f",
        "disbursement": "Identifier Disbursement",
        "refund": "Identifier Refund",
        "txn": "Identifier Txn",
        "chargeback": "Identifier chargeback",
        "adjustment": "Adjustment Id",
        "event": 6,
        "eventId": "t1_txn_67bec0c60db89fcfa9a59b4",
        "description": "AUTH fee schedule",
        "amount": 20,
        "pending": 0,
        "profitShare": "Identifier ProfitShare",
        "originalCurrency": "USD",
        "currencyRate": 0,
        "isFee": 1,
        "statement": "Identifier Statement",
        "settlement": "Identifier Settlement",
        "archiveSummary": 0,
        "pendingEntry": "t1_per_67bec0c78fd3b8473b2564b",
        "pendingEntryCreated": "2025-02-26 02:20:39",
        "originalEventId": "t1_txn_67bec0c60db89fcfa9a59b4",
        "originalEvent": 7,
        "revShareStatement": "Identifier RevShareStatement",
        "isEFE": 0
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


# Get Entries

Query an Entry resource. An Entry resource represents a record of amounts moving in or out of the funds held by an Entity. This could be a time-based activity such as a weekly or monthly summary, or an event-based activity such as a Capture, a Payout, or a Fee. In the case of an event-based activity, the Entry contains references to the activity in the appropriate field.

```php
function getEntries(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): EntriesResponseResult
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

[`EntriesResponseResult`](../../doc/models/entries-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $entriesController->getEntries(
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
        "id": "t1_etr_00bec0c794be4453f0af5b0",
        "created": "2025-02-26 02:20:39.6114",
        "modified": "2025-02-26 02:20:39.6114",
        "creator": "t1_log_5d13d9c20a39da6f5030426",
        "modifier": "t1_log_5d13d9c20a39da6f5030426",
        "entity": "t1_ent_60e733ce0f66e73b1b7dd5z",
        "onentity": "t1_ent_60e733ce0f66e73b1b7dd5z",
        "fromentity": "t1_ent_5cd31628c78e5ab17b6212c",
        "opposingEntry": "t1_etr_67bec0c7931a622f7b44cez",
        "fund": "t1_fun_60e738089037530645049e6",
        "fee": "t1_fee_5cd3159e7b45182f3663a6f",
        "disbursement": "Identifier Disbursement",
        "refund": "Identifier Refund",
        "txn": "Identifier Txn",
        "chargeback": "Identifier chargeback",
        "adjustment": "Adjustment Id",
        "event": 6,
        "eventId": "t1_txn_67bec0c60db89fcfa9a59b4",
        "description": "AUTH fee schedule",
        "amount": 20,
        "pending": 0,
        "profitShare": "Identifier ProfitShare",
        "originalCurrency": "USD",
        "currencyRate": 0,
        "isFee": 1,
        "statement": "Identifier Statement",
        "settlement": "Identifier Settlement",
        "archiveSummary": 0,
        "pendingEntry": "t1_per_67bec0c78fd3b8473b2564b",
        "pendingEntryCreated": "2025-02-26 02:20:39",
        "originalEventId": "t1_txn_67bec0c60db89fcfa9a59b4",
        "originalEvent": 7,
        "revShareStatement": "Identifier RevShareStatement",
        "isEFE": 0
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

