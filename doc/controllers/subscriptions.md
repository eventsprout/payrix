# Subscriptions

Resources that deal with customer subscriptions to a plan. Customers are subscribed to plans to allow for recurring payments to be made from that customer.

```php
$subscriptionsController = $client->getSubscriptionsController();
```

## Class Name

`SubscriptionsController`

## Methods

* [Get Subscriptions Id](../../doc/controllers/subscriptions.md#get-subscriptions-id)
* [Put Subscriptions Id](../../doc/controllers/subscriptions.md#put-subscriptions-id)
* [Delete Subscriptions Id](../../doc/controllers/subscriptions.md#delete-subscriptions-id)
* [Get Subscriptions](../../doc/controllers/subscriptions.md#get-subscriptions)
* [Post Subscriptions](../../doc/controllers/subscriptions.md#post-subscriptions)


# Get Subscriptions Id

Query a Subscription that specifies both starting and ending dates and charges the customer according to the schedule in the associated Plan during the interval between these dates.

```php
function getSubscriptionsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): SubscriptionResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this subscription. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`SubscriptionResponseResult`](../../doc/models/subscription-response-result.md)

## Example Usage

```php
$id = 't1_sbn_680064d2db9dbdc8d3e9a0z';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $subscriptionsController->getSubscriptionsId(
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
        "id": "t1_sbn_680064d2db9dbdc8d3e9a0z",
        "created": "2025-04-16 22:17:54.9157",
        "modified": "2025-04-16 22:17:57.0415",
        "creator": "t1_log_653ae6ec24a9357ace75ebf",
        "modifier": "t1_log_65e23f228adad41b7a2a0a9",
        "plan": "t1_pln_680064c9e9920768c5f7156",
        "start": 20250416,
        "finish": 20250416,
        "tax": 0,
        "descriptor": "",
        "inactive": 0,
        "frozen": 0,
        "failures": 0,
        "maxFailures": 0,
        "origin": 2,
        "firstTxn": "t1_txn_680064d333e8a4e6cc85903",
        "txnDescription": "subscription1",
        "order": "t183l8nsmsiq",
        "authentication": "",
        "authenticationId": "",
        "statementEntity": ""
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


# Put Subscriptions Id

Update a Subscription, A Subscription specifies both starting and ending dates and the customer is charged according to the schedule in the associated Plan during the interval between these dates.

```php
function putSubscriptionsId(
    string $id,
    SubscriptionsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): SubscriptionResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this subscription. |
| `body` | [`SubscriptionsPutRequest`](../../doc/models/subscriptions-put-request.md) | Body, Required | Update Subscription Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`SubscriptionResponseResult`](../../doc/models/subscription-response-result.md)

## Example Usage

```php
$id = 't1_sbn_680064d2db9dbdc8d3e9a0z';

$body = SubscriptionsPutRequestBuilder::init()
    ->plan('t1_pln_680064c9e9920768c5f7156')
    ->statementEntity('paying entity')
    ->firstTxn('t1_txn_680064d333e8a4e6cc85903')
    ->start(20250416)
    ->finish(20250416)
    ->tax(0)
    ->descriptor('Subscription Descriptor')
    ->txnDescription('subscription1')
    ->order('t183l8nsmsiq')
    ->origin(SubscriptionOriginEnum::ECOMMERCE)
    ->authentication('Authentication token')
    ->authenticationId('Authentication reference ID')
    ->failures(0)
    ->maxFailures(0)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $subscriptionsController->putSubscriptionsId(
    $id,
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
        "id": "t1_sbn_680064d2db9dbdc8d3e9a0z",
        "created": "2025-04-16 22:17:54.9157",
        "modified": "2025-04-16 22:17:57.0415",
        "creator": "t1_log_653ae6ec24a9357ace75ebf",
        "modifier": "t1_log_65e23f228adad41b7a2a0a9",
        "plan": "t1_pln_680064c9e9920768c5f7156",
        "start": 20250416,
        "finish": 20250416,
        "tax": 0,
        "descriptor": "",
        "inactive": 0,
        "frozen": 0,
        "failures": 0,
        "maxFailures": 0,
        "origin": 2,
        "firstTxn": "t1_txn_680064d333e8a4e6cc85903",
        "txnDescription": "subscription1",
        "order": "t183l8nsmsiq",
        "authentication": "",
        "authenticationId": "",
        "statementEntity": ""
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


# Delete Subscriptions Id

Delete a Subscription. A Subscription is a scheduled invocation of a particular Plan over a certain period of time, specifying both starting and ending dates, and the customer is charged according to the schedule in the associated Plan during the interval between these dates.

```php
function deleteSubscriptionsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): SubscriptionResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this subscription. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`SubscriptionResponseResult`](../../doc/models/subscription-response-result.md)

## Example Usage

```php
$id = 't1_sbn_680064d2db9dbdc8d3e9a0z';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $subscriptionsController->deleteSubscriptionsId(
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
        "id": "t1_sbn_680064d2db9dbdc8d3e9a0z",
        "created": "2025-04-16 22:17:54.9157",
        "modified": "2025-04-16 22:17:57.0415",
        "creator": "t1_log_653ae6ec24a9357ace75ebf",
        "modifier": "t1_log_65e23f228adad41b7a2a0a9",
        "plan": "t1_pln_680064c9e9920768c5f7156",
        "start": 20250416,
        "finish": 20250416,
        "tax": 0,
        "descriptor": "",
        "inactive": 0,
        "frozen": 0,
        "failures": 0,
        "maxFailures": 0,
        "origin": 2,
        "firstTxn": "t1_txn_680064d333e8a4e6cc85903",
        "txnDescription": "subscription1",
        "order": "t183l8nsmsiq",
        "authentication": "",
        "authenticationId": "",
        "statementEntity": ""
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


# Get Subscriptions

Query a Subscription.
A Subscription is a scheduled invocation of a particular Plan over a certain period of time.
A Subscription specifies both starting and ending dates and the customer is charged according to the schedule in the associated Plan during the interval between these dates.

```php
function getSubscriptions(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): SubscriptionResponseResult
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

[`SubscriptionResponseResult`](../../doc/models/subscription-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $subscriptionsController->getSubscriptions(
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
        "id": "t1_sbn_680064d2db9dbdc8d3e9a0z",
        "created": "2025-04-16 22:17:54.9157",
        "modified": "2025-04-16 22:17:57.0415",
        "creator": "t1_log_653ae6ec24a9357ace75ebf",
        "modifier": "t1_log_65e23f228adad41b7a2a0a9",
        "plan": "t1_pln_680064c9e9920768c5f7156",
        "start": 20250416,
        "finish": 20250416,
        "tax": 0,
        "descriptor": "",
        "inactive": 0,
        "frozen": 0,
        "failures": 0,
        "maxFailures": 0,
        "origin": 2,
        "firstTxn": "t1_txn_680064d333e8a4e6cc85903",
        "txnDescription": "subscription1",
        "order": "t183l8nsmsiq",
        "authentication": "",
        "authenticationId": "",
        "statementEntity": ""
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


# Post Subscriptions

Create a Subscription.
A Subscription is a scheduled invocation of a particular Plan over a certain period of time.
A Subscription specifies both starting and ending dates and the customer is charged according to the schedule in the associated Plan during the interval between these dates.

```php
function postSubscriptions(
    SubscriptionsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): SubscriptionResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SubscriptionsPostRequest`](../../doc/models/subscriptions-post-request.md) | Body, Required | Create Subscription Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`SubscriptionResponseResult`](../../doc/models/subscription-response-result.md)

## Example Usage

```php
$body = SubscriptionsPostRequestBuilder::init(
    't1_pln_680064c9e9920768c5f7156',
    20250416,
    'Authentication token',
    0
)
    ->statementEntity('paying entity')
    ->firstTxn('t1_txn_680064d333e8a4e6cc85903')
    ->finish(20250416)
    ->tax(0)
    ->descriptor('Subscription Descriptor')
    ->txnDescription('subscription1')
    ->order('t183l8nsmsiq')
    ->origin(SubscriptionOriginEnum::ECOMMERCE)
    ->authenticationId('Authentication reference ID')
    ->maxFailures(0)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $subscriptionsController->postSubscriptions(
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
        "id": "t1_sbn_680064d2db9dbdc8d3e9a0z",
        "created": "2025-04-16 22:17:54.9157",
        "modified": "2025-04-16 22:17:57.0415",
        "creator": "t1_log_653ae6ec24a9357ace75ebf",
        "modifier": "t1_log_65e23f228adad41b7a2a0a9",
        "plan": "t1_pln_680064c9e9920768c5f7156",
        "start": 20250416,
        "finish": 20250416,
        "tax": 0,
        "descriptor": "",
        "inactive": 0,
        "frozen": 0,
        "failures": 0,
        "maxFailures": 0,
        "origin": 2,
        "firstTxn": "t1_txn_680064d333e8a4e6cc85903",
        "txnDescription": "subscription1",
        "order": "t183l8nsmsiq",
        "authentication": "",
        "authenticationId": "",
        "statementEntity": ""
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

