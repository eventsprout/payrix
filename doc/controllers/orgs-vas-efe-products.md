# Orgs VAS Efe Products

```php
$orgsVASEfeProductsController = $client->getOrgsVASEfeProductsController();
```

## Class Name

`OrgsVASEfeProductsController`

## Methods

* [Get Orgs VAS Efe Products Id](../../doc/controllers/orgs-vas-efe-products.md#get-orgs-vas-efe-products-id)
* [Put Orgs VAS Efe Products Id](../../doc/controllers/orgs-vas-efe-products.md#put-orgs-vas-efe-products-id)
* [Delete Orgs VAS Efe Products Id](../../doc/controllers/orgs-vas-efe-products.md#delete-orgs-vas-efe-products-id)
* [Get Orgs VAS Efe Products](../../doc/controllers/orgs-vas-efe-products.md#get-orgs-vas-efe-products)
* [Post Orgs VAS Efe Products](../../doc/controllers/orgs-vas-efe-products.md#post-orgs-vas-efe-products)


# Get Orgs VAS Efe Products Id

Query orgsVASEfeProducts.

```php
function getOrgsVASEfeProductsId(
    string $id,
    ?string $token = null,
    ?string $embed = null
): OrgsVASEfeProductsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource, or the (unknown) ID associated with the Orgs VAS EfeProducts. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`OrgsVASEfeProductsResponseResult`](../../doc/models/orgs-vas-efe-products-response-result.md)

## Example Usage

```php
$id = 't1_ove_6862c122527a9042ec000c0';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$result = $orgsVASEfeProductsController->getOrgsVASEfeProductsId(
    $id,
    $token
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_ove_6862c122527a9042ec000c0",
        "created": "2025-06-30 12:53:54.3584",
        "modified": "2025-06-30 12:53:54.3584",
        "creator": "t1_log_65c6415ad9791e3796f000c",
        "modifier": "t1_log_65c6415ad9791e3796f000c",
        "org": "t1_org_6862c1211b366bbfe87657c",
        "product": "merchantWorkingCapital",
        "contractType": "{\"residualFeeType\": \"rev_share\"}",
        "platform": "PARAFIN",
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


# Put Orgs VAS Efe Products Id

Update orgsVASEfeProducts.

```php
function putOrgsVASEfeProductsId(
    string $id,
    OrgsVASEfeProductsPutRequest $body,
    ?string $token = null
): OrgsVASEfeProductsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this Orgs VAS EfeProducts. |
| `body` | [`OrgsVASEfeProductsPutRequest`](../../doc/models/orgs-vas-efe-products-put-request.md) | Body, Required | Update Orgs VAS EfeProducts |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |

## Response Type

[`OrgsVASEfeProductsResponseResult`](../../doc/models/orgs-vas-efe-products-response-result.md)

## Example Usage

```php
$id = 't1_ove_6862c122527a9042ec000c0';

$body = OrgsVASEfeProductsPutRequestBuilder::init()
    ->org('t1_org_6862c1211b366bbfe87657c')
    ->product(OrgsVASEfeProductsProductEnum::MERCHANTWORKINGCAPITAL)
    ->contractType('{"residualFeeType": "rev_share"}')
    ->platform(OrgsVASEfeProductsPlatformEnum::PARAFIN)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$result = $orgsVASEfeProductsController->putOrgsVASEfeProductsId(
    $id,
    $body,
    $token
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_ove_6862c122527a9042ec000c0",
        "created": "2025-06-30 12:53:54.3584",
        "modified": "2025-06-30 12:53:54.3584",
        "creator": "t1_log_65c6415ad9791e3796f000c",
        "modifier": "t1_log_65c6415ad9791e3796f000c",
        "org": "t1_org_6862c1211b366bbfe87657c",
        "product": "merchantWorkingCapital",
        "contractType": "{\"residualFeeType\": \"rev_share\"}",
        "platform": "PARAFIN",
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


# Delete Orgs VAS Efe Products Id

Delete orgsVASEfeProducts.

```php
function deleteOrgsVASEfeProductsId(string $id, ?string $token = null): OrgsVASEfeProductsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this Orgs VAS EfeProducts. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |

## Response Type

[`OrgsVASEfeProductsResponseResult`](../../doc/models/orgs-vas-efe-products-response-result.md)

## Example Usage

```php
$id = 't1_ove_6862c122527a9042ec000c0';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$result = $orgsVASEfeProductsController->deleteOrgsVASEfeProductsId(
    $id,
    $token
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_ove_6862c122527a9042ec000c0",
        "created": "2025-06-30 12:53:54.3584",
        "modified": "2025-06-30 12:53:54.3584",
        "creator": "t1_log_65c6415ad9791e3796f000c",
        "modifier": "t1_log_65c6415ad9791e3796f000c",
        "org": "t1_org_6862c1211b366bbfe87657c",
        "product": "merchantWorkingCapital",
        "contractType": "{\"residualFeeType\": \"rev_share\"}",
        "platform": "PARAFIN",
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


# Get Orgs VAS Efe Products

Query a orgsVASEfeProducts.

```php
function getOrgsVASEfeProducts(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): OrgsVASEfeProductsResponseResult
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

[`OrgsVASEfeProductsResponseResult`](../../doc/models/orgs-vas-efe-products-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $orgsVASEfeProductsController->getOrgsVASEfeProducts(
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
        "id": "t1_ove_6862c122527a9042ec000c0",
        "created": "2025-06-30 12:53:54.3584",
        "modified": "2025-06-30 12:53:54.3584",
        "creator": "t1_log_65c6415ad9791e3796f000c",
        "modifier": "t1_log_65c6415ad9791e3796f000c",
        "org": "t1_org_6862c1211b366bbfe87657c",
        "product": "merchantWorkingCapital",
        "contractType": "{\"residualFeeType\": \"rev_share\"}",
        "platform": "PARAFIN",
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


# Post Orgs VAS Efe Products

Create a orgsVASEfeProducts.

```php
function postOrgsVASEfeProducts(
    OrgsVASEfeProductsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): OrgsVASEfeProductsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`OrgsVASEfeProductsPostRequest`](../../doc/models/orgs-vas-efe-products-post-request.md) | Body, Required | - |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`OrgsVASEfeProductsResponseResult`](../../doc/models/orgs-vas-efe-products-response-result.md)

## Example Usage

```php
$body = OrgsVASEfeProductsPostRequestBuilder::init()
    ->org('t1_org_6862c1211b366bbfe87657c')
    ->product(OrgsVASEfeProductsProductEnum::MERCHANTWORKINGCAPITAL)
    ->contractType('{"residualFeeType": "rev_share"}')
    ->platform(OrgsVASEfeProductsPlatformEnum::PARAFIN)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgsVASEfeProductsController->postOrgsVASEfeProducts(
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
        "id": "t1_ove_6862c122527a9042ec000c0",
        "created": "2025-06-30 12:53:54.3584",
        "modified": "2025-06-30 12:53:54.3584",
        "creator": "t1_log_65c6415ad9791e3796f000c",
        "modifier": "t1_log_65c6415ad9791e3796f000c",
        "org": "t1_org_6862c1211b366bbfe87657c",
        "product": "merchantWorkingCapital",
        "contractType": "{\"residualFeeType\": \"rev_share\"}",
        "platform": "PARAFIN",
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

