# Orgs VAS Pinless Debit Conversions

```php
$orgsVASPinlessDebitConversionsController = $client->getOrgsVASPinlessDebitConversionsController();
```

## Class Name

`OrgsVASPinlessDebitConversionsController`

## Methods

* [Get Orgs VAS Pinless Debit Conversions Id](../../doc/controllers/orgs-vas-pinless-debit-conversions.md#get-orgs-vas-pinless-debit-conversions-id)
* [Put Orgs VAS Pinless Debit Conversions Id](../../doc/controllers/orgs-vas-pinless-debit-conversions.md#put-orgs-vas-pinless-debit-conversions-id)
* [Get Orgs VAS Pinless Debit Conversions](../../doc/controllers/orgs-vas-pinless-debit-conversions.md#get-orgs-vas-pinless-debit-conversions)
* [Post Orgs VAS Pinless Debit Conversions](../../doc/controllers/orgs-vas-pinless-debit-conversions.md#post-orgs-vas-pinless-debit-conversions)


# Get Orgs VAS Pinless Debit Conversions Id

Query orgsVASPinlessDebitConversions.

```php
function getOrgsVASPinlessDebitConversionsId(
    string $id,
    ?string $token = null,
    ?string $embed = null
): OrgsVASPinlessDebitConversionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource, or the (unknown) ID associated with the Orgs VAS Pinless Debit Conversions. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`OrgsVASPinlessDebitConversionsResponseResult`](../../doc/models/orgs-vas-pinless-debit-conversions-response-result.md)

## Example Usage

```php
$id = 't1_ovp_680bfd41d139cba791290z0';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$result = $orgsVASPinlessDebitConversionsController->getOrgsVASPinlessDebitConversionsId(
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
        "id": "t1_ovp_680bfd41d139cba791290z0",
        "created": "2025-04-25 17:23:13.8787",
        "modified": "2025-04-25 17:23:13.8787",
        "creator": "t1_log_66db672e98bceb86ecbb000",
        "modifier": "t1_log_66db672e98bceb86ecbb000",
        "org": "t1_org_680bfd2cea2729081810000",
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


# Put Orgs VAS Pinless Debit Conversions Id

Update orgsVASPinlessDebitConversions.

```php
function putOrgsVASPinlessDebitConversionsId(
    string $id,
    OrgsVASPinlessDebitConversionsPutRequest $body,
    ?string $token = null
): OrgsVASPinlessDebitConversionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this Orgs VAS Pinless Debit Conversions. |
| `body` | [`OrgsVASPinlessDebitConversionsPutRequest`](../../doc/models/orgs-vas-pinless-debit-conversions-put-request.md) | Body, Required | Update Orgs VAS Pinless Debit Conversions |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |

## Response Type

[`OrgsVASPinlessDebitConversionsResponseResult`](../../doc/models/orgs-vas-pinless-debit-conversions-response-result.md)

## Example Usage

```php
$id = 't1_ovp_680bfd41d139cba791290z0';

$body = OrgsVASPinlessDebitConversionsPutRequestBuilder::init()
    ->org('t1_org_680bfd2cea2729081810000')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$result = $orgsVASPinlessDebitConversionsController->putOrgsVASPinlessDebitConversionsId(
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
        "id": "t1_ovp_680bfd41d139cba791290z0",
        "created": "2025-04-25 17:23:13.8787",
        "modified": "2025-04-25 17:23:13.8787",
        "creator": "t1_log_66db672e98bceb86ecbb000",
        "modifier": "t1_log_66db672e98bceb86ecbb000",
        "org": "t1_org_680bfd2cea2729081810000",
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


# Get Orgs VAS Pinless Debit Conversions

Query a orgsVASPinlessDebitConversions.

```php
function getOrgsVASPinlessDebitConversions(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): OrgsVASPinlessDebitConversionsResponseResult
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

[`OrgsVASPinlessDebitConversionsResponseResult`](../../doc/models/orgs-vas-pinless-debit-conversions-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $orgsVASPinlessDebitConversionsController->getOrgsVASPinlessDebitConversions(
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
        "id": "t1_ovp_680bfd41d139cba791290z0",
        "created": "2025-04-25 17:23:13.8787",
        "modified": "2025-04-25 17:23:13.8787",
        "creator": "t1_log_66db672e98bceb86ecbb000",
        "modifier": "t1_log_66db672e98bceb86ecbb000",
        "org": "t1_org_680bfd2cea2729081810000",
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


# Post Orgs VAS Pinless Debit Conversions

Create a orgsVASPinlessDebitConversions.

```php
function postOrgsVASPinlessDebitConversions(
    OrgsVASPinlessDebitConversionsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): OrgsVASPinlessDebitConversionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`OrgsVASPinlessDebitConversionsPostRequest`](../../doc/models/orgs-vas-pinless-debit-conversions-post-request.md) | Body, Required | - |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`OrgsVASPinlessDebitConversionsResponseResult`](../../doc/models/orgs-vas-pinless-debit-conversions-response-result.md)

## Example Usage

```php
$body = OrgsVASPinlessDebitConversionsPostRequestBuilder::init(
    't1_org_680bfd2cea2729081815573'
)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgsVASPinlessDebitConversionsController->postOrgsVASPinlessDebitConversions(
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
        "id": "t1_ovp_680bfd41d139cba791290z0",
        "created": "2025-04-25 17:23:13.8787",
        "modified": "2025-04-25 17:23:13.8787",
        "creator": "t1_log_66db672e98bceb86ecbb000",
        "modifier": "t1_log_66db672e98bceb86ecbb000",
        "org": "t1_org_680bfd2cea2729081810000",
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

