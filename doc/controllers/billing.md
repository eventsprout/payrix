# Billing

The billing deals with billing configuration for an entity, org, division or partition. A billing configuration determines how an entity is billed for their payables within Payrix Pro.

```php
$billingController = $client->getBillingController();
```

## Class Name

`BillingController`

## Methods

* [Get Billings Id](../../doc/controllers/billing.md#get-billings-id)
* [Put Billings Id](../../doc/controllers/billing.md#put-billings-id)
* [Delete Billings Id](../../doc/controllers/billing.md#delete-billings-id)
* [Get Billings](../../doc/controllers/billing.md#get-billings)
* [Post Billings](../../doc/controllers/billing.md#post-billings)


# Get Billings Id

Query a Billing that is a means to collect and invoice for any funds owed for a particular period of time, such as setting up a billing to collect fees and create a statement on a monthly basis.

```php
function getBillingsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): BillingsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Billing ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`BillingsResponseResult`](../../doc/models/billings-response-result.md)

## Example Usage

```php
$id = 't1_bil_67dbdc94ee1b1a43e6ab400';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $billingController->getBillingsId(
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
        "id": "t1_bil_67dbdc94ee1b1a43e6ab400",
        "created": "2025-03-20 05:15:00.9831",
        "modified": "2025-03-20 05:15:00.9831",
        "creator": "t1_log_5cd987a73478a6179b95008",
        "modifier": "t1_log_5cd987a73478a6179b95008",
        "login": "t1_log_5cd987a73478a6179b95008",
        "entity": "t1_ent_5cd987a735c33bab09e7570",
        "org": "t1_org_5b0e08025ec790d3f9b8c00",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414970z0",
        "description": "Monthly Billing",
        "schedule": "months",
        "scheduleFactor": 1,
        "start": 20250401,
        "finish": 20250401,
        "collection": "entity",
        "collectionFactor": "months",
        "collectionOffset": 1,
        "collectionIncludeCurrent": 0,
        "currency": "USD",
        "inactive": 0,
        "frozen": 0,
        "forentity": "t1_ent_67dbdc7bb6b1dd5dbf396e0"
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


# Put Billings Id

Update a Billing, which is a means to collect and invoice for any funds owed for a particular period of time, such as setting up a billing to collect fees and create a statement on a monthly basis.

```php
function putBillingsId(
    string $id,
    BillingsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): BillingsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Billing ID. |
| `body` | [`BillingsPutRequest`](../../doc/models/billings-put-request.md) | Body, Required | Update Billing Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`BillingsResponseResult`](../../doc/models/billings-response-result.md)

## Example Usage

```php
$id = 't1_bil_67dbdc94ee1b1a43e6ab400';

$body = BillingsPutRequestBuilder::init()
    ->login('t1_log_5cd987a73478a6179b95008')
    ->entity('identifier')
    ->forentity('t1_ent_67dbdc7bb6b1dd5dbf396e0')
    ->org('t1_org_5b0e08025ec790d3f9b8c00')
    ->division('t1_div_67c56806728fbbf0bae0b00')
    ->partition('t1_ptn_666834d4d504f21414970z0')
    ->description('Monthly Billing')
    ->schedule(BillingScheduleEnum::MONTHS)
    ->scheduleFactor(1)
    ->start(20250401)
    ->finish(20250401)
    ->collection(BillingCollectionEnum::ENTITY)
    ->collectionFactor(BillingsCollectionFactorEnum::MONTHS)
    ->collectionOffset(1)
    ->collectionIncludeCurrent(BillingsCollectionIncludeCurrentEnum::EXCLUDECURRENTPERIOD)
    ->currency(CurrencyEnum::USD)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $billingController->putBillingsId(
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
        "id": "t1_bil_67dbdc94ee1b1a43e6ab400",
        "created": "2025-03-20 05:15:00.9831",
        "modified": "2025-03-20 05:15:00.9831",
        "creator": "t1_log_5cd987a73478a6179b95008",
        "modifier": "t1_log_5cd987a73478a6179b95008",
        "login": "t1_log_5cd987a73478a6179b95008",
        "entity": "t1_ent_5cd987a735c33bab09e7570",
        "org": "t1_org_5b0e08025ec790d3f9b8c00",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414970z0",
        "description": "Monthly Billing",
        "schedule": "months",
        "scheduleFactor": 1,
        "start": 20250401,
        "finish": 20250401,
        "collection": "entity",
        "collectionFactor": "months",
        "collectionOffset": 1,
        "collectionIncludeCurrent": 0,
        "currency": "USD",
        "inactive": 0,
        "frozen": 0,
        "forentity": "t1_ent_67dbdc7bb6b1dd5dbf396e0"
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


# Delete Billings Id

Delete a Billing that is a means to collect and invoice for any funds owed for a particular period of time, such as setting up a billing to collect fees and create a statement on a monthly basis.

```php
function deleteBillingsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): BillingsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Billing ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`BillingsResponseResult`](../../doc/models/billings-response-result.md)

## Example Usage

```php
$id = 't1_bil_67dbdc94ee1b1a43e6ab400';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $billingController->deleteBillingsId(
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
        "id": "t1_bil_67dbdc94ee1b1a43e6ab400",
        "created": "2025-03-20 05:15:00.9831",
        "modified": "2025-03-20 05:15:00.9831",
        "creator": "t1_log_5cd987a73478a6179b95008",
        "modifier": "t1_log_5cd987a73478a6179b95008",
        "login": "t1_log_5cd987a73478a6179b95008",
        "entity": "t1_ent_5cd987a735c33bab09e7570",
        "org": "t1_org_5b0e08025ec790d3f9b8c00",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414970z0",
        "description": "Monthly Billing",
        "schedule": "months",
        "scheduleFactor": 1,
        "start": 20250401,
        "finish": 20250401,
        "collection": "entity",
        "collectionFactor": "months",
        "collectionOffset": 1,
        "collectionIncludeCurrent": 0,
        "currency": "USD",
        "inactive": 0,
        "frozen": 0,
        "forentity": "t1_ent_67dbdc7bb6b1dd5dbf396e0"
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


# Get Billings

Query a Billing is a means to collect and invoice for any funds owed for a particular period of time, such as setting up a billing to collect fees and create a statement on a monthly basis.

```php
function getBillings(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): BillingsResponseResult
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

[`BillingsResponseResult`](../../doc/models/billings-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $billingController->getBillings(
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
        "id": "t1_bil_67dbdc94ee1b1a43e6ab400",
        "created": "2025-03-20 05:15:00.9831",
        "modified": "2025-03-20 05:15:00.9831",
        "creator": "t1_log_5cd987a73478a6179b95008",
        "modifier": "t1_log_5cd987a73478a6179b95008",
        "login": "t1_log_5cd987a73478a6179b95008",
        "entity": "t1_ent_5cd987a735c33bab09e7570",
        "org": "t1_org_5b0e08025ec790d3f9b8c00",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414970z0",
        "description": "Monthly Billing",
        "schedule": "months",
        "scheduleFactor": 1,
        "start": 20250401,
        "finish": 20250401,
        "collection": "entity",
        "collectionFactor": "months",
        "collectionOffset": 1,
        "collectionIncludeCurrent": 0,
        "currency": "USD",
        "inactive": 0,
        "frozen": 0,
        "forentity": "t1_ent_67dbdc7bb6b1dd5dbf396e0"
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


# Post Billings

Create a Billing that is a means to collect and invoice for any funds owed for a particular period of time, such as statement of fees collected on a monthly basis.

```php
function postBillings(
    BillingsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): BillingsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`BillingsPostRequest`](../../doc/models/billings-post-request.md) | Body, Required | Create Billing Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`BillingsResponseResult`](../../doc/models/billings-response-result.md)

## Example Usage

```php
$body = BillingsPostRequestBuilder::init(
    't1_log_5cd987a73478a6179b95008',
    'identifier',
    BillingScheduleEnum::MONTHS,
    20250401,
    BillingsCollectionFactorEnum::MONTHS
)
    ->forentity('t1_ent_67dbdc7bb6b1dd5dbf396e0')
    ->org('t1_org_5b0e08025ec790d3f9b8c00')
    ->division('t1_div_67c56806728fbbf0bae0b00')
    ->partition('t1_ptn_666834d4d504f21414970z0')
    ->description('Monthly Billing')
    ->scheduleFactor(1)
    ->finish(20250401)
    ->collection(BillingCollectionEnum::ENTITY)
    ->collectionOffset(1)
    ->collectionIncludeCurrent(BillingsCollectionIncludeCurrentEnum::EXCLUDECURRENTPERIOD)
    ->currency(CurrencyEnum::USD)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $billingController->postBillings(
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
        "id": "t1_bil_67dbdc94ee1b1a43e6ab400",
        "created": "2025-03-20 05:15:00.9831",
        "modified": "2025-03-20 05:15:00.9831",
        "creator": "t1_log_5cd987a73478a6179b95008",
        "modifier": "t1_log_5cd987a73478a6179b95008",
        "login": "t1_log_5cd987a73478a6179b95008",
        "entity": "t1_ent_5cd987a735c33bab09e7570",
        "org": "t1_org_5b0e08025ec790d3f9b8c00",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414970z0",
        "description": "Monthly Billing",
        "schedule": "months",
        "scheduleFactor": 1,
        "start": 20250401,
        "finish": 20250401,
        "collection": "entity",
        "collectionFactor": "months",
        "collectionOffset": 1,
        "collectionIncludeCurrent": 0,
        "currency": "USD",
        "inactive": 0,
        "frozen": 0,
        "forentity": "t1_ent_67dbdc7bb6b1dd5dbf396e0"
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

