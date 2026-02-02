# Orgs

Resource that deals with records of all orgs. An org is an arbitrary grouping of entity records that can be attached to other resources as a unit for shared functionality.

```php
$orgsController = $client->getOrgsController();
```

## Class Name

`OrgsController`

## Methods

* [Get Orgs Id](../../doc/controllers/orgs.md#get-orgs-id)
* [Put Orgs Id](../../doc/controllers/orgs.md#put-orgs-id)
* [Delete Orgs Id](../../doc/controllers/orgs.md#delete-orgs-id)
* [Get Orgs](../../doc/controllers/orgs.md#get-orgs)
* [Post Orgs](../../doc/controllers/orgs.md#post-orgs)


# Get Orgs Id

Query an Org, which is a collection of Entities that you can associate with by creating orgEntity resources.

```php
function getOrgsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): OrgsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and the Org ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`OrgsResponseResult`](../../doc/models/orgs-response-result.md)

## Example Usage

```php
$id = 't1_org_67cab1c56e1fd4f4c0a355z';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgsController->getOrgsId(
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
        "id": "t1_org_67cab1c56e1fd4f4c0a000z",
        "created": "2025-03-07 03:43:49.4586",
        "modified": "2025-03-07 03:43:49.4586",
        "creator": "t1_log_656d51cd565edf13a27c494",
        "modifier": "t1_log_656d51cd565edf13a27c494",
        "login": "t1_log_656d51cd565edf13a27c494",
        "name": "Leora44",
        "description": "description of Org",
        "defaultFeeFromEntity": ""
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


# Put Orgs Id

Update an Org, which is a collection of Entities that you can associate with other entities by creating orgEntity resources.

```php
function putOrgsId(
    string $id,
    OrgsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): OrgsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and the Org ID. |
| `body` | [`OrgsPutRequest`](../../doc/models/orgs-put-request.md) | Body, Required | Update an Org Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`OrgsResponseResult`](../../doc/models/orgs-response-result.md)

## Example Usage

```php
$id = 't1_org_67cab1c56e1fd4f4c0a355z';

$body = OrgsPutRequestBuilder::init()
    ->login('t1_log_656d51cd565edf13a27c494')
    ->name('Leora44')
    ->description('description of Org')
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgsController->putOrgsId(
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
        "id": "t1_org_67cab1c56e1fd4f4c0a000z",
        "created": "2025-03-07 03:43:49.4586",
        "modified": "2025-03-07 03:43:49.4586",
        "creator": "t1_log_656d51cd565edf13a27c494",
        "modifier": "t1_log_656d51cd565edf13a27c494",
        "login": "t1_log_656d51cd565edf13a27c494",
        "name": "Leora44",
        "description": "description of Org",
        "defaultFeeFromEntity": ""
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


# Delete Orgs Id

Delete an Organization, which is a collection of Entities that you can associate with it by creating organization-entity resources.

```php
function deleteOrgsId(string $id, ?string $token = null, ?string $requestToken = null): OrgsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Org ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`OrgsResponseResult`](../../doc/models/orgs-response-result.md)

## Example Usage

```php
$id = 't1_org_67cab1c56e1fd4f4c0a355z';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgsController->deleteOrgsId(
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
        "id": "t1_org_67cab1c56e1fd4f4c0a000z",
        "created": "2025-03-07 03:43:49.4586",
        "modified": "2025-03-07 03:43:49.4586",
        "creator": "t1_log_656d51cd565edf13a27c494",
        "modifier": "t1_log_656d51cd565edf13a27c494",
        "login": "t1_log_656d51cd565edf13a27c494",
        "name": "Leora44",
        "description": "description of Org",
        "defaultFeeFromEntity": ""
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


# Get Orgs

Query an Org, which is a collection of Entities, To associate Entities with an Org use the [orgEntity](../../doc/controllers/org-entities.md#get-org-entities-id) endpoint. You will need the created Org ID when adding entities, such as a Merchant, to the Organization.

```php
function getOrgs(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): OrgsResponseResult
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

[`OrgsResponseResult`](../../doc/models/orgs-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $orgsController->getOrgs(
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
        "id": "t1_org_67cab1c56e1fd4f4c0a000z",
        "created": "2025-03-07 03:43:49.4586",
        "modified": "2025-03-07 03:43:49.4586",
        "creator": "t1_log_656d51cd565edf13a27c494",
        "modifier": "t1_log_656d51cd565edf13a27c494",
        "login": "t1_log_656d51cd565edf13a27c494",
        "name": "Leora44",
        "description": "description of Org",
        "defaultFeeFromEntity": ""
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


# Post Orgs

Create an Org which is a collection of Entities, To associate Entities with an Org use the [orgEntity](../../doc/controllers/org-entities.md#get-org-entities-id) endpoint. You will need the created Org ID when adding entities, such as a Merchant, to the Organization.

```php
function postOrgs(
    OrgsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): OrgsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`OrgsPostRequest`](../../doc/models/orgs-post-request.md) | Body, Required | Create Org Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`OrgsResponseResult`](../../doc/models/orgs-response-result.md)

## Example Usage

```php
$body = OrgsPostRequestBuilder::init()
    ->login('t1_log_656d51cd565edf13a27c494')
    ->name('Leora44')
    ->description('description of Org')
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgsController->postOrgs(
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
        "id": "t1_org_67cab1c56e1fd4f4c0a000z",
        "created": "2025-03-07 03:43:49.4586",
        "modified": "2025-03-07 03:43:49.4586",
        "creator": "t1_log_656d51cd565edf13a27c494",
        "modifier": "t1_log_656d51cd565edf13a27c494",
        "login": "t1_log_656d51cd565edf13a27c494",
        "name": "Leora44",
        "description": "description of Org",
        "defaultFeeFromEntity": ""
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

