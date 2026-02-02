# Entity Returns

```php
$entityReturnsController = $client->getEntityReturnsController();
```

## Class Name

`EntityReturnsController`

## Methods

* [Get Entity Returns Id](../../doc/controllers/entity-returns.md#get-entity-returns-id)
* [Get Entity Returns](../../doc/controllers/entity-returns.md#get-entity-returns)


# Get Entity Returns Id

Query an EntityReturn represents an ACH transaction or disbursement that has been rejected, which will block ACH creations or send out related to its entity and payment.

```php
function getEntityReturnsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): EntityReturnsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this entity return. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`EntityReturnsResponseResult`](../../doc/models/entity-returns-response-result.md)

## Example Usage

```php
$id = 't1_ern_67c9b2996c2944b0ffc9090';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $entityReturnsController->getEntityReturnsId(
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
        "id": "t1_ern_67c9b2996c2944b0ffc9090",
        "created": "2025-03-06 09:35:05.4506",
        "modified": "2025-03-06 09:35:05.4506",
        "creator": "t1_log_5f875c53ed397f57c0afc90",
        "modifier": "t1_log_5f875c53ed397f57c0afc90",
        "login": "t1_log_5f875c53ed397f57c0afc90",
        "entity": "t1_ent_00177a051ae2b52697fe015",
        "txn": "t1_txn_89c9afa2d319e6c23540104",
        "disbursement": "",
        "actionCode": "badAccount",
        "code": "R03",
        "message": "Unable to locate account or no account",
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


# Get Entity Returns

Query an EntityReturn represents an ACH transaction or disbursement that has been rejected. The EntityReturn will block ACH creations or send out related to its entity and payment.

```php
function getEntityReturns(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): EntityReturnsResponseResult
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

[`EntityReturnsResponseResult`](../../doc/models/entity-returns-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $entityReturnsController->getEntityReturns(
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
        "id": "t1_ern_67c9b2996c2944b0ffc9090",
        "created": "2025-03-06 09:35:05.4506",
        "modified": "2025-03-06 09:35:05.4506",
        "creator": "t1_log_5f875c53ed397f57c0afc90",
        "modifier": "t1_log_5f875c53ed397f57c0afc90",
        "login": "t1_log_5f875c53ed397f57c0afc90",
        "entity": "t1_ent_00177a051ae2b52697fe015",
        "txn": "t1_txn_89c9afa2d319e6c23540104",
        "disbursement": "",
        "actionCode": "badAccount",
        "code": "R03",
        "message": "Unable to locate account or no account",
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

