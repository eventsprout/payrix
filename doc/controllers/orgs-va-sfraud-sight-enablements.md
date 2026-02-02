# Orgs VA Sfraud Sight Enablements

```php
$orgsVASfraudSightEnablementsController = $client->getOrgsVASfraudSightEnablementsController();
```

## Class Name

`OrgsVASfraudSightEnablementsController`

## Methods

* [Get Orgs VAS Fraud Sight Enablements Id](../../doc/controllers/orgs-va-sfraud-sight-enablements.md#get-orgs-vas-fraud-sight-enablements-id)
* [Delete Orgs VAS Fraud Sight Enablements Id](../../doc/controllers/orgs-va-sfraud-sight-enablements.md#delete-orgs-vas-fraud-sight-enablements-id)
* [Get Orgs VAS Fraud Sight Enablements](../../doc/controllers/orgs-va-sfraud-sight-enablements.md#get-orgs-vas-fraud-sight-enablements)
* [Post Orgs VAS Fraud Sight Enablements](../../doc/controllers/orgs-va-sfraud-sight-enablements.md#post-orgs-vas-fraud-sight-enablements)


# Get Orgs VAS Fraud Sight Enablements Id

Query a OrgsVASFraudSightEnablements. an Entity.

```php
function getOrgsVASFraudSightEnablementsId(
    string $orgId,
    string $id,
    ?string $requestToken = null,
    ?string $embed = null
): OrgsVASFraudSightEnablementsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `orgId` | `string` | Template, Required | The Org ID this fraud sight enablement belongs to. |
| `id` | `string` | Template, Required | The ID of this resource. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`OrgsVASFraudSightEnablementsResponseResult`](../../doc/models/orgs-vas-fraud-sight-enablements-response-result.md)

## Example Usage

```php
$orgId = 't1_org_680bfd2cea2729081810000';

$id = 't1_ovf_67a18bcde1a1b2ec3d9c9az';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgsVASFraudSightEnablementsController->getOrgsVASFraudSightEnablementsId(
    $orgId,
    $id,
    $requestToken
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_ovf_67a18bcde1a1b2ec3d9c9az",
        "created": "2025-07-31 08:42:16.7318",
        "modified": "2025-07-31 08:42:16.7318",
        "creator": "t1_log_0092b50e8812b18e41d511s",
        "modifier": "t1_log_0092b50e8812b18e41d511s",
        "org": "t1_org_680bfd2cea2729081810000",
        "groupName": "PIECPA",
        "description": "Post Network -Decision Non EMV CP & Inform remaining CP",
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


# Delete Orgs VAS Fraud Sight Enablements Id

Delete Orgs VAS Fraud Sight Enablements.

```php
function deleteOrgsVASFraudSightEnablementsId(
    string $orgId,
    string $id
): OrgsVASFraudSightEnablementsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `orgId` | `string` | Template, Required | The Org ID this fraud sight enablement belongs to. |
| `id` | `string` | Template, Required | The ID of this Orgs VAS Fraud Sight Enablements. |

## Response Type

[`OrgsVASFraudSightEnablementsResponseResult`](../../doc/models/orgs-vas-fraud-sight-enablements-response-result.md)

## Example Usage

```php
$orgId = 't1_org_680bfd2cea2729081810000';

$id = 't1_ovf_67ffd50aa5b2855bcd59e00';

$result = $orgsVASFraudSightEnablementsController->deleteOrgsVASFraudSightEnablementsId(
    $orgId,
    $id
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_ovf_67a18bcde1a1b2ec3d9c9az",
        "created": "2025-07-31 08:42:16.7318",
        "modified": "2025-07-31 08:42:16.7318",
        "creator": "t1_log_0092b50e8812b18e41d511s",
        "modifier": "t1_log_0092b50e8812b18e41d511s",
        "org": "t1_org_680bfd2cea2729081810000",
        "groupName": "PIECPA",
        "description": "Post Network -Decision Non EMV CP & Inform remaining CP",
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


# Get Orgs VAS Fraud Sight Enablements

Query all OrgsVASFraudSightEnablements.

```php
function getOrgsVASFraudSightEnablements(
    string $orgId,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): OrgsVASFraudSightEnablementsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `orgId` | `string` | Template, Required | The Org ID this fraud sight enablement belongs to. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `search` | `?string` | Header, Optional | Set this header to filter or sort the list of resources that the method returns.<br>See [Searches](page:welcome#searches) for detailed information and examples on how to use search header. |
| `totals` | `?string` | Header, Optional | To configure a request to return a total for all instances of a field in a result set,  use the totals header in the format `totals={operator}[]={key}`.  This will calculate the desired total and return it in the `details > totals` object of the response.  For instance, if you want to sum the `total` field of all transactions,  you would use the `sum` operator. The response will include the result set,  along with the calculated total in the `details` section. See [Collection Operators](page:welcome#collection-operators) for detailed information and examples on how to use totals header. |
| `pageNumber` | `?int` | Query, Optional | Set this path parameter to request a specific page of records.<br>For example, set `?page[number]=2` to retrieve the second page of records for this request. |
| `pageLimit` | `?int` | Query, Optional | Set this path parameter to request up to a specific amount of records. By default 30 records are retrieved per page. The maximum limit that can be set is 100.<br>For example, set `?page[limit]=50` to retrieve up to 50 records for this request. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`OrgsVASFraudSightEnablementsResponseResult`](../../doc/models/orgs-vas-fraud-sight-enablements-response-result.md)

## Example Usage

```php
$orgId = 't1_org_680bfd2cea2729081810000';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $orgsVASFraudSightEnablementsController->getOrgsVASFraudSightEnablements(
    $orgId,
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
        "id": "t1_ovf_67a18bcde1a1b2ec3d9c9az",
        "created": "2025-07-31 08:42:16.7318",
        "modified": "2025-07-31 08:42:16.7318",
        "creator": "t1_log_0092b50e8812b18e41d511s",
        "modifier": "t1_log_0092b50e8812b18e41d511s",
        "org": "t1_org_680bfd2cea2729081810000",
        "groupName": "PIECPA",
        "description": "Post Network -Decision Non EMV CP & Inform remaining CP",
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


# Post Orgs VAS Fraud Sight Enablements

Create a OrgsVASFraudSightEnablement.

```php
function postOrgsVASFraudSightEnablements(
    string $orgId,
    OrgsVASFraudSightEnablementsPostRequest $body,
    ?string $requestToken = null
): OrgsVASFraudSightEnablementsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `orgId` | `string` | Template, Required | The Org ID this fraud sight enablement belongs to. |
| `body` | [`OrgsVASFraudSightEnablementsPostRequest`](../../doc/models/orgs-vas-fraud-sight-enablements-post-request.md) | Body, Required | Add OrgsVASFraudSightEnablement Request |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`OrgsVASFraudSightEnablementsResponseResult`](../../doc/models/orgs-vas-fraud-sight-enablements-response-result.md)

## Example Usage

```php
$orgId = 't1_org_680bfd2cea2729081810000';

$body = OrgsVASFraudSightEnablementsPostRequestBuilder::init(
    't1_org_680bfd2cea2729081810000',
    GroupNameEnum::PIECPA,
    'The description of the Group Name.'
)->build();

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgsVASFraudSightEnablementsController->postOrgsVASFraudSightEnablements(
    $orgId,
    $body,
    $requestToken
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_ovf_67a18bcde1a1b2ec3d9c9az",
        "created": "2025-07-31 08:42:16.7318",
        "modified": "2025-07-31 08:42:16.7318",
        "creator": "t1_log_0092b50e8812b18e41d511s",
        "modifier": "t1_log_0092b50e8812b18e41d511s",
        "org": "t1_org_680bfd2cea2729081810000",
        "groupName": "PIECPA",
        "description": "Post Network -Decision Non EMV CP & Inform remaining CP",
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

