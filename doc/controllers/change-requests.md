# Change Requests

```php
$changeRequestsController = $client->getChangeRequestsController();
```

## Class Name

`ChangeRequestsController`

## Methods

* [Get Change Requests Id](../../doc/controllers/change-requests.md#get-change-requests-id)
* [Delete Change Requests Id](../../doc/controllers/change-requests.md#delete-change-requests-id)
* [Get Change Requests](../../doc/controllers/change-requests.md#get-change-requests)


# Get Change Requests Id

Query a Change Request.
ChangeRequests is a resource that manages changes to a certain resource.

```php
function getChangeRequestsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): ChangeRequestsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`ChangeRequestsResponseResult`](../../doc/models/change-requests-response-result.md)

## Example Usage

```php
$id = 't1_chr_67461c21ce3bae674b5500a';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $changeRequestsController->getChangeRequestsId(
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
        "id": "t1_chr_67461c21ce3bae674b5500a",
        "created": "2024-11-26 14:06:09.8529",
        "modified": "2024-11-26 14:06:10.1982",
        "creator": "t1_log_5c758e990c7a922100d4f36",
        "modifier": "t1_log_5c758e990c7a922100d4f36",
        "deleted": "2024-11-26 14:06:10",
        "login": "t1_log_5c758e990c7a922100d4f36",
        "operation": "update",
        "status": "manualReview",
        "reason": "",
        "changes": "{\"account\":{\"method\":8,\"number\":\"4444\",\"routing\":\"3123\"},\"primary\":1}",
        "model": "accounts",
        "recordId": "t1_act_6491d8a2bbbae477f00e5d0",
        "reasonType": "",
        "analyst": "",
        "reviewed": "2024-11-26 14:06:10",
        "entity": "t1_ent_6491d8a2b75c8b71b1d6c96",
        "authType": 3
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


# Delete Change Requests Id

Delete a Change Request.
ChangeRequests is a resource that manages changes to a certain resource.

```php
function deleteChangeRequestsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): ChangeRequestsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ChangeRequestsResponseResult`](../../doc/models/change-requests-response-result.md)

## Example Usage

```php
$id = 't1_chr_67461c21ce3bae674b5500a';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $changeRequestsController->deleteChangeRequestsId(
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
        "id": "t1_chr_67461c21ce3bae674b5500a",
        "created": "2024-11-26 14:06:09.8529",
        "modified": "2024-11-26 14:06:10.1982",
        "creator": "t1_log_5c758e990c7a922100d4f36",
        "modifier": "t1_log_5c758e990c7a922100d4f36",
        "deleted": "2024-11-26 14:06:10",
        "login": "t1_log_5c758e990c7a922100d4f36",
        "operation": "update",
        "status": "manualReview",
        "reason": "",
        "changes": "{\"account\":{\"method\":8,\"number\":\"4444\",\"routing\":\"3123\"},\"primary\":1}",
        "model": "accounts",
        "recordId": "t1_act_6491d8a2bbbae477f00e5d0",
        "reasonType": "",
        "analyst": "",
        "reviewed": "2024-11-26 14:06:10",
        "entity": "t1_ent_6491d8a2b75c8b71b1d6c96",
        "authType": 3
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


# Get Change Requests

Query a Change Request.
ChangeRequests is a resource that manages changes to a certain resource.

```php
function getChangeRequests(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): ChangeRequestsResponseResult
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

[`ChangeRequestsResponseResult`](../../doc/models/change-requests-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $changeRequestsController->getChangeRequests(
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
        "id": "t1_chr_67461c21ce3bae674b5500a",
        "created": "2024-11-26 14:06:09.8529",
        "modified": "2024-11-26 14:06:10.1982",
        "creator": "t1_log_5c758e990c7a922100d4f36",
        "modifier": "t1_log_5c758e990c7a922100d4f36",
        "deleted": "2024-11-26 14:06:10",
        "login": "t1_log_5c758e990c7a922100d4f36",
        "operation": "update",
        "status": "manualReview",
        "reason": "",
        "changes": "{\"account\":{\"method\":8,\"number\":\"4444\",\"routing\":\"3123\"},\"primary\":1}",
        "model": "accounts",
        "recordId": "t1_act_6491d8a2bbbae477f00e5d0",
        "reasonType": "",
        "analyst": "",
        "reviewed": "2024-11-26 14:06:10",
        "entity": "t1_ent_6491d8a2b75c8b71b1d6c96",
        "authType": 3
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

