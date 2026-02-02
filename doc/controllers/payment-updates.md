# Payment Updates

```php
$paymentUpdatesController = $client->getPaymentUpdatesController();
```

## Class Name

`PaymentUpdatesController`

## Methods

* [Get Payment Updates Id](../../doc/controllers/payment-updates.md#get-payment-updates-id)
* [Get Payment Updates](../../doc/controllers/payment-updates.md#get-payment-updates)


# Get Payment Updates Id

_CONFLICT Query a Payment Update that holds information about the payment update, related to a payment, subscriptionToken or account, and owned by a paymentUpdateGroup.

```php
function getPaymentUpdatesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): PaymentUpdatesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this payment update. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`PaymentUpdatesResponseResult`](../../doc/models/payment-updates-response-result.md)

## Example Usage

```php
$id = 't1_pmu_67c80c49a8274b15ad4dd0z';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $paymentUpdatesController->getPaymentUpdatesId(
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
        "id": "t1_pmu_67c80c49a8274b15ad4dd0z",
        "created": "2025-03-05 03:33:13.7279",
        "modified": "2025-03-05 03:33:13.7279",
        "creator": "t1_log_6760a3141b9bbb0c77f0000",
        "modifier": "t1_log_6760a3141b9bbb0c77f0000",
        "paymentUpdateGroup": "t1_pug_67c80c1f44bc3a7dcb1f000",
        "status": "processed",
        "token": "t1_tok_67c5809c7dfcff7ac57955z",
        "account": "t1_act_67aafff2c40a8cecf5cb000",
        "platform": "VANTIV",
        "ref": "12345678901234",
        "clientRef": "04315629",
        "message": "Account was closed",
        "expiration": "1030"
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


# Get Payment Updates

Query a PaymentUpdate.
A PaymentUpdate holds information about the payment update. The paymentUpdate will be related to a payment, subscriptionToken or account, and owned by a paymentUpdateGroup.

```php
function getPaymentUpdates(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): PaymentUpdatesResponseResult
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

[`PaymentUpdatesResponseResult`](../../doc/models/payment-updates-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $paymentUpdatesController->getPaymentUpdates(
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
        "id": "t1_pmu_67c80c49a8274b15ad4dd0z",
        "created": "2025-03-05 03:33:13.7279",
        "modified": "2025-03-05 03:33:13.7279",
        "creator": "t1_log_6760a3141b9bbb0c77f0000",
        "modifier": "t1_log_6760a3141b9bbb0c77f0000",
        "paymentUpdateGroup": "t1_pug_67c80c1f44bc3a7dcb1f000",
        "status": "processed",
        "token": "t1_tok_67c5809c7dfcff7ac57955z",
        "account": "t1_act_67aafff2c40a8cecf5cb000",
        "platform": "VANTIV",
        "ref": "12345678901234",
        "clientRef": "04315629",
        "message": "Account was closed",
        "expiration": "1030"
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

