# Plans

Resource that represents a recurring type of payment that charges a certain amount on a weekly, monthly, quarterly, or annual basis.

```php
$plansController = $client->getPlansController();
```

## Class Name

`PlansController`

## Methods

* [Get Plans Id](../../doc/controllers/plans.md#get-plans-id)
* [Put Plans Id](../../doc/controllers/plans.md#put-plans-id)
* [Delete Plans Id](../../doc/controllers/plans.md#delete-plans-id)
* [Get Plans](../../doc/controllers/plans.md#get-plans)
* [Post Plans](../../doc/controllers/plans.md#post-plans)


# Get Plans Id

Query a Plan that represents a recurring type of payment that charges a certain amount on a weekly, monthly, quarterly, or annual basis, once created, allowing association with a Subscription and user.

```php
function getPlansId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): PlansResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this plan. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`PlansResponseResult`](../../doc/models/plans-response-result.md)

## Example Usage

```php
$id = 'p1_pln_00bdbe193c3abe3b2243695';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $plansController->getPlansId(
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
        "id": "p1_pln_00cb491aa15f9b515c3b59b",
        "created": "2025-03-07 14:29:30.6772",
        "modified": "2025-03-07 14:29:30.6772",
        "creator": "p1_log_000444ad99da5eb18e00207",
        "modifier": "p1_log_000444ad99da5eb18e00207",
        "merchant": "p1_mer_000444add0403c3553f4d20",
        "name": "Lind - Wyman Subscription Plan weekly",
        "description": "regular plan",
        "schedule": 3,
        "scheduleFactor": 1,
        "amount": 9211,
        "inactive": 0,
        "frozen": 0,
        "maxFailures": 2,
        "type": "recurring",
        "txnDescription": "plan txn description",
        "order": "S1 - 1000 - LAST",
        "billing": "p1_bil_00cee36329ead6ae6d31e43",
        "um": "actual"
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


# Put Plans Id

Update a Plan that represents a recurring type of payment that charges a certain amount on a weekly, monthly, quarterly, or annual basis, once created, allowing association with a Subscription and user.

```php
function putPlansId(
    string $id,
    PlansPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): PlansResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this plan. |
| `body` | [`PlansPutRequest`](../../doc/models/plans-put-request.md) | Body, Required | Update plan Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`PlansResponseResult`](../../doc/models/plans-response-result.md)

## Example Usage

```php
$id = 'p1_pln_00bdbe193c3abe3b2243695';

$body = PlansPutRequestBuilder::init()
    ->amount(50000)
    ->billing('p1_bil_00cee36329ead6ae6d31e43')
    ->order('S1 - 1000 - LAST')
    ->txnDescription('Payment Plan')
    ->description('Payment')
    ->maxFailures(2)
    ->name('Lind - Wyman Subscription Plan weekly')
    ->schedule(PlanScheduleEnum::DAILY)
    ->scheduleFactor(1)
    ->um(PlanUmEnum::ACTUAL)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $plansController->putPlansId(
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
        "id": "p1_pln_00cb491aa15f9b515c3b59b",
        "created": "2025-03-07 14:29:30.6772",
        "modified": "2025-03-07 14:29:30.6772",
        "creator": "p1_log_000444ad99da5eb18e00207",
        "modifier": "p1_log_000444ad99da5eb18e00207",
        "merchant": "p1_mer_000444add0403c3553f4d20",
        "name": "Lind - Wyman Subscription Plan weekly",
        "description": "regular plan",
        "schedule": 3,
        "scheduleFactor": 1,
        "amount": 9211,
        "inactive": 0,
        "frozen": 0,
        "maxFailures": 2,
        "type": "recurring",
        "txnDescription": "plan txn description",
        "order": "S1 - 1000 - LAST",
        "billing": "p1_bil_00cee36329ead6ae6d31e43",
        "um": "actual"
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


# Delete Plans Id

Delete a Plan that represents a recurring type of payment that charges a certain amount on a weekly, monthly, quarterly, or annual basis, once created, allowing association with a Subscription and user.

```php
function deletePlansId(string $id, ?string $token = null, ?string $requestToken = null): PlansResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this plan. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`PlansResponseResult`](../../doc/models/plans-response-result.md)

## Example Usage

```php
$id = 'p1_pln_00bdbe193c3abe3b2243695';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $plansController->deletePlansId(
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
        "id": "p1_pln_00cb491aa15f9b515c3b59b",
        "created": "2025-03-07 14:29:30.6772",
        "modified": "2025-03-07 14:29:30.6772",
        "creator": "p1_log_000444ad99da5eb18e00207",
        "modifier": "p1_log_000444ad99da5eb18e00207",
        "merchant": "p1_mer_000444add0403c3553f4d20",
        "name": "Lind - Wyman Subscription Plan weekly",
        "description": "regular plan",
        "schedule": 3,
        "scheduleFactor": 1,
        "amount": 9211,
        "inactive": 0,
        "frozen": 0,
        "maxFailures": 2,
        "type": "recurring",
        "txnDescription": "plan txn description",
        "order": "S1 - 1000 - LAST",
        "billing": "p1_bil_00cee36329ead6ae6d31e43",
        "um": "actual"
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


# Get Plans

Query a Plan.
A Plan represents a recurring type of payment that charges a certain amount on a weekly, monthly, quarterly, or annual basis.
Once you create a Plan, you can associate a Subscription and user with it.

```php
function getPlans(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): PlansResponseResult
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

[`PlansResponseResult`](../../doc/models/plans-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $plansController->getPlans(
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
        "id": "p1_pln_00cb491aa15f9b515c3b59b",
        "created": "2025-03-07 14:29:30.6772",
        "modified": "2025-03-07 14:29:30.6772",
        "creator": "p1_log_000444ad99da5eb18e00207",
        "modifier": "p1_log_000444ad99da5eb18e00207",
        "merchant": "p1_mer_000444add0403c3553f4d20",
        "name": "Lind - Wyman Subscription Plan weekly",
        "description": "regular plan",
        "schedule": 3,
        "scheduleFactor": 1,
        "amount": 9211,
        "inactive": 0,
        "frozen": 0,
        "maxFailures": 2,
        "type": "recurring",
        "txnDescription": "plan txn description",
        "order": "S1 - 1000 - LAST",
        "billing": "p1_bil_00cee36329ead6ae6d31e43",
        "um": "actual"
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


# Post Plans

Create a Plan that represents a recurring type of payment that charges a certain amount on a weekly, monthly, quarterly, or annual basis, which once created, allows you to associate a Subscription and user with it.

```php
function postPlans(
    PlansPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): PlansResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`PlansPostRequest`](../../doc/models/plans-post-request.md) | Body, Required | - |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`PlansResponseResult`](../../doc/models/plans-response-result.md)

## Example Usage

```php
$body = PlansPostRequestBuilder::init(
    50000,
    'p1_mer_000444add0403c3553f4d20',
    PlanScheduleEnum::DAILY
)
    ->billing('p1_bil_00cee36329ead6ae6d31e43')
    ->order('S1 - 1000 - LAST')
    ->txnDescription('Payment Plan')
    ->description('Payment')
    ->maxFailures(2)
    ->name('Lind - Wyman Subscription Plan weekly')
    ->scheduleFactor(1)
    ->um(PlanUmEnum::ACTUAL)
    ->type(PlanTypeEnum::RECURRING)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $plansController->postPlans(
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
        "id": "p1_pln_00cb491aa15f9b515c3b59b",
        "created": "2025-03-07 14:29:30.6772",
        "modified": "2025-03-07 14:29:30.6772",
        "creator": "p1_log_000444ad99da5eb18e00207",
        "modifier": "p1_log_000444ad99da5eb18e00207",
        "merchant": "p1_mer_000444add0403c3553f4d20",
        "name": "Lind - Wyman Subscription Plan weekly",
        "description": "regular plan",
        "schedule": 3,
        "scheduleFactor": 1,
        "amount": 9211,
        "inactive": 0,
        "frozen": 0,
        "maxFailures": 2,
        "type": "recurring",
        "txnDescription": "plan txn description",
        "order": "S1 - 1000 - LAST",
        "billing": "p1_bil_00cee36329ead6ae6d31e43",
        "um": "actual"
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

