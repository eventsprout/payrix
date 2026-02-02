# Org Flows

```php
$orgFlowsController = $client->getOrgFlowsController();
```

## Class Name

`OrgFlowsController`

## Methods

* [Get Org Flows Id](../../doc/controllers/org-flows.md#get-org-flows-id)
* [Put Org Flows Id](../../doc/controllers/org-flows.md#put-org-flows-id)
* [Delete Org Flows Id](../../doc/controllers/org-flows.md#delete-org-flows-id)
* [Get Org Flows](../../doc/controllers/org-flows.md#get-org-flows)
* [Post Org Flows](../../doc/controllers/org-flows.md#post-org-flows)


# Get Org Flows Id

Query an Org Flow represents a way to trigger the addition or removal of the Merchants associated with a Login to a particular Org, optionally setting this addition or removal to be recursive, affecting all Merchants in any child Logins.

```php
function getOrgFlowsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): OrgFlowsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource, also known as The Org Flow ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`OrgFlowsResponseResult`](../../doc/models/org-flows-response-result.md)

## Example Usage

```php
$id = 't1_ofw_67ed51ece84aae1a7d0000z';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgFlowsController->getOrgFlowsId(
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
        "id": "t1_ofw_67ed51ece84aae1a7d0000z",
        "created": "2025-04-07 09:47:34.4871",
        "modified": "2025-04-07 09:47:34.4871",
        "creator": "t1_log_63335e0e83c545bbb91d9ac",
        "modifier": "t1_log_63335e0e83c545bbb91d9ac",
        "login": "g1577139c2304b7",
        "forlogin": "t1_log_67c203583fbd0a4437d1332",
        "team": "t1_tem_67c202b908935b505104500",
        "division": "t1_div_67c56806728fbbf0bae0b10",
        "recursive": 0,
        "trigger": "create",
        "partition": "t1_ptn_666834d4d504f21414978f5"
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


# Put Org Flows Id

Update an Org Flow. An orgFlows resource represents a way to trigger the addition or removal of the Merchants associated with a Login to a particular Org, optionally set to be recursive, affecting all Merchants in any child Logins.

```php
function putOrgFlowsId(
    string $id,
    OrgFlowsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): OrgFlowsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Org Flow ID. |
| `body` | [`OrgFlowsPutRequest`](../../doc/models/org-flows-put-request.md) | Body, Required | Update an Org Flow Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`OrgFlowsResponseResult`](../../doc/models/org-flows-response-result.md)

## Example Usage

```php
$id = 't1_ofw_67ed51ece84aae1a7d0000z';

$body = OrgFlowsPutRequestBuilder::init(
    'g1577139c2304b7',
    OrgFlowTriggerEnum::CREATE
)
    ->forlogin('t1_log_67c203583fbd0a4437d1332')
    ->team('t1_tem_67c202b908935b505104500')
    ->division('t1_div_67c56806728fbbf0bae0b10')
    ->partition('t1_ptn_666834d4d504f21414978f5')
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgFlowsController->putOrgFlowsId(
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
        "id": "t1_ofw_67ed51ece84aae1a7d0000z",
        "created": "2025-04-07 09:47:34.4871",
        "modified": "2025-04-07 09:47:34.4871",
        "creator": "t1_log_63335e0e83c545bbb91d9ac",
        "modifier": "t1_log_63335e0e83c545bbb91d9ac",
        "login": "g1577139c2304b7",
        "forlogin": "t1_log_67c203583fbd0a4437d1332",
        "team": "t1_tem_67c202b908935b505104500",
        "division": "t1_div_67c56806728fbbf0bae0b10",
        "recursive": 0,
        "trigger": "create",
        "partition": "t1_ptn_666834d4d504f21414978f5"
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


# Delete Org Flows Id

Delete an Org Flow.

```php
function deleteOrgFlowsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): OrgFlowsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource, also known as The Org Flow ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`OrgFlowsResponseResult`](../../doc/models/org-flows-response-result.md)

## Example Usage

```php
$id = 't1_ofw_67ed51ece84aae1a7d0000z';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgFlowsController->deleteOrgFlowsId(
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
        "id": "t1_ofw_67ed51ece84aae1a7d0000z",
        "created": "2025-04-07 09:47:34.4871",
        "modified": "2025-04-07 09:47:34.4871",
        "creator": "t1_log_63335e0e83c545bbb91d9ac",
        "modifier": "t1_log_63335e0e83c545bbb91d9ac",
        "login": "g1577139c2304b7",
        "forlogin": "t1_log_67c203583fbd0a4437d1332",
        "team": "t1_tem_67c202b908935b505104500",
        "division": "t1_div_67c56806728fbbf0bae0b10",
        "recursive": 0,
        "trigger": "create",
        "partition": "t1_ptn_666834d4d504f21414978f5"
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


# Get Org Flows

Query an orgFlows resource.
An orgFlows resource represents a way to trigger the addition or removal of the Merchants associated with a Login to a particular Org.
You can optionally set this addition or removal to be recursive, affecting all Merchants in any child Logins.

```php
function getOrgFlows(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): OrgFlowsResponseResult
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

[`OrgFlowsResponseResult`](../../doc/models/org-flows-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $orgFlowsController->getOrgFlows(
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
        "id": "t1_ofw_67ed51ece84aae1a7d0000z",
        "created": "2025-04-07 09:47:34.4871",
        "modified": "2025-04-07 09:47:34.4871",
        "creator": "t1_log_63335e0e83c545bbb91d9ac",
        "modifier": "t1_log_63335e0e83c545bbb91d9ac",
        "login": "g1577139c2304b7",
        "forlogin": "t1_log_67c203583fbd0a4437d1332",
        "team": "t1_tem_67c202b908935b505104500",
        "division": "t1_div_67c56806728fbbf0bae0b10",
        "recursive": 0,
        "trigger": "create",
        "partition": "t1_ptn_666834d4d504f21414978f5"
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


# Post Org Flows

Create an orgFlows resource.
An orgFlows resource represents a way to trigger the addition or removal of the Merchants associated with a Login to a particular Org.
You can optionally set this addition or removal to be recursive, affecting all Merchants in any child Logins.

```php
function postOrgFlows(
    OrgFlowsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): OrgFlowsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`OrgFlowsPostRequest`](../../doc/models/org-flows-post-request.md) | Body, Required | Create Org Flow Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`OrgFlowsResponseResult`](../../doc/models/org-flows-response-result.md)

## Example Usage

```php
$body = OrgFlowsPostRequestBuilder::init(
    'g1577139c2304b7',
    OrgFlowTriggerEnum::CREATE
)
    ->forlogin('t1_log_67c203583fbd0a4437d1332')
    ->team('t1_tem_67c202b908935b505104500')
    ->division('t1_div_67c56806728fbbf0bae0b10')
    ->partition('t1_ptn_666834d4d504f21414978f5')
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgFlowsController->postOrgFlows(
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
        "id": "t1_ofw_67ed51ece84aae1a7d0000z",
        "created": "2025-04-07 09:47:34.4871",
        "modified": "2025-04-07 09:47:34.4871",
        "creator": "t1_log_63335e0e83c545bbb91d9ac",
        "modifier": "t1_log_63335e0e83c545bbb91d9ac",
        "login": "g1577139c2304b7",
        "forlogin": "t1_log_67c203583fbd0a4437d1332",
        "team": "t1_tem_67c202b908935b505104500",
        "division": "t1_div_67c56806728fbbf0bae0b10",
        "recursive": 0,
        "trigger": "create",
        "partition": "t1_ptn_666834d4d504f21414978f5"
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

