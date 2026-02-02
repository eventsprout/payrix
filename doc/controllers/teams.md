# Teams

A team is an arbitrary grouping of user records that may have access provisioned on each other and can be attached to other resources as a unit for shared functionality.

```php
$teamsController = $client->getTeamsController();
```

## Class Name

`TeamsController`

## Methods

* [Get Teams Id](../../doc/controllers/teams.md#get-teams-id)
* [Put Teams Id](../../doc/controllers/teams.md#put-teams-id)
* [Delete Teams Id](../../doc/controllers/teams.md#delete-teams-id)
* [Get Teams](../../doc/controllers/teams.md#get-teams)
* [Post Teams](../../doc/controllers/teams.md#post-teams)


# Get Teams Id

Query a Team, which is a collection of Logins that you can associate by creating teamLogin resources.

```php
function getTeamsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): TeamsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this team. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`TeamsResponseResult`](../../doc/models/teams-response-result.md)

## Example Usage

```php
$id = 't1_tem_680155b5a6467e4911aa0z0';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $teamsController->getTeamsId(
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
        "id": "t1_tem_680155b5a6467e4911aa0z0",
        "created": "2025-04-17 15:25:41.6956",
        "modified": "2025-04-17 15:25:41.6956",
        "creator": "t1_log_5deeafd8b9b491e28296a51",
        "modifier": "t1_log_5deeafd8b9b491e28296a51",
        "login": "t1_log_6801559c6218199cb0820df",
        "name": "merchant-team-t1_mer_680155985dbaab55256ecb0",
        "description": "Esmeralda McCullough Team",
        "autoCascadeDisabled": 0,
        "inactive": 0,
        "frozen": 0,
        "autoCascadeOwner": 0
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


# Put Teams Id

Update a Team, A Team is a collection of Logins, You can associate Logins with a Team by creating teamLogin resources.

```php
function putTeamsId(
    string $id,
    TeamsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): TeamsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this team. |
| `body` | [`TeamsPutRequest`](../../doc/models/teams-put-request.md) | Body, Required | Update Team Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`TeamsResponseResult`](../../doc/models/teams-response-result.md)

## Example Usage

```php
$id = 't1_tem_680155b5a6467e4911aa0z0';

$body = TeamsPutRequestBuilder::init()
    ->login('t1_log_6801559c6218199cb0820df')
    ->name('merchant-team-t1_mer_680155985dbaab55256ecb0')
    ->description('Esmeralda McCullough Team')
    ->autoCascadeDisabled(TeamsAutoCascadeDisabledEnum::DISABLED)
    ->autoCascadeOwner(TeamsAutoCascadeOwnerEnum::OFF)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $teamsController->putTeamsId(
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
        "id": "t1_tem_680155b5a6467e4911aa0z0",
        "created": "2025-04-17 15:25:41.6956",
        "modified": "2025-04-17 15:25:41.6956",
        "creator": "t1_log_5deeafd8b9b491e28296a51",
        "modifier": "t1_log_5deeafd8b9b491e28296a51",
        "login": "t1_log_6801559c6218199cb0820df",
        "name": "merchant-team-t1_mer_680155985dbaab55256ecb0",
        "description": "Esmeralda McCullough Team",
        "autoCascadeDisabled": 0,
        "inactive": 0,
        "frozen": 0,
        "autoCascadeOwner": 0
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


# Delete Teams Id

Delete a Team, A Team is a collection of Logins, You can associate Logins with a Team by creating teamLogin resources.

```php
function deleteTeamsId(string $id, ?string $token = null, ?string $requestToken = null): TeamsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this team. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`TeamsResponseResult`](../../doc/models/teams-response-result.md)

## Example Usage

```php
$id = 't1_tem_680155b5a6467e4911aa0z0';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $teamsController->deleteTeamsId(
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
        "id": "t1_tem_680155b5a6467e4911aa0z0",
        "created": "2025-04-17 15:25:41.6956",
        "modified": "2025-04-17 15:25:41.6956",
        "creator": "t1_log_5deeafd8b9b491e28296a51",
        "modifier": "t1_log_5deeafd8b9b491e28296a51",
        "login": "t1_log_6801559c6218199cb0820df",
        "name": "merchant-team-t1_mer_680155985dbaab55256ecb0",
        "description": "Esmeralda McCullough Team",
        "autoCascadeDisabled": 0,
        "inactive": 0,
        "frozen": 0,
        "autoCascadeOwner": 0
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


# Get Teams

Query a Team.
A Team is a collection of Logins.
You can associate Logins with a Team by creating teamLogin resources.

```php
function getTeams(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): TeamsResponseResult
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

[`TeamsResponseResult`](../../doc/models/teams-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $teamsController->getTeams(
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
        "id": "t1_tem_680155b5a6467e4911aa0z0",
        "created": "2025-04-17 15:25:41.6956",
        "modified": "2025-04-17 15:25:41.6956",
        "creator": "t1_log_5deeafd8b9b491e28296a51",
        "modifier": "t1_log_5deeafd8b9b491e28296a51",
        "login": "t1_log_6801559c6218199cb0820df",
        "name": "merchant-team-t1_mer_680155985dbaab55256ecb0",
        "description": "Esmeralda McCullough Team",
        "autoCascadeDisabled": 0,
        "inactive": 0,
        "frozen": 0,
        "autoCascadeOwner": 0
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


# Post Teams

Create a Team.
A Team is a collection of Logins.
You can associate Logins with a Team by creating teamLogin resources.

```php
function postTeams(
    TeamsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): TeamsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`TeamsPostRequest`](../../doc/models/teams-post-request.md) | Body, Required | Create Team Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`TeamsResponseResult`](../../doc/models/teams-response-result.md)

## Example Usage

```php
$body = TeamsPostRequestBuilder::init(
    't1_log_6801559c6218199cb0820df'
)
    ->name('merchant-team-t1_mer_680155985dbaab55256ecb0')
    ->description('Esmeralda McCullough Team')
    ->autoCascadeDisabled(TeamsAutoCascadeDisabledEnum::DISABLED)
    ->autoCascadeOwner(TeamsAutoCascadeOwnerEnum::OFF)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $teamsController->postTeams(
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
        "id": "t1_tem_680155b5a6467e4911aa0z0",
        "created": "2025-04-17 15:25:41.6956",
        "modified": "2025-04-17 15:25:41.6956",
        "creator": "t1_log_5deeafd8b9b491e28296a51",
        "modifier": "t1_log_5deeafd8b9b491e28296a51",
        "login": "t1_log_6801559c6218199cb0820df",
        "name": "merchant-team-t1_mer_680155985dbaab55256ecb0",
        "description": "Esmeralda McCullough Team",
        "autoCascadeDisabled": 0,
        "inactive": 0,
        "frozen": 0,
        "autoCascadeOwner": 0
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

