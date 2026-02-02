# Org Entities

```php
$orgEntitiesController = $client->getOrgEntitiesController();
```

## Class Name

`OrgEntitiesController`

## Methods

* [Get Org Entities Id](../../doc/controllers/org-entities.md#get-org-entities-id)
* [Put Org Entities Id](../../doc/controllers/org-entities.md#put-org-entities-id)
* [Delete Org Entities Id](../../doc/controllers/org-entities.md#delete-org-entities-id)
* [Get Org Entities](../../doc/controllers/org-entities.md#get-org-entities)
* [Post Org Entities](../../doc/controllers/org-entities.md#post-org-entities)


# Get Org Entities Id

Query an orgEntity.

```php
function getOrgEntitiesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): OrgEntitiesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and the Org Entity ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`OrgEntitiesResponseResult`](../../doc/models/org-entities-response-result.md)

## Example Usage

```php
$id = 'p1_oet_61c9a3e852a54260ebb505b';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgEntitiesController->getOrgEntitiesId(
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
        "id": "p1_oet_61c9a3e852a54260ebb505b",
        "created": "2025-03-06 08:32:24.3467",
        "modified": "2025-03-06 08:32:43.6505",
        "creator": "t1_log_67c56806038bb4eb85a0000",
        "modifier": "t1_log_67c56806038bb4eb85a0000",
        "org": "t1_org_00c56806038bb4eb85a0000",
        "entity": "p1_ent_01c96187e33536db84f8a62"
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


# Put Org Entities Id

Update an orgEntity.

```php
function putOrgEntitiesId(
    string $id,
    OrgEntitiesPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): OrgEntitiesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Org Entity ID. |
| `body` | [`OrgEntitiesPutRequest`](../../doc/models/org-entities-put-request.md) | Body, Required | Update an Org Entity Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`OrgEntitiesResponseResult`](../../doc/models/org-entities-response-result.md)

## Example Usage

```php
$id = 'p1_oet_61c9a3e852a54260ebb505b';

$body = OrgEntitiesPutRequestBuilder::init(
    't1_org_5b0e08025ec790d3f9b8c11',
    't1_ent_10c99d558e910765c164a01'
)->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgEntitiesController->putOrgEntitiesId(
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
        "id": "p1_oet_61c9a3e852a54260ebb505b",
        "created": "2025-03-06 08:32:24.3467",
        "modified": "2025-03-06 08:32:43.6505",
        "creator": "t1_log_67c56806038bb4eb85a0000",
        "modifier": "t1_log_67c56806038bb4eb85a0000",
        "org": "t1_org_00c56806038bb4eb85a0000",
        "entity": "p1_ent_01c96187e33536db84f8a62"
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


# Delete Org Entities Id

Delete an Org Entity. An orgEntity is a record of an association between a particular Org and a particular Entity. One Org can contain and be associated with many Entities.

```php
function deleteOrgEntitiesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): OrgEntitiesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Org Entity ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`OrgEntitiesResponseResult`](../../doc/models/org-entities-response-result.md)

## Example Usage

```php
$id = 'p1_oet_61c9a3e852a54260ebb505b';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgEntitiesController->deleteOrgEntitiesId(
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
        "id": "p1_oet_61c9a3e852a54260ebb505b",
        "created": "2025-03-06 08:32:24.3467",
        "modified": "2025-03-06 08:32:43.6505",
        "creator": "t1_log_67c56806038bb4eb85a0000",
        "modifier": "t1_log_67c56806038bb4eb85a0000",
        "org": "t1_org_00c56806038bb4eb85a0000",
        "entity": "p1_ent_01c96187e33536db84f8a62"
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


# Get Org Entities

Query an orgEntity.
An orgEntity is a record of an association between a particular Org and a particular Entity.
You can associate Entities with an Org by creating orgEntity resources. One Org can contain and be associated with many Entities.

```php
function getOrgEntities(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): OrgEntitiesResponseResult
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

[`OrgEntitiesResponseResult`](../../doc/models/org-entities-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $orgEntitiesController->getOrgEntities(
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
        "id": "p1_oet_61c9a3e852a54260ebb505b",
        "created": "2025-03-06 08:32:24.3467",
        "modified": "2025-03-06 08:32:43.6505",
        "creator": "t1_log_67c56806038bb4eb85a0000",
        "modifier": "t1_log_67c56806038bb4eb85a0000",
        "org": "t1_org_00c56806038bb4eb85a0000",
        "entity": "p1_ent_01c96187e33536db84f8a62"
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


# Post Org Entities

Create an orgEntity.
An orgEntity is a record of an association between a particular Org and a particular Entity.
You can associate Entities with an Org by creating orgEntity resources. One Org can contain and be associated with many Entities.

```php
function postOrgEntities(
    OrgEntitiesPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): OrgEntitiesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`OrgEntitiesPostRequest`](../../doc/models/org-entities-post-request.md) | Body, Required | Create Org Entity Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`OrgEntitiesResponseResult`](../../doc/models/org-entities-response-result.md)

## Example Usage

```php
$body = OrgEntitiesPostRequestBuilder::init(
    't1_org_5b0e08025ec790d3f9b8c11',
    't1_ent_10c99d558e910765c164a01'
)->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgEntitiesController->postOrgEntities(
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
        "id": "p1_oet_61c9a3e852a54260ebb505b",
        "created": "2025-03-06 08:32:24.3467",
        "modified": "2025-03-06 08:32:43.6505",
        "creator": "t1_log_67c56806038bb4eb85a0000",
        "modifier": "t1_log_67c56806038bb4eb85a0000",
        "org": "t1_org_00c56806038bb4eb85a0000",
        "entity": "p1_ent_01c96187e33536db84f8a62"
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

