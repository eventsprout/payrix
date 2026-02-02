# Terminal Transactions Datas

```php
$terminalTransactionsDatasController = $client->getTerminalTransactionsDatasController();
```

## Class Name

`TerminalTransactionsDatasController`

## Methods

* [Get Terminal Txns Datas Id](../../doc/controllers/terminal-transactions-datas.md#get-terminal-txns-datas-id)
* [Get Terminal Txns Datas](../../doc/controllers/terminal-transactions-datas.md#get-terminal-txns-datas)
* [Post Terminal Txns Datas](../../doc/controllers/terminal-transactions-datas.md#post-terminal-txns-datas)


# Get Terminal Txns Datas Id

Query a TerminalTxnData resource.

```php
function getTerminalTxnsDatasId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): TerminalTxnDatasResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The Terminal Transaction Data ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`TerminalTxnDatasResponseResult`](../../doc/models/terminal-txn-datas-response-result.md)

## Example Usage

```php
$id = 't1_ttd_67fd4be4e353654e911c6zz';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $terminalTransactionsDatasController->getTerminalTxnsDatasId(
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
        "id": "t1_ttd_67fd4be4e353654e911c6zz",
        "created": "2025-04-14 13:54:44.9506",
        "modified": "2025-04-14 13:54:44.9506",
        "creator": "t1_log_60ff010ead8a25392a4bb08",
        "modifier": "t1_log_60ff010ead8a25392a4bb08",
        "terminalTxn": "t1_ttx_67fd4bc0ecb91c5915f3e2e",
        "signature": "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"
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


# Get Terminal Txns Datas

Query a TerminalTxnData resource.

```php
function getTerminalTxnsDatas(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): TerminalTxnDatasResponseResult
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

[`TerminalTxnDatasResponseResult`](../../doc/models/terminal-txn-datas-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $terminalTransactionsDatasController->getTerminalTxnsDatas(
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
        "id": "t1_ttd_67fd4be4e353654e911c6zz",
        "created": "2025-04-14 13:54:44.9506",
        "modified": "2025-04-14 13:54:44.9506",
        "creator": "t1_log_60ff010ead8a25392a4bb08",
        "modifier": "t1_log_60ff010ead8a25392a4bb08",
        "terminalTxn": "t1_ttx_67fd4bc0ecb91c5915f3e2e",
        "signature": "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"
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


# Post Terminal Txns Datas

Create a TerminalTxnData resource.

```php
function postTerminalTxnsDatas(
    TerminalTxnsDatasPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): TerminalTxnDatasResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`TerminalTxnsDatasPostRequest`](../../doc/models/terminal-txns-datas-post-request.md) | Body, Required | Create Terminal Transaction Data Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`TerminalTxnDatasResponseResult`](../../doc/models/terminal-txn-datas-response-result.md)

## Example Usage

```php
$body = TerminalTxnsDatasPostRequestBuilder::init(
    't1_ttx_67fd4bc0ecb91c5915f3e2e',
    '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'
)->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $terminalTransactionsDatasController->postTerminalTxnsDatas(
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
        "id": "t1_ttd_67fd4be4e353654e911c6zz",
        "created": "2025-04-14 13:54:44.9506",
        "modified": "2025-04-14 13:54:44.9506",
        "creator": "t1_log_60ff010ead8a25392a4bb08",
        "modifier": "t1_log_60ff010ead8a25392a4bb08",
        "terminalTxn": "t1_ttx_67fd4bc0ecb91c5915f3e2e",
        "signature": "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"
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

