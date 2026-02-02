# Chargeback Messages

```php
$chargebackMessagesController = $client->getChargebackMessagesController();
```

## Class Name

`ChargebackMessagesController`

## Methods

* [Get Chargeback Messages Id](../../doc/controllers/chargeback-messages.md#get-chargeback-messages-id)
* [Get Chargeback Messages](../../doc/controllers/chargeback-messages.md#get-chargeback-messages)
* [Post Chargeback Messages](../../doc/controllers/chargeback-messages.md#post-chargeback-messages)


# Get Chargeback Messages Id

Query a chargebackMessage. A chargebackMessage resource represents a message that is sent by a Merchant, processor, or bank in relation to a Chargeback.

```php
function getChargebackMessagesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null,
    ?string $search = null
): ChargebackMessagesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this chargeback message. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |
| `search` | `?string` | Header, Optional | Set this header to filter or sort the list of resources that the method returns.<br>See [Searches](page:welcome#searches) for detailed information and examples on how to use search header. |

## Response Type

[`ChargebackMessagesResponseResult`](../../doc/models/chargeback-messages-response-result.md)

## Example Usage

```php
$id = 't1_chm_fd94438bed7d5e80f0000ea';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$result = $chargebackMessagesController->getChargebackMessagesId(
    $id,
    $token,
    $requestToken,
    null,
    $search
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_chm_fd94438bed7d5e80f0000ea",
        "created": "2019-09-08 22:30:00.0000",
        "modified": "2019-09-08 22:30:00.0000",
        "creator": "t1_log_6564b6476c2015fa1c04ec7",
        "modifier": "t1_log_6564b6476c2015fa1c04ec7",
        "chargeback": "t1_chb_2c2443d86f1c94d3846f85b",
        "date": "20190908",
        "type": "respond",
        "fromQueue": "",
        "toQueue": "",
        "contact": "",
        "amount": 1,
        "currency": "USD",
        "note": "Charge Merchant",
        "status": "processed",
        "inactive": 0,
        "frozen": 0,
        "imported": 1
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


# Get Chargeback Messages

Query a chargebackMessage resource, which represents a message that is sent by a Merchant, processor, or bank in relation to a Chargeback.

```php
function getChargebackMessages(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): ChargebackMessagesResponseResult
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

[`ChargebackMessagesResponseResult`](../../doc/models/chargeback-messages-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $chargebackMessagesController->getChargebackMessages(
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
        "id": "t1_chm_fd94438bed7d5e80f0000ea",
        "created": "2019-09-08 22:30:00.0000",
        "modified": "2019-09-08 22:30:00.0000",
        "creator": "t1_log_6564b6476c2015fa1c04ec7",
        "modifier": "t1_log_6564b6476c2015fa1c04ec7",
        "chargeback": "t1_chb_2c2443d86f1c94d3846f85b",
        "date": "20190908",
        "type": "respond",
        "fromQueue": "",
        "toQueue": "",
        "contact": "",
        "amount": 1,
        "currency": "USD",
        "note": "Charge Merchant",
        "status": "processed",
        "inactive": 0,
        "frozen": 0,
        "imported": 1
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


# Post Chargeback Messages

Create a chargebackMessage. A chargebackMessage resource represents a message that is sent by a Merchant, processor, or bank in relation to a Chargeback.

```php
function postChargebackMessages(
    ChargebackMessagePostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): ChargebackMessagesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`ChargebackMessagePostRequest`](../../doc/models/chargeback-message-post-request.md) | Body, Required | Create Chargeback Message Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ChargebackMessagesResponseResult`](../../doc/models/chargeback-messages-response-result.md)

## Example Usage

```php
$body = ChargebackMessagePostRequestBuilder::init(
    't1_chb_2c2443d86f1c94d3846f85b',
    ChargebackMessageTypeEnum::RESPOND
)
    ->date('20190908')
    ->fromQueue('specifies queue')
    ->toQueue('specifies queue')
    ->contact('identifier of Contact')
    ->amount(1)
    ->currency(CurrencyEnum::USD)
    ->note('Charge Merchant')
    ->status(ChargebackMessageStatusEnum::PROCESSED)
    ->imported(ChargebackMessageImportedEnum::IMPORTED)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $chargebackMessagesController->postChargebackMessages(
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
        "id": "t1_chm_fd94438bed7d5e80f0000ea",
        "created": "2019-09-08 22:30:00.0000",
        "modified": "2019-09-08 22:30:00.0000",
        "creator": "t1_log_6564b6476c2015fa1c04ec7",
        "modifier": "t1_log_6564b6476c2015fa1c04ec7",
        "chargeback": "t1_chb_2c2443d86f1c94d3846f85b",
        "date": "20190908",
        "type": "respond",
        "fromQueue": "",
        "toQueue": "",
        "contact": "",
        "amount": 1,
        "currency": "USD",
        "note": "Charge Merchant",
        "status": "processed",
        "inactive": 0,
        "frozen": 0,
        "imported": 1
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

