# Billing Modifiers

```php
$billingModifiersController = $client->getBillingModifiersController();
```

## Class Name

`BillingModifiersController`

## Methods

* [Get Billing Modifiers Id](../../doc/controllers/billing-modifiers.md#get-billing-modifiers-id)
* [Put Billing Modifiers Id](../../doc/controllers/billing-modifiers.md#put-billing-modifiers-id)
* [Delete Billing Modifiers Id](../../doc/controllers/billing-modifiers.md#delete-billing-modifiers-id)
* [Get Billing Modifiers](../../doc/controllers/billing-modifiers.md#get-billing-modifiers)
* [Post Billing Modifiers](../../doc/controllers/billing-modifiers.md#post-billing-modifiers)


# Get Billing Modifiers Id

Query a Billing Modifier that can change the total amount of the billing or whoever will pay it, such as applying a 10% markup on the fee total for a specific org.

```php
function getBillingModifiersId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): BillingModifiersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this billing modifer. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`BillingModifiersResponseResult`](../../doc/models/billing-modifiers-response-result.md)

## Example Usage

```php
$id = 't1_blm_67d9c9f74881eb511220000';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $billingModifiersController->getBillingModifiersId(
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
        "id": "t1_blm_67d9c9f74881eb511220000",
        "created": "2025-03-18 15:31:03.3269",
        "modified": "2025-03-18 15:31:03.3269",
        "creator": "t1_log_605e14227eb0a0b1c1d2b12",
        "modifier": "t1_log_605e14227eb0a0b1c1d2b12",
        "billing": "t1_bil_67d9c8a7df33cf77a3e5e4a",
        "entity": "t1_ent_5cd987a735c33bab09e7570",
        "org": "t1_org_5b0e08025ec790d3f9b8c00",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414970z0",
        "fromentity": "t1_ent_67d851660b5836731a89ee3",
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


# Put Billing Modifiers Id

Update a Billing Modifier that can change the total amount of the billing or whoever will pay it, such as applying a 10% markup on the fee total for a specific org.

```php
function putBillingModifiersId(
    string $id,
    BillingModifiersPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): BillingModifiersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this billing modifer. |
| `body` | [`BillingModifiersPutRequest`](../../doc/models/billing-modifiers-put-request.md) | Body, Required | Update Billing Modifer Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`BillingModifiersResponseResult`](../../doc/models/billing-modifiers-response-result.md)

## Example Usage

```php
$id = 't1_blm_67d9c9f74881eb511220000';

$body = BillingModifiersPutRequestBuilder::init()
    ->billing('t1_bil_67d9c8a7df33cf77a3e5e4a')
    ->entity('t1_ent_5cd987a735c33bab09e7570')
    ->org('t1_org_67d9c6a866e5d47dca276c3')
    ->division('t1_div_67c56806728fbbf0bae0b00')
    ->partition('t1_ptn_666834d4d504f21414970z0')
    ->fromentity('t1_ent_67d851660b5836731a89ee3')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $billingModifiersController->putBillingModifiersId(
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
        "id": "t1_blm_67d9c9f74881eb511220000",
        "created": "2025-03-18 15:31:03.3269",
        "modified": "2025-03-18 15:31:03.3269",
        "creator": "t1_log_605e14227eb0a0b1c1d2b12",
        "modifier": "t1_log_605e14227eb0a0b1c1d2b12",
        "billing": "t1_bil_67d9c8a7df33cf77a3e5e4a",
        "entity": "t1_ent_5cd987a735c33bab09e7570",
        "org": "t1_org_5b0e08025ec790d3f9b8c00",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414970z0",
        "fromentity": "t1_ent_67d851660b5836731a89ee3",
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


# Delete Billing Modifiers Id

Delete a Billing Modifier that can change the total amount of the billing or whoever will pay it.

```php
function deleteBillingModifiersId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): BillingModifiersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this billing modifer. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`BillingModifiersResponseResult`](../../doc/models/billing-modifiers-response-result.md)

## Example Usage

```php
$id = 't1_blm_67d9c9f74881eb511220000';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $billingModifiersController->deleteBillingModifiersId(
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
        "id": "t1_blm_67d9c9f74881eb511220000",
        "created": "2025-03-18 15:31:03.3269",
        "modified": "2025-03-18 15:31:03.3269",
        "creator": "t1_log_605e14227eb0a0b1c1d2b12",
        "modifier": "t1_log_605e14227eb0a0b1c1d2b12",
        "billing": "t1_bil_67d9c8a7df33cf77a3e5e4a",
        "entity": "t1_ent_5cd987a735c33bab09e7570",
        "org": "t1_org_5b0e08025ec790d3f9b8c00",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414970z0",
        "fromentity": "t1_ent_67d851660b5836731a89ee3",
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


# Get Billing Modifiers

Query a Billing Modifier that can change the total amount of the billing or determine who will pay it. For example, a Billing Modifier may apply a 10% markup on the fee total for a specific organization.

```php
function getBillingModifiers(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): BillingModifiersResponseResult
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

[`BillingModifiersResponseResult`](../../doc/models/billing-modifiers-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $billingModifiersController->getBillingModifiers(
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
        "id": "t1_blm_67d9c9f74881eb511220000",
        "created": "2025-03-18 15:31:03.3269",
        "modified": "2025-03-18 15:31:03.3269",
        "creator": "t1_log_605e14227eb0a0b1c1d2b12",
        "modifier": "t1_log_605e14227eb0a0b1c1d2b12",
        "billing": "t1_bil_67d9c8a7df33cf77a3e5e4a",
        "entity": "t1_ent_5cd987a735c33bab09e7570",
        "org": "t1_org_5b0e08025ec790d3f9b8c00",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414970z0",
        "fromentity": "t1_ent_67d851660b5836731a89ee3",
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


# Post Billing Modifiers

Create a Billing Modifier that can change the total amount of the billing or adjust who will pay it, such as applying a 10% markup on the fee total for a specific organization.

```php
function postBillingModifiers(
    BillingModifiersPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): BillingModifiersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`BillingModifiersPostRequest`](../../doc/models/billing-modifiers-post-request.md) | Body, Required | Create Billing Modifier Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`BillingModifiersResponseResult`](../../doc/models/billing-modifiers-response-result.md)

## Example Usage

```php
$body = BillingModifiersPostRequestBuilder::init(
    't1_bil_67d9c8a7df33cf77a3e5e4a',
    't1_ent_67d851660b5836731a89ee3'
)
    ->entity('t1_ent_5cd987a735c33bab09e7570')
    ->org('t1_org_67d9c6a866e5d47dca276c3')
    ->division('t1_div_67c56806728fbbf0bae0b00')
    ->partition('t1_ptn_666834d4d504f21414970z0')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $billingModifiersController->postBillingModifiers(
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
        "id": "t1_blm_67d9c9f74881eb511220000",
        "created": "2025-03-18 15:31:03.3269",
        "modified": "2025-03-18 15:31:03.3269",
        "creator": "t1_log_605e14227eb0a0b1c1d2b12",
        "modifier": "t1_log_605e14227eb0a0b1c1d2b12",
        "billing": "t1_bil_67d9c8a7df33cf77a3e5e4a",
        "entity": "t1_ent_5cd987a735c33bab09e7570",
        "org": "t1_org_5b0e08025ec790d3f9b8c00",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414970z0",
        "fromentity": "t1_ent_67d851660b5836731a89ee3",
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

