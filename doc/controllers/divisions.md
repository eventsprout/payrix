# Divisions

Divisions contains a list of user divisions associated with an account. It allows for an additional and optional layer of separation within a partition.

```php
$divisionsController = $client->getDivisionsController();
```

## Class Name

`DivisionsController`

## Methods

* [Get Divisions Id](../../doc/controllers/divisions.md#get-divisions-id)
* [Put Divisions Id](../../doc/controllers/divisions.md#put-divisions-id)
* [Get Divisions](../../doc/controllers/divisions.md#get-divisions)
* [Post Divisions](../../doc/controllers/divisions.md#post-divisions)


# Get Divisions Id

Query a Division.

```php
function getDivisionsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): DivisionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource, The Division ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`DivisionsResponseResult`](../../doc/models/divisions-response-result.md)

## Example Usage

```php
$id = 't1_div_67e151c6b0210514824000a';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $divisionsController->getDivisionsId(
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
        "id": "t1_div_67e151c6b0210514824000a",
        "created": "2025-03-24 08:36:22.7392",
        "modified": "2025-03-24 08:36:22.7392",
        "creator": "t1_log_663ce214b2f25f2325a9935",
        "modifier": "t1_log_663ce214b2f25f2325a9935",
        "login": "t1_log_67e150467ee225924163f18",
        "name": "sampleDivision",
        "email": "testuse1@example.com",
        "minPasswordLength": 9,
        "minPasswordComplexity": 1,
        "changeManagementEnabled": 0,
        "saferPaymentNonComplianceFeeManaged": 0,
        "canUsePlaidWrapperMicroservice": 0,
        "simplifiedDepositEnabled": 1
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


# Put Divisions Id

Update a Division.

```php
function putDivisionsId(
    string $id,
    DivisionsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): DivisionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource, The Division ID. |
| `body` | [`DivisionsPutRequest`](../../doc/models/divisions-put-request.md) | Body, Required | Update Division Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`DivisionsResponseResult`](../../doc/models/divisions-response-result.md)

## Example Usage

```php
$id = 't1_div_67e151c6b0210514824000a';

$body = DivisionsPutRequestBuilder::init()
    ->login('t1_log_67e150467ee225924163f18')
    ->name('sampleDivision')
    ->email('testuse1@example.com')
    ->changeManagementEnabled(ChangeManagementEnabledEnum::DISABLED)
    ->minPasswordLength(9)
    ->minPasswordComplexity(MinPasswordComplexityEnum::ONE)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $divisionsController->putDivisionsId(
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
        "id": "t1_div_67e151c6b0210514824000a",
        "created": "2025-03-24 08:36:22.7392",
        "modified": "2025-03-24 08:36:22.7392",
        "creator": "t1_log_663ce214b2f25f2325a9935",
        "modifier": "t1_log_663ce214b2f25f2325a9935",
        "login": "t1_log_67e150467ee225924163f18",
        "name": "sampleDivision",
        "email": "testuse1@example.com",
        "minPasswordLength": 9,
        "minPasswordComplexity": 1,
        "changeManagementEnabled": 0,
        "saferPaymentNonComplianceFeeManaged": 0,
        "canUsePlaidWrapperMicroservice": 0,
        "simplifiedDepositEnabled": 1
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


# Get Divisions

Query Division.

```php
function getDivisions(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): DivisionsResponseResult
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

[`DivisionsResponseResult`](../../doc/models/divisions-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $divisionsController->getDivisions(
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
        "id": "t1_div_67e151c6b0210514824000a",
        "created": "2025-03-24 08:36:22.7392",
        "modified": "2025-03-24 08:36:22.7392",
        "creator": "t1_log_663ce214b2f25f2325a9935",
        "modifier": "t1_log_663ce214b2f25f2325a9935",
        "login": "t1_log_67e150467ee225924163f18",
        "name": "sampleDivision",
        "email": "testuse1@example.com",
        "minPasswordLength": 9,
        "minPasswordComplexity": 1,
        "changeManagementEnabled": 0,
        "saferPaymentNonComplianceFeeManaged": 0,
        "canUsePlaidWrapperMicroservice": 0,
        "simplifiedDepositEnabled": 1
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


# Post Divisions

Create a Division.

```php
function postDivisions(
    DivisionsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): DivisionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`DivisionsPostRequest`](../../doc/models/divisions-post-request.md) | Body, Required | Create Division Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`DivisionsResponseResult`](../../doc/models/divisions-response-result.md)

## Example Usage

```php
$body = DivisionsPostRequestBuilder::init(
    't1_log_67e150467ee225924163f18',
    'sampleDivision'
)
    ->email('testuse1@example.com')
    ->changeManagementEnabled(ChangeManagementEnabledEnum::DISABLED)
    ->minPasswordLength(9)
    ->minPasswordComplexity(MinPasswordComplexityEnum::ONE)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $divisionsController->postDivisions(
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
        "id": "t1_div_67e151c6b0210514824000a",
        "created": "2025-03-24 08:36:22.7392",
        "modified": "2025-03-24 08:36:22.7392",
        "creator": "t1_log_663ce214b2f25f2325a9935",
        "modifier": "t1_log_663ce214b2f25f2325a9935",
        "login": "t1_log_67e150467ee225924163f18",
        "name": "sampleDivision",
        "email": "testuse1@example.com",
        "minPasswordLength": 9,
        "minPasswordComplexity": 1,
        "changeManagementEnabled": 0,
        "saferPaymentNonComplianceFeeManaged": 0,
        "canUsePlaidWrapperMicroservice": 0,
        "simplifiedDepositEnabled": 1
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

