# Team Logins

```php
$teamLoginsController = $client->getTeamLoginsController();
```

## Class Name

`TeamLoginsController`

## Methods

* [Get Team Logins Id](../../doc/controllers/team-logins.md#get-team-logins-id)
* [Put Team Logins Id](../../doc/controllers/team-logins.md#put-team-logins-id)
* [Delete Team Logins Id](../../doc/controllers/team-logins.md#delete-team-logins-id)
* [Get Team Logins](../../doc/controllers/team-logins.md#get-team-logins)
* [Post Team Logins](../../doc/controllers/team-logins.md#post-team-logins)


# Get Team Logins Id

Query a teamLogins or Team Login resource that represents the link between a Login and a Team as well as the Login's rights on the Team, where the Login resource identified in its 'login' field is considered part of the Team.

```php
function getTeamLoginsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): TeamLoginResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this team login. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`TeamLoginResponseResult`](../../doc/models/team-login-response-result.md)

## Example Usage

```php
$id = 't1_tel_6802c54d22f16393d4be00z';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $teamLoginsController->getTeamLoginsId(
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
        "id": "t1_tel_6802c54d22f16393d4be00z",
        "created": "2025-04-18 17:34:05.1626",
        "modified": "2025-04-18 17:34:05.1626",
        "creator": "t1_log_67c4d37d494077b9db8faf0",
        "modifier": "t1_log_67c4d37d494077b9db8faf0",
        "login": "t1_log_6802c54cba888f6abfd88cc",
        "team": "t1_tem_6621af6c10f4a29427a2d35",
        "create": 0,
        "read": 0,
        "update": 0,
        "delete": 0,
        "reference": 0,
        "teamAdmin": 0
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


# Put Team Logins Id

Update a teamLogins or Team Login resource, representing the link between a Login and a Team as well as the Login's rights on the Team, where the Login resource identified in its 'login' field is considered part of the Team.

```php
function putTeamLoginsId(
    string $id,
    TeamLoginPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): TeamLoginResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this team's login. |
| `body` | [`TeamLoginPutRequest`](../../doc/models/team-login-put-request.md) | Body, Required | Update Team Login Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`TeamLoginResponseResult`](../../doc/models/team-login-response-result.md)

## Example Usage

```php
$id = 't1_tel_6802c54d22f16393d4be00z';

$body = TeamLoginPutRequestBuilder::init()
    ->login('t1_log_6802c54cba888f6abfd88cc')
    ->team('t1_tem_6621af6c10f4a29427a2d35')
    ->create(TeamLoginCreateEnum::NONE)
    ->read(TeamLoginReadEnum::NONE)
    ->update(TeamLoginUpdateEnum::NONE)
    ->delete(TeamLoginDeleteEnum::NONE)
    ->reference(TeamLoginReferenceEnum::NONE)
    ->teamAdmin(TeamLoginTeamAdminEnum::NONE)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $teamLoginsController->putTeamLoginsId(
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
        "id": "t1_tel_6802c54d22f16393d4be00z",
        "created": "2025-04-18 17:34:05.1626",
        "modified": "2025-04-18 17:34:05.1626",
        "creator": "t1_log_67c4d37d494077b9db8faf0",
        "modifier": "t1_log_67c4d37d494077b9db8faf0",
        "login": "t1_log_6802c54cba888f6abfd88cc",
        "team": "t1_tem_6621af6c10f4a29427a2d35",
        "create": 0,
        "read": 0,
        "update": 0,
        "delete": 0,
        "reference": 0,
        "teamAdmin": 0
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


# Delete Team Logins Id

Delete a Team Login, which represents the link between a Login and a Team as well as the Login's rights on the Team, where the Login resource identified in its 'login' field is considered part of the Team.

```php
function deleteTeamLoginsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): TeamLoginResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this team login. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`TeamLoginResponseResult`](../../doc/models/team-login-response-result.md)

## Example Usage

```php
$id = 't1_tel_6802c54d22f16393d4be00z';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $teamLoginsController->deleteTeamLoginsId(
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
        "id": "t1_tel_6802c54d22f16393d4be00z",
        "created": "2025-04-18 17:34:05.1626",
        "modified": "2025-04-18 17:34:05.1626",
        "creator": "t1_log_67c4d37d494077b9db8faf0",
        "modifier": "t1_log_67c4d37d494077b9db8faf0",
        "login": "t1_log_6802c54cba888f6abfd88cc",
        "team": "t1_tem_6621af6c10f4a29427a2d35",
        "create": 0,
        "read": 0,
        "update": 0,
        "delete": 0,
        "reference": 0,
        "teamAdmin": 0
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


# Get Team Logins

Query a teamLogins resource.
A teamLogins resource represents the link between a Login and a Team as well as the Login's rights on the Team. The Login resource identified in its 'login' field is considered part of the Team.

```php
function getTeamLogins(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): TeamLoginResponseResult
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

[`TeamLoginResponseResult`](../../doc/models/team-login-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $teamLoginsController->getTeamLogins(
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
        "id": "t1_tel_6802c54d22f16393d4be00z",
        "created": "2025-04-18 17:34:05.1626",
        "modified": "2025-04-18 17:34:05.1626",
        "creator": "t1_log_67c4d37d494077b9db8faf0",
        "modifier": "t1_log_67c4d37d494077b9db8faf0",
        "login": "t1_log_6802c54cba888f6abfd88cc",
        "team": "t1_tem_6621af6c10f4a29427a2d35",
        "create": 0,
        "read": 0,
        "update": 0,
        "delete": 0,
        "reference": 0,
        "teamAdmin": 0
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


# Post Team Logins

Create a teamLogins resource.
A teamLogins resource represents the link between a Login and a Team as well as the Login's rights on the Team. The Login resource identified in its 'login' field is considered part of the Team.

```php
function postTeamLogins(
    TeamLoginPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): TeamLoginResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`TeamLoginPostRequest`](../../doc/models/team-login-post-request.md) | Body, Required | Create Team Login Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`TeamLoginResponseResult`](../../doc/models/team-login-response-result.md)

## Example Usage

```php
$body = TeamLoginPostRequestBuilder::init(
    't1_log_6802c54cba888f6abfd88cc',
    't1_tem_6621af6c10f4a29427a2d35'
)
    ->create(TeamLoginCreateEnum::NONE)
    ->read(TeamLoginReadEnum::NONE)
    ->update(TeamLoginUpdateEnum::NONE)
    ->delete(TeamLoginDeleteEnum::NONE)
    ->reference(TeamLoginReferenceEnum::NONE)
    ->teamAdmin(TeamLoginTeamAdminEnum::NONE)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $teamLoginsController->postTeamLogins(
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
        "id": "t1_tel_6802c54d22f16393d4be00z",
        "created": "2025-04-18 17:34:05.1626",
        "modified": "2025-04-18 17:34:05.1626",
        "creator": "t1_log_67c4d37d494077b9db8faf0",
        "modifier": "t1_log_67c4d37d494077b9db8faf0",
        "login": "t1_log_6802c54cba888f6abfd88cc",
        "team": "t1_tem_6621af6c10f4a29427a2d35",
        "create": 0,
        "read": 0,
        "update": 0,
        "delete": 0,
        "reference": 0,
        "teamAdmin": 0
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

