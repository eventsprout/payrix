# Decision Actions

```php
$decisionActionsController = $client->getDecisionActionsController();
```

## Class Name

`DecisionActionsController`

## Methods

* [Get Decision Actions Id](../../doc/controllers/decision-actions.md#get-decision-actions-id)
* [Put Decision Actions Id](../../doc/controllers/decision-actions.md#put-decision-actions-id)
* [Delete Decision Actions Id](../../doc/controllers/decision-actions.md#delete-decision-actions-id)
* [Get Decision Actions](../../doc/controllers/decision-actions.md#get-decision-actions)
* [Post Decision Actions](../../doc/controllers/decision-actions.md#post-decision-actions)


# Get Decision Actions Id

Query a Decision Action, which is a piece of conditional logic that makes a VerificationResult change the application and the decision action in certain circumstances.

```php
function getDecisionActionsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): DecisionActionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Decision Action ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`DecisionActionsResponseResult`](../../doc/models/decision-actions-response-result.md)

## Example Usage

```php
$id = 't1_dca_67ddc0163f51a4ffd1ea3d0';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $decisionActionsController->getDecisionActionsId(
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
        "id": "p1_dca_67e284e38e9613fb4b69e6d",
        "created": "2025-03-25 06:26:43.5877",
        "modified": "2025-03-25 06:26:43.5877",
        "creator": "t1_log_61e72ab44fd39df9483aa2c",
        "modifier": "t1_log_61e72ab44fd39df9483aa2c",
        "decision": "t1_dcs_67ddc0163a32ae0c5c33bfc",
        "action": 1,
        "application": "account",
        "scoreType": "low",
        "type": "less",
        "field": "score",
        "score": "20",
        "data": "dummy@dummy.neoncrm.com",
        "message": "Required",
        "code": "I602",
        "grouping": "bademail",
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


# Put Decision Actions Id

Update a Decision Action, which is a piece of conditional logic that makes a VerificationResult change the application and the decision action in certain circumstances.

```php
function putDecisionActionsId(
    string $id,
    DecisionActionsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): DecisionActionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Decision Action ID. |
| `body` | [`DecisionActionsPutRequest`](../../doc/models/decision-actions-put-request.md) | Body, Required | Update Decision Action Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`DecisionActionsResponseResult`](../../doc/models/decision-actions-response-result.md)

## Example Usage

```php
$id = 't1_dca_67ddc0163f51a4ffd1ea3d0';

$body = DecisionActionsPutRequestBuilder::init()
    ->decision('t1_dcs_67ddc0163a32ae0c5c33bfc')
    ->action(DescisionActionsActionEnum::BLOCK)
    ->application(DecisionActionsApplicationEnum::ACCOUNT)
    ->scoreType(DecisionActionsScoreTypeEnum::LOW)
    ->type(DecisionActionTypeEnum::LESS)
    ->field('score')
    ->score('20')
    ->data('dummy@dummy.neoncrm.com')
    ->message('Required')
    ->code('I602')
    ->grouping('bademail')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $decisionActionsController->putDecisionActionsId(
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
        "id": "p1_dca_67e284e38e9613fb4b69e6d",
        "created": "2025-03-25 06:26:43.5877",
        "modified": "2025-03-25 06:26:43.5877",
        "creator": "t1_log_61e72ab44fd39df9483aa2c",
        "modifier": "t1_log_61e72ab44fd39df9483aa2c",
        "decision": "t1_dcs_67ddc0163a32ae0c5c33bfc",
        "action": 1,
        "application": "account",
        "scoreType": "low",
        "type": "less",
        "field": "score",
        "score": "20",
        "data": "dummy@dummy.neoncrm.com",
        "message": "Required",
        "code": "I602",
        "grouping": "bademail",
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


# Delete Decision Actions Id

Delete a Decision Action. A Decision Action is a piece of conditional logic that makes a VerificationResult change the application and the decision action in certain circumstances.

```php
function deleteDecisionActionsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): DecisionActionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Decision Action ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`DecisionActionsResponseResult`](../../doc/models/decision-actions-response-result.md)

## Example Usage

```php
$id = 't1_dca_67ddc0163f51a4ffd1ea3d0';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $decisionActionsController->deleteDecisionActionsId(
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
        "id": "p1_dca_67e284e38e9613fb4b69e6d",
        "created": "2025-03-25 06:26:43.5877",
        "modified": "2025-03-25 06:26:43.5877",
        "creator": "t1_log_61e72ab44fd39df9483aa2c",
        "modifier": "t1_log_61e72ab44fd39df9483aa2c",
        "decision": "t1_dcs_67ddc0163a32ae0c5c33bfc",
        "action": 1,
        "application": "account",
        "scoreType": "low",
        "type": "less",
        "field": "score",
        "score": "20",
        "data": "dummy@dummy.neoncrm.com",
        "message": "Required",
        "code": "I602",
        "grouping": "bademail",
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


# Get Decision Actions

Query a Decision Action, A Decision Action is a piece of conditional logic that makes a VerificationResult change the application and the decision action in certain circumstances.

```php
function getDecisionActions(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): DecisionActionsResponseResult
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

[`DecisionActionsResponseResult`](../../doc/models/decision-actions-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $decisionActionsController->getDecisionActions(
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
        "id": "p1_dca_67e284e38e9613fb4b69e6d",
        "created": "2025-03-25 06:26:43.5877",
        "modified": "2025-03-25 06:26:43.5877",
        "creator": "t1_log_61e72ab44fd39df9483aa2c",
        "modifier": "t1_log_61e72ab44fd39df9483aa2c",
        "decision": "t1_dcs_67ddc0163a32ae0c5c33bfc",
        "action": 1,
        "application": "account",
        "scoreType": "low",
        "type": "less",
        "field": "score",
        "score": "20",
        "data": "dummy@dummy.neoncrm.com",
        "message": "Required",
        "code": "I602",
        "grouping": "bademail",
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


# Post Decision Actions

Create a Decision Action in conjunction with This resource, which is used to further tune the reactions based on conditions defined in the DecisionAction.

```php
function postDecisionActions(
    DecisionActionsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): DecisionActionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`DecisionActionsPostRequest`](../../doc/models/decision-actions-post-request.md) | Body, Required | Create Decision Action Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`DecisionActionsResponseResult`](../../doc/models/decision-actions-response-result.md)

## Example Usage

```php
$body = DecisionActionsPostRequestBuilder::init(
    't1_dcs_67ddc0163a32ae0c5c33bfc'
)
    ->action(DescisionActionsActionEnum::BLOCK)
    ->application(DecisionActionsApplicationEnum::ACCOUNT)
    ->scoreType(DecisionActionsScoreTypeEnum::LOW)
    ->type(DecisionActionTypeEnum::LESS)
    ->field('score')
    ->score('20')
    ->data('dummy@dummy.neoncrm.com')
    ->message('Required')
    ->code('I602')
    ->grouping('bademail')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $decisionActionsController->postDecisionActions(
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
        "id": "p1_dca_67e284e38e9613fb4b69e6d",
        "created": "2025-03-25 06:26:43.5877",
        "modified": "2025-03-25 06:26:43.5877",
        "creator": "t1_log_61e72ab44fd39df9483aa2c",
        "modifier": "t1_log_61e72ab44fd39df9483aa2c",
        "decision": "t1_dcs_67ddc0163a32ae0c5c33bfc",
        "action": 1,
        "application": "account",
        "scoreType": "low",
        "type": "less",
        "field": "score",
        "score": "20",
        "data": "dummy@dummy.neoncrm.com",
        "message": "Required",
        "code": "I602",
        "grouping": "bademail",
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

