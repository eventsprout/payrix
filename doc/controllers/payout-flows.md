# Payout Flows

```php
$payoutFlowsController = $client->getPayoutFlowsController();
```

## Class Name

`PayoutFlowsController`

## Methods

* [Get Payout Flows Id](../../doc/controllers/payout-flows.md#get-payout-flows-id)
* [Put Payout Flows Id](../../doc/controllers/payout-flows.md#put-payout-flows-id)
* [Delete Payout Flows Id](../../doc/controllers/payout-flows.md#delete-payout-flows-id)
* [Get Payout Flows](../../doc/controllers/payout-flows.md#get-payout-flows)
* [Post Payout Flows](../../doc/controllers/payout-flows.md#post-payout-flows)


# Get Payout Flows Id

Query a payoutFlows resource.
A payoutFlows resource represents a way to set up a Payouts resource automatically for an Entity or Org when it is boarded, or when a bank account is associated.
You can set up the schedule and amount for the Payouts in the payoutFlows resource.

```php
function getPayoutFlowsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): PayoutFlowsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this payout flow. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`PayoutFlowsResponseResult`](../../doc/models/payout-flows-response-result.md)

## Example Usage

```php
$id = 't1_pfw_67e2ff129aad30995408a00';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $payoutFlowsController->getPayoutFlowsId(
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
        "id": "t1_pfw_67e2ff129aad30995408a00",
        "created": "2025-03-25 15:08:02.6559",
        "modified": "2025-03-25 15:08:02.6559",
        "creator": "t1_log_673245a79517f80bf2e7738",
        "modifier": "t1_log_673245a79517f80bf2e7738",
        "login": "t1_log_673245a79517f80bf2e7738",
        "payoutLogin": "",
        "org": "t1_org_67b8f82d4f96c5a520ef5c8",
        "entity": "p1_ent_00ce6d2c1f773f68e9cbe00",
        "trigger": "board",
        "schedule": "weeks",
        "scheduleFactor": 1,
        "um": "percent",
        "amount": 10000,
        "minimum": 5000,
        "payoutInactive": 0,
        "skipOffDays": 1,
        "inactive": 0,
        "frozen": 0,
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_006834d4d504f11234578f0",
        "secondaryDescriptor": "",
        "billing": "t1_bil_67d9c8a7df33cf77a3e5e0z",
        "start": 20160120,
        "currency": "USD",
        "sameDay": 0
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


# Put Payout Flows Id

Update a payoutFlows resource that represents a way to set up a Payouts resource automatically for an Entity or Org when it is boarded, or when a bank account is associated, allowing you to set up the schedule and amount for the Payouts in the payoutFlows resource.

```php
function putPayoutFlowsId(
    string $id,
    PayoutFlowsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): PayoutFlowsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this payout flow. |
| `body` | [`PayoutFlowsPutRequest`](../../doc/models/payout-flows-put-request.md) | Body, Required | Update Payout Flow Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`PayoutFlowsResponseResult`](../../doc/models/payout-flows-response-result.md)

## Example Usage

```php
$id = 't1_pfw_67e2ff129aad30995408a00';

$body = PayoutFlowsPutRequestBuilder::init()
    ->login('t1_log_673245a79517f80bf2e7738')
    ->payoutLogin('payoutLogin')
    ->org('t1_org_67b8f82d4f96c5a520ef5c8')
    ->entity('p1_ent_00ce6d2c1f773f68e9cbe00')
    ->billing('t1_bil_67d9c8a7df33cf77a3e5e0z')
    ->trigger(PayoutFlowTriggerEnum::BOARD)
    ->schedule(PayoutFlowScheduleEnum::WEEKS)
    ->scheduleFactor(1)
    ->start(20160120)
    ->um(PayoutFlowUmEnum::PERCENT)
    ->amount(10000)
    ->minimum(5000)
    ->payoutInactive(PayoutInactiveEnum::INACTIVE)
    ->skipOffDays(PayoutFlowsSkipOffDaysEnum::DONOTSKIP)
    ->secondaryDescriptor('Wellness')
    ->currency(CurrencyEnum::USD)
    ->sameDay(PayoutFlowsSameDayEnum::DISABLED)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $payoutFlowsController->putPayoutFlowsId(
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
        "id": "t1_pfw_67e2ff129aad30995408a00",
        "created": "2025-03-25 15:08:02.6559",
        "modified": "2025-03-25 15:08:02.6559",
        "creator": "t1_log_673245a79517f80bf2e7738",
        "modifier": "t1_log_673245a79517f80bf2e7738",
        "login": "t1_log_673245a79517f80bf2e7738",
        "payoutLogin": "",
        "org": "t1_org_67b8f82d4f96c5a520ef5c8",
        "entity": "p1_ent_00ce6d2c1f773f68e9cbe00",
        "trigger": "board",
        "schedule": "weeks",
        "scheduleFactor": 1,
        "um": "percent",
        "amount": 10000,
        "minimum": 5000,
        "payoutInactive": 0,
        "skipOffDays": 1,
        "inactive": 0,
        "frozen": 0,
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_006834d4d504f11234578f0",
        "secondaryDescriptor": "",
        "billing": "t1_bil_67d9c8a7df33cf77a3e5e0z",
        "start": 20160120,
        "currency": "USD",
        "sameDay": 0
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


# Delete Payout Flows Id

Delete a payoutFlows resource that represents a way to set up a Payouts resource automatically for an Entity or Org when it is boarded, or when a bank account is associated, allowing you to set up the schedule and amount for the Payouts in the payoutFlows resource.

```php
function deletePayoutFlowsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): PayoutFlowsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this payout flow. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`PayoutFlowsResponseResult`](../../doc/models/payout-flows-response-result.md)

## Example Usage

```php
$id = 't1_pfw_67e2ff129aad30995408a00';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $payoutFlowsController->deletePayoutFlowsId(
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
        "id": "t1_pfw_67e2ff129aad30995408a00",
        "created": "2025-03-25 15:08:02.6559",
        "modified": "2025-03-25 15:08:02.6559",
        "creator": "t1_log_673245a79517f80bf2e7738",
        "modifier": "t1_log_673245a79517f80bf2e7738",
        "login": "t1_log_673245a79517f80bf2e7738",
        "payoutLogin": "",
        "org": "t1_org_67b8f82d4f96c5a520ef5c8",
        "entity": "p1_ent_00ce6d2c1f773f68e9cbe00",
        "trigger": "board",
        "schedule": "weeks",
        "scheduleFactor": 1,
        "um": "percent",
        "amount": 10000,
        "minimum": 5000,
        "payoutInactive": 0,
        "skipOffDays": 1,
        "inactive": 0,
        "frozen": 0,
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_006834d4d504f11234578f0",
        "secondaryDescriptor": "",
        "billing": "t1_bil_67d9c8a7df33cf77a3e5e0z",
        "start": 20160120,
        "currency": "USD",
        "sameDay": 0
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


# Get Payout Flows

Query a payoutFlows resource.
A payoutFlows resource represents a way to set up a Payouts resource automatically for an Entity or Org when it is boarded, or when a bank account is associated.
You can set up the schedule and amount for the Payouts in the payoutFlows resource.

```php
function getPayoutFlows(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): PayoutFlowsResponseResult
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

[`PayoutFlowsResponseResult`](../../doc/models/payout-flows-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $payoutFlowsController->getPayoutFlows(
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
        "id": "t1_pfw_67e2ff129aad30995408a00",
        "created": "2025-03-25 15:08:02.6559",
        "modified": "2025-03-25 15:08:02.6559",
        "creator": "t1_log_673245a79517f80bf2e7738",
        "modifier": "t1_log_673245a79517f80bf2e7738",
        "login": "t1_log_673245a79517f80bf2e7738",
        "payoutLogin": "",
        "org": "t1_org_67b8f82d4f96c5a520ef5c8",
        "entity": "p1_ent_00ce6d2c1f773f68e9cbe00",
        "trigger": "board",
        "schedule": "weeks",
        "scheduleFactor": 1,
        "um": "percent",
        "amount": 10000,
        "minimum": 5000,
        "payoutInactive": 0,
        "skipOffDays": 1,
        "inactive": 0,
        "frozen": 0,
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_006834d4d504f11234578f0",
        "secondaryDescriptor": "",
        "billing": "t1_bil_67d9c8a7df33cf77a3e5e0z",
        "start": 20160120,
        "currency": "USD",
        "sameDay": 0
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


# Post Payout Flows

Create a payoutFlows resource.
A payoutFlows resource represents a way to set up a Payouts resource automatically for an Entity or Org when it is boarded, or when a bank account is associated.
You can set up the schedule and amount for the Payouts in the payoutFlows resource.

```php
function postPayoutFlows(
    PayoutFlowsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): PayoutFlowsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PayoutFlowsPostRequest`](../../doc/models/payout-flows-post-request.md) | Body, Required | Create Payout Flow Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`PayoutFlowsResponseResult`](../../doc/models/payout-flows-response-result.md)

## Example Usage

```php
$body = PayoutFlowsPostRequestBuilder::init(
    't1_log_673245a79517f80bf2e7738',
    PayoutFlowTriggerEnum::BOARD
)
    ->payoutLogin('payoutLogin')
    ->org('t1_org_67b8f82d4f96c5a520ef5c8')
    ->entity('p1_ent_00ce6d2c1f773f68e9cbe00')
    ->billing('t1_bil_67d9c8a7df33cf77a3e5e0z')
    ->schedule(PayoutFlowScheduleEnum::WEEKS)
    ->scheduleFactor(1)
    ->start(20160120)
    ->um(PayoutFlowUmEnum::PERCENT)
    ->amount(10000)
    ->minimum(5000)
    ->payoutInactive(PayoutInactiveEnum::INACTIVE)
    ->skipOffDays(PayoutFlowsSkipOffDaysEnum::DONOTSKIP)
    ->secondaryDescriptor('Wellness')
    ->currency(CurrencyEnum::USD)
    ->sameDay(PayoutFlowsSameDayEnum::DISABLED)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $payoutFlowsController->postPayoutFlows(
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
        "id": "t1_pfw_67e2ff129aad30995408a00",
        "created": "2025-03-25 15:08:02.6559",
        "modified": "2025-03-25 15:08:02.6559",
        "creator": "t1_log_673245a79517f80bf2e7738",
        "modifier": "t1_log_673245a79517f80bf2e7738",
        "login": "t1_log_673245a79517f80bf2e7738",
        "payoutLogin": "",
        "org": "t1_org_67b8f82d4f96c5a520ef5c8",
        "entity": "p1_ent_00ce6d2c1f773f68e9cbe00",
        "trigger": "board",
        "schedule": "weeks",
        "scheduleFactor": 1,
        "um": "percent",
        "amount": 10000,
        "minimum": 5000,
        "payoutInactive": 0,
        "skipOffDays": 1,
        "inactive": 0,
        "frozen": 0,
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_006834d4d504f11234578f0",
        "secondaryDescriptor": "",
        "billing": "t1_bil_67d9c8a7df33cf77a3e5e0z",
        "start": 20160120,
        "currency": "USD",
        "sameDay": 0
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

