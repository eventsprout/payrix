# Orgs VAS Safer Payments

```php
$orgsVASSaferPaymentsController = $client->getOrgsVASSaferPaymentsController();
```

## Class Name

`OrgsVASSaferPaymentsController`

## Methods

* [Get Orgs VAS Safer Payments Id](../../doc/controllers/orgs-vas-safer-payments.md#get-orgs-vas-safer-payments-id)
* [Put Orgs VAS Safer Payments Id](../../doc/controllers/orgs-vas-safer-payments.md#put-orgs-vas-safer-payments-id)
* [Delete Orgs VAS Safer Payments Id](../../doc/controllers/orgs-vas-safer-payments.md#delete-orgs-vas-safer-payments-id)
* [Get Orgs VAS Safer Payments](../../doc/controllers/orgs-vas-safer-payments.md#get-orgs-vas-safer-payments)
* [Post Orgs VAS Safer Payments](../../doc/controllers/orgs-vas-safer-payments.md#post-orgs-vas-safer-payments)


# Get Orgs VAS Safer Payments Id

Query Orgs VAS Safer Payments.

```php
function getOrgsVASSaferPaymentsId(
    string $id,
    ?string $token = null,
    ?string $embed = null
): OrgsVASSaferPaymentsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource, or the (unknown) ID associated with the Orgs VAS Safer Payments. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`OrgsVASSaferPaymentsResponseResult`](../../doc/models/orgs-vas-safer-payments-response-result.md)

## Example Usage

```php
$id = 't1_ovs_67ffd50aa5b2855bcd59e00';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$result = $orgsVASSaferPaymentsController->getOrgsVASSaferPaymentsId(
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
        "id": "t1_ovs_67ffd50aa5b2855bcd59e00",
        "created": "2025-04-16 12:04:26.6985",
        "modified": "2025-04-16 12:04:26.6985",
        "creator": "t1_log_65c6415ad9791e3796f739c",
        "modifier": "t1_log_65c6415ad9791e3796f739c",
        "org": "t1_org_67ffd5094c032a71089829d",
        "defaultProgram": "basic",
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


# Put Orgs VAS Safer Payments Id

Update Orgs VAS Safer Payments.

```php
function putOrgsVASSaferPaymentsId(
    string $id,
    OrgsVASSaferPaymentsPutRequest $body,
    ?string $token = null
): OrgsVASSaferPaymentsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this Orgs VAS Safer Payments. |
| `body` | [`OrgsVASSaferPaymentsPutRequest`](../../doc/models/orgs-vas-safer-payments-put-request.md) | Body, Required | Update Orgs VAS Safer Payments |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |

## Response Type

[`OrgsVASSaferPaymentsResponseResult`](../../doc/models/orgs-vas-safer-payments-response-result.md)

## Example Usage

```php
$id = 't1_ovs_67ffd50aa5b2855bcd59e00';

$body = OrgsVASSaferPaymentsPutRequestBuilder::init()
    ->org('t1_org_680bfd2cea2729081810000')
    ->defaultProgram(OrgsVASSaferPaymentsDefaultProgramEnum::BASIC)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$result = $orgsVASSaferPaymentsController->putOrgsVASSaferPaymentsId(
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
        "id": "t1_ovs_67ffd50aa5b2855bcd59e00",
        "created": "2025-04-16 12:04:26.6985",
        "modified": "2025-04-16 12:04:26.6985",
        "creator": "t1_log_65c6415ad9791e3796f739c",
        "modifier": "t1_log_65c6415ad9791e3796f739c",
        "org": "t1_org_67ffd5094c032a71089829d",
        "defaultProgram": "basic",
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


# Delete Orgs VAS Safer Payments Id

Delete Safer Payments.

```php
function deleteOrgsVASSaferPaymentsId(string $id, ?string $token = null): OrgsVASSaferPaymentsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this Orgs VAS Safer Payments. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |

## Response Type

[`OrgsVASSaferPaymentsResponseResult`](../../doc/models/orgs-vas-safer-payments-response-result.md)

## Example Usage

```php
$id = 't1_ovs_67ffd50aa5b2855bcd59e00';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$result = $orgsVASSaferPaymentsController->deleteOrgsVASSaferPaymentsId(
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
        "id": "t1_ovs_67ffd50aa5b2855bcd59e00",
        "created": "2025-04-16 12:04:26.6985",
        "modified": "2025-04-16 12:04:26.6985",
        "creator": "t1_log_65c6415ad9791e3796f739c",
        "modifier": "t1_log_65c6415ad9791e3796f739c",
        "org": "t1_org_67ffd5094c032a71089829d",
        "defaultProgram": "basic",
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


# Get Orgs VAS Safer Payments

Query a Orgs VAS Safer Payments.

```php
function getOrgsVASSaferPayments(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): OrgsVASSaferPaymentsResponseResult
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

[`OrgsVASSaferPaymentsResponseResult`](../../doc/models/orgs-vas-safer-payments-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $orgsVASSaferPaymentsController->getOrgsVASSaferPayments(
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
        "id": "t1_ovs_67ffd50aa5b2855bcd59e00",
        "created": "2025-04-16 12:04:26.6985",
        "modified": "2025-04-16 12:04:26.6985",
        "creator": "t1_log_65c6415ad9791e3796f739c",
        "modifier": "t1_log_65c6415ad9791e3796f739c",
        "org": "t1_org_67ffd5094c032a71089829d",
        "defaultProgram": "basic",
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


# Post Orgs VAS Safer Payments

Create a Orgs VAS Safer Payments.

```php
function postOrgsVASSaferPayments(
    OrgsVASSaferPaymentsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): OrgsVASSaferPaymentsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`OrgsVASSaferPaymentsPostRequest`](../../doc/models/orgs-vas-safer-payments-post-request.md) | Body, Required | - |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`OrgsVASSaferPaymentsResponseResult`](../../doc/models/orgs-vas-safer-payments-response-result.md)

## Example Usage

```php
$body = OrgsVASSaferPaymentsPostRequestBuilder::init()
    ->org('t1_org_680bfd2cea2729081810000')
    ->defaultProgram(OrgsVASSaferPaymentsDefaultProgramEnum::BASIC)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgsVASSaferPaymentsController->postOrgsVASSaferPayments(
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
        "id": "t1_ovs_67ffd50aa5b2855bcd59e00",
        "created": "2025-04-16 12:04:26.6985",
        "modified": "2025-04-16 12:04:26.6985",
        "creator": "t1_log_65c6415ad9791e3796f739c",
        "modifier": "t1_log_65c6415ad9791e3796f739c",
        "org": "t1_org_67ffd5094c032a71089829d",
        "defaultProgram": "basic",
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

