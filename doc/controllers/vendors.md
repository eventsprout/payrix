# Vendors

Resources that deal with third-party entities (non-facilitators and non-merchants) that are involved with the merchant processing and provide a service (or set of services) to the merchant, for which they usually take a fee.

```php
$vendorsController = $client->getVendorsController();
```

## Class Name

`VendorsController`

## Methods

* [Get Vendors Id](../../doc/controllers/vendors.md#get-vendors-id)
* [Put Vendors Id](../../doc/controllers/vendors.md#put-vendors-id)
* [Delete Vendors Id](../../doc/controllers/vendors.md#delete-vendors-id)
* [Get Vendors](../../doc/controllers/vendors.md#get-vendors)


# Get Vendors Id

Querying a Vendor resource represents a third-party vendor who interacts with the API, for example, a referral platform.

```php
function getVendorsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): VendorsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource, The Vendor ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`VendorsResponseResult`](../../doc/models/vendors-response-result.md)

## Example Usage

```php
$id = 'p1_ven_00be57c6efdce043adae8a1';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $vendorsController->getVendorsId(
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
        "id": "p1_ven_00be57c6efdce043adae8a1",
        "created": "2025-02-25 18:52:38.9990",
        "modified": "2025-02-25 18:52:43.4509",
        "creator": "g1577d7719644a9",
        "modifier": "g1577d7719644a9",
        "entity": "p1_ent_67be57c6a1d97f564021b6b",
        "division": "p1_div_67be57c6d34928c1ee16155",
        "inactive": 0,
        "frozen": 0,
        "dealId": "",
        "onboardingContactEmails": "",
        "riskContactEmails": ""
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


# Put Vendors Id

Manage a Vendor resource.

Details:
Update a Vendor resource. A Vendor resource represents a third-party vendor who interacts with the API, for example, a referral platform.
Query a Vendor resource.

```php
function putVendorsId(
    string $id,
    VendorsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): VendorsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Vendor ID. |
| `body` | [`VendorsPutRequest`](../../doc/models/vendors-put-request.md) | Body, Required | Update Vendor Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`VendorsResponseResult`](../../doc/models/vendors-response-result.md)

## Example Usage

```php
$id = 'p1_ven_00be57c6efdce043adae8a1';

$body = VendorsPutRequestBuilder::init()
    ->entity('p1_ent_67be57c6a1d97f564021b6b')
    ->division('p1_div_67be57c6d34928c1ee16155')
    ->onboardingContactEmails('robert@example.com')
    ->riskContactEmails('robert.j@example.com')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $vendorsController->putVendorsId(
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
        "id": "p1_ven_00be57c6efdce043adae8a1",
        "created": "2025-02-25 18:52:38.9990",
        "modified": "2025-02-25 18:52:43.4509",
        "creator": "g1577d7719644a9",
        "modifier": "g1577d7719644a9",
        "entity": "p1_ent_67be57c6a1d97f564021b6b",
        "division": "p1_div_67be57c6d34928c1ee16155",
        "inactive": 0,
        "frozen": 0,
        "dealId": "",
        "onboardingContactEmails": "",
        "riskContactEmails": ""
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


# Delete Vendors Id

Delete a Vendor or Vendors resource that represents a third-party vendor who interacts with the API, for example, a referral platform.

```php
function deleteVendorsId(string $id, ?string $token = null, ?string $requestToken = null): VendorsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource, The Vendor ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`VendorsResponseResult`](../../doc/models/vendors-response-result.md)

## Example Usage

```php
$id = 'p1_ven_00be57c6efdce043adae8a1';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $vendorsController->deleteVendorsId(
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
        "id": "p1_ven_00be57c6efdce043adae8a1",
        "created": "2025-02-25 18:52:38.9990",
        "modified": "2025-02-25 18:52:43.4509",
        "creator": "g1577d7719644a9",
        "modifier": "g1577d7719644a9",
        "entity": "p1_ent_67be57c6a1d97f564021b6b",
        "division": "p1_div_67be57c6d34928c1ee16155",
        "inactive": 0,
        "frozen": 0,
        "dealId": "",
        "onboardingContactEmails": "",
        "riskContactEmails": ""
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


# Get Vendors

Query a Vendor resource. A Vendor resource represents a third-party vendor who interacts with the API, for example, a referral platform.

```php
function getVendors(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): VendorsResponseResult
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

[`VendorsResponseResult`](../../doc/models/vendors-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $vendorsController->getVendors(
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
        "id": "p1_ven_00be57c6efdce043adae8a1",
        "created": "2025-02-25 18:52:38.9990",
        "modified": "2025-02-25 18:52:43.4509",
        "creator": "g1577d7719644a9",
        "modifier": "g1577d7719644a9",
        "entity": "p1_ent_67be57c6a1d97f564021b6b",
        "division": "p1_div_67be57c6d34928c1ee16155",
        "inactive": 0,
        "frozen": 0,
        "dealId": "",
        "onboardingContactEmails": "",
        "riskContactEmails": ""
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

