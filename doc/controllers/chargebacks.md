# Chargebacks

Resources that deal with chargebacks. A chargeback is a dispute of a purchase that has already been charged to an account that can result in a return of funds.

```php
$chargebacksController = $client->getChargebacksController();
```

## Class Name

`ChargebacksController`

## Methods

* [Get Chargebacks Id](../../doc/controllers/chargebacks.md#get-chargebacks-id)
* [Get Chargebacks](../../doc/controllers/chargebacks.md#get-chargebacks)


# Get Chargebacks Id

Query a Chargeback. A Chargeback is the reversal of a Transaction and means that the funds have been returned to their source. The resource for a Chargeback gives details of the Chargeback, including the reason why it occurred and the date when it occurred.

```php
function getChargebacksId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): ChargebacksResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of the Chargeback. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`ChargebacksResponseResult`](../../doc/models/chargebacks-response-result.md)

## Example Usage

```php
$id = 't1_chb_678e573098a7706d87b45c1';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $chargebacksController->getChargebacksId(
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
        "id": "t1_chb_678e573098a7706d87b45c1",
        "created": "2025-01-20 09:01:20.6435",
        "modified": "2025-01-20 09:09:33.7798",
        "creator": "t1_log_6564b6476c2015fa1c08th9",
        "modifier": "t1_log_6564b6476c2015fa1c08th9",
        "merchant": "t1_mer_66a7dcc35e03d452faa32dc",
        "txn": "t1_txn_678e56d221e81b116dbb452",
        "mid": "01242567",
        "description": "Chargeback for the txn of $200,000",
        "total": 20000,
        "representedTotal": 20000,
        "cycle": "first",
        "currency": "USD",
        "platform": "VANTIV",
        "paymentMethod": 1,
        "ref": "6574367",
        "reason": "No Cardholder Authorization",
        "reasonCode": "4837",
        "issued": 20140815,
        "received": 20140815,
        "reply": 20140919,
        "bankRef": "6574367",
        "chargebackRef": "6574367",
        "status": "open",
        "lastStatusChange": "6574367",
        "actionable": 1,
        "shadow": 0,
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


# Get Chargebacks

Query Chargebacks. A Chargeback is the reversal of a Transaction, meaning that the funds have been returned to their source. The resource for each Chargeback gives details of the Chargeback, including the reason why it occurred and the date when it occurred.

```php
function getChargebacks(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): ChargebacksResponseResult
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

[`ChargebacksResponseResult`](../../doc/models/chargebacks-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $chargebacksController->getChargebacks(
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
        "id": "t1_chb_678e573098a7706d87b45c1",
        "created": "2025-01-20 09:01:20.6435",
        "modified": "2025-01-20 09:09:33.7798",
        "creator": "t1_log_6564b6476c2015fa1c08th9",
        "modifier": "t1_log_6564b6476c2015fa1c08th9",
        "merchant": "t1_mer_66a7dcc35e03d452faa32dc",
        "txn": "t1_txn_678e56d221e81b116dbb452",
        "mid": "01242567",
        "description": "Chargeback for the txn of $200,000",
        "total": 20000,
        "representedTotal": 20000,
        "cycle": "first",
        "currency": "USD",
        "platform": "VANTIV",
        "paymentMethod": 1,
        "ref": "6574367",
        "reason": "No Cardholder Authorization",
        "reasonCode": "4837",
        "issued": 20140815,
        "received": 20140815,
        "reply": 20140919,
        "bankRef": "6574367",
        "chargebackRef": "6574367",
        "status": "open",
        "lastStatusChange": "6574367",
        "actionable": 1,
        "shadow": 0,
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

