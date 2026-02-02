# Sessions

Resources that deals with secret (private) and public (publishable) user session keys for authentication in API interactions.

```php
$sessionsController = $client->getSessionsController();
```

## Class Name

`SessionsController`

## Methods

* [Get Sessions Id](../../doc/controllers/sessions.md#get-sessions-id)
* [Delete Sessions Id](../../doc/controllers/sessions.md#delete-sessions-id)
* [Get Sessions](../../doc/controllers/sessions.md#get-sessions)
* [Post Sessions](../../doc/controllers/sessions.md#post-sessions)


# Get Sessions Id

Querying a session resource represents a third-party session who interacts with the API, for example, a referral platform.

```php
function getSessionsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): SessionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this session, The session ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`SessionsResponseResult`](../../doc/models/sessions-response-result.md)

## Example Usage

```php
$id = 'p1_ssn_00c741e02fbbe0645cb1fe7';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $sessionsController->getSessionsId(
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
        "id": "p1_ssn_00c73b181e33818d7c0a13a",
        "created": "2025-03-04 12:40:40.1366",
        "modified": "2025-03-04 12:40:40.1366",
        "creator": "p1_log_00a4d56d1b5c98e8694ae28",
        "modifier": "p1_log_00a4d56d1b5c98e8694ae28",
        "login": "p1_log_00a4d56d1b5c98e8694ae28",
        "key": "c00a5aafb5dd5352dc1fd656f4a4252c",
        "public": 1,
        "inactive": 0,
        "frozen": 0,
        "token": 0,
        "sso": 0,
        "mfaAuthenticated": 0
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


# Delete Sessions Id

Query a Statement.
A Statement resource represents the total collection of funds owed for a Billing period.

```php
function deleteSessionsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): SessionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`SessionsResponseResult`](../../doc/models/sessions-response-result.md)

## Example Usage

```php
$id = 'p1_ssn_00c741e02fbbe0645cb1fe7';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $sessionsController->deleteSessionsId(
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
        "id": "p1_ssn_00c73b181e33818d7c0a13a",
        "created": "2025-03-04 12:40:40.1366",
        "modified": "2025-03-04 12:40:40.1366",
        "creator": "p1_log_00a4d56d1b5c98e8694ae28",
        "modifier": "p1_log_00a4d56d1b5c98e8694ae28",
        "login": "p1_log_00a4d56d1b5c98e8694ae28",
        "key": "c00a5aafb5dd5352dc1fd656f4a4252c",
        "public": 1,
        "inactive": 0,
        "frozen": 0,
        "token": 0,
        "sso": 0,
        "mfaAuthenticated": 0
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


# Get Sessions

Query a Session.
A Session represents a temporary method of authentication to the API. Each Session expires automatically after 30 minutes of inactivity.
They are similar to API Keys (/apikeys) in their capabilities and field structure - but unlike API Keys, Sessions are not permanent.

```php
function getSessions(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): SessionsPostResponseResult
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

[`SessionsPostResponseResult`](../../doc/models/sessions-post-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $sessionsController->getSessions(
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
        "id": "p1_ssn_00c73b181e33818d7c0a13a",
        "created": "2025-03-04 12:40:40.1366",
        "modified": "2025-03-04 12:40:40.1366",
        "creator": "p1_log_00a4d56d1b5c98e8694ae28",
        "modifier": "p1_log_00a4d56d1b5c98e8694ae28",
        "login": "p1_log_00a4d56d1b5c98e8694ae28",
        "key": "c00a5aafb5dd5352dc1fd656f4a4252c",
        "public": 1,
        "inactive": 0,
        "frozen": 0,
        "token": 0,
        "sso": 0,
        "mfaAuthenticated": 0,
        "effectiveRoles": 562949953421302,
        "effectiveResources": ""
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


# Post Sessions

Create a Session.
A Session represents a temporary method of authentication to the API. Each Session expires automatically after 30 minutes of inactivity.
They are similar to API Keys (/apikeys) in their capabilities and field structure - but unlike API Keys, Sessions are not permanent.

```php
function postSessions(
    SessionsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): SessionsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SessionsPostRequest`](../../doc/models/sessions-post-request.md) | Body, Required | Create Session Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`SessionsResponseResult`](../../doc/models/sessions-response-result.md)

## Example Usage

```php
$body = SessionsPostRequestBuilder::init()
    ->login('p1_log_00a4d56d1b5c98e8694ae28')
    ->public(SessionPublicEnum::PUBLICACCESS)
    ->token(SessionTokenEnum::AUTHTOKENDISABLED)
    ->mfaAuthenticated(SessionMfaAuthenticatedEnum::MFADISABLED)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $sessionsController->postSessions(
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
        "id": "p1_ssn_00c73b181e33818d7c0a13a",
        "created": "2025-03-04 12:40:40.1366",
        "modified": "2025-03-04 12:40:40.1366",
        "creator": "p1_log_00a4d56d1b5c98e8694ae28",
        "modifier": "p1_log_00a4d56d1b5c98e8694ae28",
        "login": "p1_log_00a4d56d1b5c98e8694ae28",
        "key": "c00a5aafb5dd5352dc1fd656f4a4252c",
        "public": 1,
        "inactive": 0,
        "frozen": 0,
        "token": 0,
        "sso": 0,
        "mfaAuthenticated": 0
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

