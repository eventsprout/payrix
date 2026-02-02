# Org Flow Rules

```php
$orgFlowRulesController = $client->getOrgFlowRulesController();
```

## Class Name

`OrgFlowRulesController`

## Methods

* [Get Org Flow Rules Id](../../doc/controllers/org-flow-rules.md#get-org-flow-rules-id)
* [Put Org Flow Rules Id](../../doc/controllers/org-flow-rules.md#put-org-flow-rules-id)
* [Delete Org Flow Rules Id](../../doc/controllers/org-flow-rules.md#delete-org-flow-rules-id)
* [Get Org Flow Rules](../../doc/controllers/org-flow-rules.md#get-org-flow-rules)
* [Post Org Flow Rules](../../doc/controllers/org-flow-rules.md#post-org-flow-rules)


# Get Org Flow Rules Id

Query an Org Flow Rules resource.

```php
function getOrgFlowRulesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): OrgFlowRulesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`OrgFlowRulesResponseResult`](../../doc/models/org-flow-rules-response-result.md)

## Example Usage

```php
$id = 't1_ofr_6810c6e4dad2480c7733b00';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgFlowRulesController->getOrgFlowRulesId(
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
        "id": "t1_ofr_6810c6e4dad2480c7733b00",
        "created": "2025-04-29 08:32:36.9093",
        "modified": "2025-04-29 08:37:03.2240",
        "creator": "t1_log_656d51cd565edf13a27c494",
        "modifier": "t1_log_656d51cd565edf13a27c494",
        "orgFlow": "t1_ofw_6810c6cfc7699f50be577dc",
        "name": "test1",
        "description": "test1 description",
        "type": "MCC",
        "value": "5552",
        "grouping": "portalgroup_2",
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


# Put Org Flow Rules Id

Update an Org Flow Rule.

```php
function putOrgFlowRulesId(
    string $id,
    OrgFlowRulesPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): OrgFlowRulesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource or The Org Flow Rule ID. |
| `body` | [`OrgFlowRulesPutRequest`](../../doc/models/org-flow-rules-put-request.md) | Body, Required | Update an Org Flow Rule Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`OrgFlowRulesResponseResult`](../../doc/models/org-flow-rules-response-result.md)

## Example Usage

```php
$id = 't1_ofr_6810c6e4dad2480c7733b00';

$body = OrgFlowRulesPutRequestBuilder::init()
    ->orgFlow('t1_ofr_6810c6e4dad2480c7733b00')
    ->name('Test1')
    ->description('Test1 Description')
    ->type(OrgFlowRulesTypeEnum::MCC)
    ->value('0742')
    ->grouping('portalgroup_2')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgFlowRulesController->putOrgFlowRulesId(
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
        "id": "t1_ofr_6810c6e4dad2480c7733b00",
        "created": "2025-04-29 08:32:36.9093",
        "modified": "2025-04-29 08:37:03.2240",
        "creator": "t1_log_656d51cd565edf13a27c494",
        "modifier": "t1_log_656d51cd565edf13a27c494",
        "orgFlow": "t1_ofw_6810c6cfc7699f50be577dc",
        "name": "test1",
        "description": "test1 description",
        "type": "MCC",
        "value": "5552",
        "grouping": "portalgroup_2",
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


# Delete Org Flow Rules Id

Delete an Org Flow Rule.

```php
function deleteOrgFlowRulesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): OrgFlowRulesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`OrgFlowRulesResponseResult`](../../doc/models/org-flow-rules-response-result.md)

## Example Usage

```php
$id = 't1_ofr_6810c6e4dad2480c7733b00';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgFlowRulesController->deleteOrgFlowRulesId(
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
        "id": "t1_ofr_6810c6e4dad2480c7733b00",
        "created": "2025-04-29 08:32:36.9093",
        "modified": "2025-04-29 08:37:03.2240",
        "creator": "t1_log_656d51cd565edf13a27c494",
        "modifier": "t1_log_656d51cd565edf13a27c494",
        "orgFlow": "t1_ofw_6810c6cfc7699f50be577dc",
        "name": "test1",
        "description": "test1 description",
        "type": "MCC",
        "value": "5552",
        "grouping": "portalgroup_2",
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


# Get Org Flow Rules

Query an orgFlowRules resource.

```php
function getOrgFlowRules(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): OrgFlowRulesResponseResult
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

[`OrgFlowRulesResponseResult`](../../doc/models/org-flow-rules-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $orgFlowRulesController->getOrgFlowRules(
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
        "id": "t1_ofr_6810c6e4dad2480c7733b00",
        "created": "2025-04-29 08:32:36.9093",
        "modified": "2025-04-29 08:37:03.2240",
        "creator": "t1_log_656d51cd565edf13a27c494",
        "modifier": "t1_log_656d51cd565edf13a27c494",
        "orgFlow": "t1_ofw_6810c6cfc7699f50be577dc",
        "name": "test1",
        "description": "test1 description",
        "type": "MCC",
        "value": "5552",
        "grouping": "portalgroup_2",
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


# Post Org Flow Rules

Create an Org Flow Rule.

```php
function postOrgFlowRules(
    OrgFlowRulesPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): OrgFlowRulesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`OrgFlowRulesPostRequest`](../../doc/models/org-flow-rules-post-request.md) | Body, Required | Create Org Flow Rule Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`OrgFlowRulesResponseResult`](../../doc/models/org-flow-rules-response-result.md)

## Example Usage

```php
$body = OrgFlowRulesPostRequestBuilder::init()
    ->orgFlow(
        't1_ofr_6810c6e4dad2480c7733b00'
    )
    ->name('Test1')
    ->description('Test1 Description')
    ->type(OrgFlowRulesTypeEnum::MCC)
    ->value('0742')
    ->grouping('portalgroup_2')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $orgFlowRulesController->postOrgFlowRules(
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
        "id": "t1_ofr_6810c6e4dad2480c7733b00",
        "created": "2025-04-29 08:32:36.9093",
        "modified": "2025-04-29 08:37:03.2240",
        "creator": "t1_log_656d51cd565edf13a27c494",
        "modifier": "t1_log_656d51cd565edf13a27c494",
        "orgFlow": "t1_ofw_6810c6cfc7699f50be577dc",
        "name": "test1",
        "description": "test1 description",
        "type": "MCC",
        "value": "5552",
        "grouping": "portalgroup_2",
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

