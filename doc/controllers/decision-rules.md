# Decision Rules

```php
$decisionRulesController = $client->getDecisionRulesController();
```

## Class Name

`DecisionRulesController`

## Methods

* [Get Decision Rules Id](../../doc/controllers/decision-rules.md#get-decision-rules-id)
* [Put Decision Rules Id](../../doc/controllers/decision-rules.md#put-decision-rules-id)
* [Delete Decision Rules Id](../../doc/controllers/decision-rules.md#delete-decision-rules-id)
* [Get Decision Rules](../../doc/controllers/decision-rules.md#get-decision-rules)
* [Post Decision Rules](../../doc/controllers/decision-rules.md#post-decision-rules)


# Get Decision Rules Id

Query a Decision Rule that makes a Decision apply only in certain circumstances, such as applying an administration charge if a payment is under $50.

```php
function getDecisionRulesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): DecisionRulesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Decision Rule ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`DecisionRulesResponseResult`](../../doc/models/decision-rules-response-result.md)

## Example Usage

```php
$id = 't1_drl_67d9836cb20781126c769f0';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $decisionRulesController->getDecisionRulesId(
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
        "id": "t1_drl_67d9836cb20781126c769f0",
        "created": "2025-03-18 10:30:04.7380",
        "modified": "2025-03-18 10:30:04.7380",
        "creator": "t1_log_5ade08dbe7c74ccfa14e832",
        "modifier": "t1_log_5ade08dbe7c74ccfa14e832",
        "decision": "t1_dcs_67d97ed1a0fc6848c89d537",
        "name": "DecisionRule11",
        "description": "Rule Description",
        "type": "type",
        "value": 8,
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


# Put Decision Rules Id

Update a Decision Rule that makes a Decision apply only in certain circumstances, for example, applying an administration charge if a payment is under $50.

```php
function putDecisionRulesId(
    string $id,
    DecisionRulesPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): DecisionRulesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Decision Rule ID. |
| `body` | [`DecisionRulesPutRequest`](../../doc/models/decision-rules-put-request.md) | Body, Required | Update Decision Rule Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`DecisionRulesResponseResult`](../../doc/models/decision-rules-response-result.md)

## Example Usage

```php
$id = 't1_drl_67d9836cb20781126c769f0';

$body = DecisionRulesPutRequestBuilder::init()
    ->decision('t1_dcs_67d97ed1a0fc6848c89d537')
    ->name('DecisionRule11')
    ->description('Rule Description')
    ->type(DecisionRuleTypeEnum::TYPE)
    ->value(8)
    ->grouping('portalgroup_2')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $decisionRulesController->putDecisionRulesId(
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
        "id": "t1_drl_67d9836cb20781126c769f0",
        "created": "2025-03-18 10:30:04.7380",
        "modified": "2025-03-18 10:30:04.7380",
        "creator": "t1_log_5ade08dbe7c74ccfa14e832",
        "modifier": "t1_log_5ade08dbe7c74ccfa14e832",
        "decision": "t1_dcs_67d97ed1a0fc6848c89d537",
        "name": "DecisionRule11",
        "description": "Rule Description",
        "type": "type",
        "value": 8,
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


# Delete Decision Rules Id

Delete a Decision Rule that makes a Decision apply only in certain circumstances, for example, applying an administration charge if a payment is under $50.

```php
function deleteDecisionRulesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): DecisionRulesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Decision Rule ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`DecisionRulesResponseResult`](../../doc/models/decision-rules-response-result.md)

## Example Usage

```php
$id = 't1_drl_67d9836cb20781126c769f0';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $decisionRulesController->deleteDecisionRulesId(
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
        "id": "t1_drl_67d9836cb20781126c769f0",
        "created": "2025-03-18 10:30:04.7380",
        "modified": "2025-03-18 10:30:04.7380",
        "creator": "t1_log_5ade08dbe7c74ccfa14e832",
        "modifier": "t1_log_5ade08dbe7c74ccfa14e832",
        "decision": "t1_dcs_67d97ed1a0fc6848c89d537",
        "name": "DecisionRule11",
        "description": "Rule Description",
        "type": "type",
        "value": 8,
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


# Get Decision Rules

Query a Decision Rule; A Decision Rule is a piece of conditional logic that makes a Decision apply only in certain circumstances, For example, a Decision Rule could apply an administration charge if a payment is under $50.

```php
function getDecisionRules(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): DecisionRulesResponseResult
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

[`DecisionRulesResponseResult`](../../doc/models/decision-rules-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $decisionRulesController->getDecisionRules(
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
        "id": "t1_drl_67d9836cb20781126c769f0",
        "created": "2025-03-18 10:30:04.7380",
        "modified": "2025-03-18 10:30:04.7380",
        "creator": "t1_log_5ade08dbe7c74ccfa14e832",
        "modifier": "t1_log_5ade08dbe7c74ccfa14e832",
        "decision": "t1_dcs_67d97ed1a0fc6848c89d537",
        "name": "DecisionRule11",
        "description": "Rule Description",
        "type": "type",
        "value": 8,
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


# Post Decision Rules

Create a Decision Rule that makes a Decision apply only in certain circumstances, such as applying an administration charge if a payment is under $50.

```php
function postDecisionRules(
    DecisionRulesPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): DecisionRulesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`DecisionRulesPostRequest`](../../doc/models/decision-rules-post-request.md) | Body, Required | Create Decision Rule Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`DecisionRulesResponseResult`](../../doc/models/decision-rules-response-result.md)

## Example Usage

```php
$body = DecisionRulesPostRequestBuilder::init(
    't1_dcs_67d97ed1a0fc6848c89d537',
    DecisionRuleTypeEnum::TYPE,
    8
)
    ->name('DecisionRule11')
    ->description('Rule Description')
    ->grouping('portalgroup_2')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $decisionRulesController->postDecisionRules(
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
        "id": "t1_drl_67d9836cb20781126c769f0",
        "created": "2025-03-18 10:30:04.7380",
        "modified": "2025-03-18 10:30:04.7380",
        "creator": "t1_log_5ade08dbe7c74ccfa14e832",
        "modifier": "t1_log_5ade08dbe7c74ccfa14e832",
        "decision": "t1_dcs_67d97ed1a0fc6848c89d537",
        "name": "DecisionRule11",
        "description": "Rule Description",
        "type": "type",
        "value": 8,
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

