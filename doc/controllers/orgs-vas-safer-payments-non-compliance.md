# Orgs VAS Safer Payments Non-Compliance

```php
$orgsVASSaferPaymentsNonComplianceController = $client->getOrgsVASSaferPaymentsNonComplianceController();
```

## Class Name

`OrgsVASSaferPaymentsNonComplianceController`

## Methods

* [Get Orgs VAS Safer Payments Non Compliance Id](../../doc/controllers/orgs-vas-safer-payments-non-compliance.md#get-orgs-vas-safer-payments-non-compliance-id)
* [Delete Orgs VAS Safer Payments Non Compliance Id](../../doc/controllers/orgs-vas-safer-payments-non-compliance.md#delete-orgs-vas-safer-payments-non-compliance-id)
* [Get Orgs VAS Safer Payments Non Compliance](../../doc/controllers/orgs-vas-safer-payments-non-compliance.md#get-orgs-vas-safer-payments-non-compliance)
* [Post Orgs VAS Safer Payments Non Compliance](../../doc/controllers/orgs-vas-safer-payments-non-compliance.md#post-orgs-vas-safer-payments-non-compliance)


# Get Orgs VAS Safer Payments Non Compliance Id

Query Orgs VAS Safer Payments Non-compliance.

```php
function getOrgsVASSaferPaymentsNonComplianceId(
    string $id,
    ?string $token = null
): OrgsVASSaferPaymentsNonComplianceResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource, or the (unknown) ID associated with the Orgs VAS Safer Payments Non-compliance. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |

## Response Type

[`OrgsVASSaferPaymentsNonComplianceResponseResult`](../../doc/models/orgs-vas-safer-payments-non-compliance-response-result.md)

## Example Usage

```php
$id = 't1_ovsn_67ffd50aa5b2855bcd59e00';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$result = $orgsVASSaferPaymentsNonComplianceController->getOrgsVASSaferPaymentsNonComplianceId(
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
        "id": "t1_ovsn_67ffd50aa5b2855bcd59e00",
        "created": "2025-04-16 12:04:26.6985",
        "modified": "2025-04-16 12:04:26.6985",
        "creator": "t1_log_65c6415ad9791e3796f739c",
        "modifier": "t1_log_65c6415ad9791e3796f739c",
        "org": "t1_org_67ffd5094c032a71089829d",
        "division": "t1_div_67ffd5094c032a71089829d",
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


# Delete Orgs VAS Safer Payments Non Compliance Id

Delete Orgs VAS Safer Payments Non-compliance.

```php
function deleteOrgsVASSaferPaymentsNonComplianceId(
    string $id,
    ?string $token = null
): OrgsVASSaferPaymentsNonComplianceResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this Orgs VAS Safer Payments Non-compliance. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |

## Response Type

[`OrgsVASSaferPaymentsNonComplianceResponseResult`](../../doc/models/orgs-vas-safer-payments-non-compliance-response-result.md)

## Example Usage

```php
$id = 't1_ovsn_67ffd50aa5b2855bcd59e00';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$result = $orgsVASSaferPaymentsNonComplianceController->deleteOrgsVASSaferPaymentsNonComplianceId(
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
        "id": "t1_ovsn_67ffd50aa5b2855bcd59e00",
        "created": "2025-04-16 12:04:26.6985",
        "modified": "2025-04-16 12:04:26.6985",
        "creator": "t1_log_65c6415ad9791e3796f739c",
        "modifier": "t1_log_65c6415ad9791e3796f739c",
        "org": "t1_org_67ffd5094c032a71089829d",
        "division": "t1_div_67ffd5094c032a71089829d",
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


# Get Orgs VAS Safer Payments Non Compliance

Query a Orgs VAS Safer Payments Non-compliance.

```php
function getOrgsVASSaferPaymentsNonCompliance(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null
): OrgsVASSaferPaymentsNonComplianceResponseResult
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

## Response Type

[`OrgsVASSaferPaymentsNonComplianceResponseResult`](../../doc/models/orgs-vas-safer-payments-non-compliance-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $orgsVASSaferPaymentsNonComplianceController->getOrgsVASSaferPaymentsNonCompliance(
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
        "id": "t1_ovsn_67ffd50aa5b2855bcd59e00",
        "created": "2025-04-16 12:04:26.6985",
        "modified": "2025-04-16 12:04:26.6985",
        "creator": "t1_log_65c6415ad9791e3796f739c",
        "modifier": "t1_log_65c6415ad9791e3796f739c",
        "org": "t1_org_67ffd5094c032a71089829d",
        "division": "t1_div_67ffd5094c032a71089829d",
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


# Post Orgs VAS Safer Payments Non Compliance

Create a Orgs VAS Safer Payments Non-compliance.

```php
function postOrgsVASSaferPaymentsNonCompliance(
    OrgsVASSaferPaymentsNonCompliancePostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): OrgsVASSaferPaymentsNonComplianceResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`OrgsVASSaferPaymentsNonCompliancePostRequest`](../../doc/models/orgs-vas-safer-payments-non-compliance-post-request.md) | Body, Required | - |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`OrgsVASSaferPaymentsNonComplianceResponseResult`](../../doc/models/orgs-vas-safer-payments-non-compliance-response-result.md)

## Example Usage

```php
$body = OrgsVASSaferPaymentsNonCompliancePostRequestBuilder::init(
    't1_org_680bfd2cea2729081810000',
    't1_div_680bfd2cea2729081810000'
)->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgsVASSaferPaymentsNonComplianceController->postOrgsVASSaferPaymentsNonCompliance(
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
        "id": "t1_ovsn_67ffd50aa5b2855bcd59e00",
        "created": "2025-04-16 12:04:26.6985",
        "modified": "2025-04-16 12:04:26.6985",
        "creator": "t1_log_65c6415ad9791e3796f739c",
        "modifier": "t1_log_65c6415ad9791e3796f739c",
        "org": "t1_org_67ffd5094c032a71089829d",
        "division": "t1_div_67ffd5094c032a71089829d",
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

