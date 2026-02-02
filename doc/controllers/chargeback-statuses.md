# Chargeback Statuses

```php
$chargebackStatusesController = $client->getChargebackStatusesController();
```

## Class Name

`ChargebackStatusesController`

## Methods

* [Get Chargeback Statuses Id](../../doc/controllers/chargeback-statuses.md#get-chargeback-statuses-id)
* [Get Chargeback Statuses](../../doc/controllers/chargeback-statuses.md#get-chargeback-statuses)


# Get Chargeback Statuses Id

Query ChargebackStatuses. A ChargebackStatuses is the logged status changes of a Chargeback, The resource for each Chargeback gives details of the Chargeback, including the reason why it occurred and the date when it occurred.

```php
function getChargebackStatusesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): ChargebackStatusesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The Chargeback Status ID of this resource. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`ChargebackStatusesResponseResult`](../../doc/models/chargeback-statuses-response-result.md)

## Example Usage

```php
$id = 'p1_chs_00cf194e96237dd16d0c1e4';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $chargebackStatusesController->getChargebackStatusesId(
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
        "id": "p1_chs_00cf1bdcc576991ce254cdc",
        "created": "2025-03-10 13:05:32.8335",
        "modified": "2025-03-10 13:05:32.8335",
        "creator": "p1_log_00b869779727da108515d99",
        "modifier": "p1_log_00b869779727da108515d99",
        "chargeback": "p1_chb_00c9d0176c29c1e85e2ad4e",
        "chargebackMessage": "p1_chm_67cf1bdc44026cc766d0793",
        "status": "open"
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


# Get Chargeback Statuses

Query ChargebackStatuses. A ChargebackStatuses is the logged status changes of a Chargeback; The resource for each Chargeback gives details of the Chargeback, including the reason why it occurred and the date when it occurred.

```php
function getChargebackStatuses(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): ChargebackStatusesResponseResult
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

[`ChargebackStatusesResponseResult`](../../doc/models/chargeback-statuses-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $chargebackStatusesController->getChargebackStatuses(
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
        "id": "p1_chs_00cf1bdcc576991ce254cdc",
        "created": "2025-03-10 13:05:32.8335",
        "modified": "2025-03-10 13:05:32.8335",
        "creator": "p1_log_00b869779727da108515d99",
        "modifier": "p1_log_00b869779727da108515d99",
        "chargeback": "p1_chb_00c9d0176c29c1e85e2ad4e",
        "chargebackMessage": "p1_chm_67cf1bdc44026cc766d0793",
        "status": "open"
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

