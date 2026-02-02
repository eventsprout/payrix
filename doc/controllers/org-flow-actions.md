# Org Flow Actions

```php
$orgFlowActionsController = $client->getOrgFlowActionsController();
```

## Class Name

`OrgFlowActionsController`

## Methods

* [Get Org Flow Actions Id](../../doc/controllers/org-flow-actions.md#get-org-flow-actions-id)
* [Put Org Flow Actions Id](../../doc/controllers/org-flow-actions.md#put-org-flow-actions-id)
* [Delete Org Flow Actions Id](../../doc/controllers/org-flow-actions.md#delete-org-flow-actions-id)
* [Get Org Flow Actions](../../doc/controllers/org-flow-actions.md#get-org-flow-actions)
* [Post Org Flow Actions](../../doc/controllers/org-flow-actions.md#post-org-flow-actions)


# Get Org Flow Actions Id

Query an Org Flow Actions resource.

```php
function getOrgFlowActionsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): OrgFlowActionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource or The Org Flow Action ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`OrgFlowActionsResponseResult`](../../doc/models/org-flow-actions-response-result.md)

## Example Usage

```php
$id = 't1_ofa_67ed51ecf3330d5d808000z';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgFlowActionsController->getOrgFlowActionsId(
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
        "id": "t1_ofa_67ed51ecf3330d5d808000z",
        "created": "2025-04-02 11:04:13.0043",
        "modified": "2025-04-02 11:04:13.0043",
        "creator": "t1_log_63335e0e83c545bbb91d9ac",
        "modifier": "t1_log_63335e0e83c545bbb91d9ac",
        "orgFlow": "t1_ofw_67ed51ece84aae1a7d0783z",
        "org": "t1_org_67c89c538efe67fbf018d00",
        "action": "add"
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


# Put Org Flow Actions Id

Update an Org Flow Action.

```php
function putOrgFlowActionsId(
    string $id,
    OrgFlowActionsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): OrgFlowActionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource or The Org Flow Action ID. |
| `body` | [`OrgFlowActionsPutRequest`](../../doc/models/org-flow-actions-put-request.md) | Body, Required | Update an Org Flow Action Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`OrgFlowActionsResponseResult`](../../doc/models/org-flow-actions-response-result.md)

## Example Usage

```php
$id = 't1_ofa_67ed51ecf3330d5d808000z';

$body = OrgFlowActionsPutRequestBuilder::init(
    't1_ofw_67ed51ece84aae1a7d0783z',
    't1_org_67c89c538efe67fbf018d00',
    OrgFlowActionEnum::ADD
)->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgFlowActionsController->putOrgFlowActionsId(
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
        "id": "t1_ofa_67ed51ecf3330d5d808000z",
        "created": "2025-04-02 11:04:13.0043",
        "modified": "2025-04-02 11:04:13.0043",
        "creator": "t1_log_63335e0e83c545bbb91d9ac",
        "modifier": "t1_log_63335e0e83c545bbb91d9ac",
        "orgFlow": "t1_ofw_67ed51ece84aae1a7d0783z",
        "org": "t1_org_67c89c538efe67fbf018d00",
        "action": "add"
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


# Delete Org Flow Actions Id

Delete an Org Flow Action.

```php
function deleteOrgFlowActionsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): OrgFlowActionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource or The Org Flow Action ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`OrgFlowActionsResponseResult`](../../doc/models/org-flow-actions-response-result.md)

## Example Usage

```php
$id = 't1_ofa_67ed51ecf3330d5d808000z';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgFlowActionsController->deleteOrgFlowActionsId(
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
        "id": "t1_ofa_67ed51ecf3330d5d808000z",
        "created": "2025-04-02 11:04:13.0043",
        "modified": "2025-04-02 11:04:13.0043",
        "creator": "t1_log_63335e0e83c545bbb91d9ac",
        "modifier": "t1_log_63335e0e83c545bbb91d9ac",
        "orgFlow": "t1_ofw_67ed51ece84aae1a7d0783z",
        "org": "t1_org_67c89c538efe67fbf018d00",
        "action": "add"
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


# Get Org Flow Actions

Query an orgFlowActions resource.
An orgFlowActions resource lets you add an Entity defined in the associated orgFlow to an Org, or remove an Entity identified in the same way from an Org.

```php
function getOrgFlowActions(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): OrgFlowActionsResponseResult
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

[`OrgFlowActionsResponseResult`](../../doc/models/org-flow-actions-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $orgFlowActionsController->getOrgFlowActions(
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
        "id": "t1_ofa_67ed51ecf3330d5d808000z",
        "created": "2025-04-02 11:04:13.0043",
        "modified": "2025-04-02 11:04:13.0043",
        "creator": "t1_log_63335e0e83c545bbb91d9ac",
        "modifier": "t1_log_63335e0e83c545bbb91d9ac",
        "orgFlow": "t1_ofw_67ed51ece84aae1a7d0783z",
        "org": "t1_org_67c89c538efe67fbf018d00",
        "action": "add"
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


# Post Org Flow Actions

Create an Org Flow Action that lets you add an Entity defined in the associated orgFlow to an Org, or remove an Entity identified in the same way from an Org.

```php
function postOrgFlowActions(
    OrgFlowActionsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): OrgFlowActionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`OrgFlowActionsPostRequest`](../../doc/models/org-flow-actions-post-request.md) | Body, Required | Create Org Flow Action Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`OrgFlowActionsResponseResult`](../../doc/models/org-flow-actions-response-result.md)

## Example Usage

```php
$body = OrgFlowActionsPostRequestBuilder::init(
    't1_ofw_67ed51ece84aae1a7d0783z',
    't1_org_67c89c538efe67fbf018d00',
    OrgFlowActionEnum::ADD
)->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgFlowActionsController->postOrgFlowActions(
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
        "id": "t1_ofa_67ed51ecf3330d5d808000z",
        "created": "2025-04-02 11:04:13.0043",
        "modified": "2025-04-02 11:04:13.0043",
        "creator": "t1_log_63335e0e83c545bbb91d9ac",
        "modifier": "t1_log_63335e0e83c545bbb91d9ac",
        "orgFlow": "t1_ofw_67ed51ece84aae1a7d0783z",
        "org": "t1_org_67c89c538efe67fbf018d00",
        "action": "add"
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

