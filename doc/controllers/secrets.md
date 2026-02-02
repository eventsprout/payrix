# Secrets

Keys used to decrypt data or an indicator of which key to be used to decrypt data

```php
$secretsController = $client->getSecretsController();
```

## Class Name

`SecretsController`

## Methods

* [Get Secrets Id](../../doc/controllers/secrets.md#get-secrets-id)
* [Put Secrets Id](../../doc/controllers/secrets.md#put-secrets-id)
* [Delete Secrets Id](../../doc/controllers/secrets.md#delete-secrets-id)
* [Get Secrets](../../doc/controllers/secrets.md#get-secrets)
* [Post Secrets](../../doc/controllers/secrets.md#post-secrets)


# Get Secrets Id

Query a Secret, A Secret represents either a key used to decrypt data or an indicator of which key to be used to decrypt data.

```php
function getSecretsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): SecretsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this secret resource. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`SecretsResponseResult`](../../doc/models/secrets-response-result.md)

## Example Usage

```php
$id = 't1_sct_678933d597288379adacez0';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $secretsController->getSecretsId(
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
        "id": "t1_sct_678933d597288379adacez0",
        "created": "2025-01-16 11:29:09.6251",
        "modified": "2025-01-16 11:29:09.6251",
        "creator": "t1_log_63d2cddf694099bfb64e976",
        "modifier": "t1_log_63d2cddf694099bfb64e976",
        "login": "t1_log_63d2cddf694099bfb64e976",
        "entity": "g157715bca1f00z",
        "org": "t1_org_5fada4629c317f80bc9cb12",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "g157713aff9b946",
        "type": "privateKey",
        "platform": "APPLE",
        "name": "Test1",
        "description": "description1",
        "key": "529c5b7ac1d02079fc162a4fe3e32a020057f4b3d7b6225eb55bf8ec65257283",
        "locked": 0,
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


# Put Secrets Id

Update a Secret, A Secret represents either a key used to decrypt data or an indicator of which key to be used to decrypt data.

```php
function putSecretsId(
    string $id,
    SecretsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): SecretsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this secret resource. |
| `body` | [`SecretsPutRequest`](../../doc/models/secrets-put-request.md) | Body, Required | Update Secret Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`SecretsResponseResult`](../../doc/models/secrets-response-result.md)

## Example Usage

```php
$id = 't1_sct_678933d597288379adacez0';

$body = SecretsPutRequestBuilder::init()
    ->login('t1_log_63d2cddf694099bfb64e976')
    ->entity('g157715bca1f00z')
    ->org('t1_org_5fada4629c317f80bc9cb12')
    ->division('t1_div_67c56806728fbbf0bae0b00')
    ->partition('g157713aff9b946')
    ->type(SecretTypeEnum::PRIVATEKEY)
    ->platform(SecretsPlatformEnum::APPLE)
    ->name('Test1')
    ->description('description1')
    ->key('529c5b7ac1d02079fc162a4fe3e32a020057f4b3d7b6225eb55bf8ec65257283')
    ->locked(SecretLockedEnum::NOTLOCKED)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $secretsController->putSecretsId(
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
        "id": "t1_sct_678933d597288379adacez0",
        "created": "2025-01-16 11:29:09.6251",
        "modified": "2025-01-16 11:29:09.6251",
        "creator": "t1_log_63d2cddf694099bfb64e976",
        "modifier": "t1_log_63d2cddf694099bfb64e976",
        "login": "t1_log_63d2cddf694099bfb64e976",
        "entity": "g157715bca1f00z",
        "org": "t1_org_5fada4629c317f80bc9cb12",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "g157713aff9b946",
        "type": "privateKey",
        "platform": "APPLE",
        "name": "Test1",
        "description": "description1",
        "key": "529c5b7ac1d02079fc162a4fe3e32a020057f4b3d7b6225eb55bf8ec65257283",
        "locked": 0,
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


# Delete Secrets Id

Delete a Secret. A Secret represents either a key used to decrypt data or an indicator of which key to be used to decrypt data.

```php
function deleteSecretsId(string $id, ?string $token = null, ?string $requestToken = null): SecretsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this secret resource. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`SecretsResponseResult`](../../doc/models/secrets-response-result.md)

## Example Usage

```php
$id = 't1_sct_678933d597288379adacez0';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $secretsController->deleteSecretsId(
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
        "id": "t1_sct_678933d597288379adacez0",
        "created": "2025-01-16 11:29:09.6251",
        "modified": "2025-01-16 11:29:09.6251",
        "creator": "t1_log_63d2cddf694099bfb64e976",
        "modifier": "t1_log_63d2cddf694099bfb64e976",
        "login": "t1_log_63d2cddf694099bfb64e976",
        "entity": "g157715bca1f00z",
        "org": "t1_org_5fada4629c317f80bc9cb12",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "g157713aff9b946",
        "type": "privateKey",
        "platform": "APPLE",
        "name": "Test1",
        "description": "description1",
        "key": "529c5b7ac1d02079fc162a4fe3e32a020057f4b3d7b6225eb55bf8ec65257283",
        "locked": 0,
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


# Get Secrets

Query a Secret.
A Secret represents either a key used to decrypt data or an indicator of which key to be used to decrypt data.

```php
function getSecrets(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): SecretsResponseResult
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

[`SecretsResponseResult`](../../doc/models/secrets-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $secretsController->getSecrets(
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
        "id": "t1_sct_678933d597288379adacez0",
        "created": "2025-01-16 11:29:09.6251",
        "modified": "2025-01-16 11:29:09.6251",
        "creator": "t1_log_63d2cddf694099bfb64e976",
        "modifier": "t1_log_63d2cddf694099bfb64e976",
        "login": "t1_log_63d2cddf694099bfb64e976",
        "entity": "g157715bca1f00z",
        "org": "t1_org_5fada4629c317f80bc9cb12",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "g157713aff9b946",
        "type": "privateKey",
        "platform": "APPLE",
        "name": "Test1",
        "description": "description1",
        "key": "529c5b7ac1d02079fc162a4fe3e32a020057f4b3d7b6225eb55bf8ec65257283",
        "locked": 0,
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


# Post Secrets

Create a Secret.
A Secret represents either a key used to decrypt data or an indicator of which key to be used to decrypt data.

```php
function postSecrets(
    SecretsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): SecretsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SecretsPostRequest`](../../doc/models/secrets-post-request.md) | Body, Required | Create Secret Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`SecretsResponseResult`](../../doc/models/secrets-response-result.md)

## Example Usage

```php
$body = SecretsPostRequestBuilder::init(
    't1_log_63d2cddf694099bfb64e976',
    SecretTypeEnum::PRIVATEKEY,
    '529c5b7ac1d02079fc162a4fe3e32a020057f4b3d7b6225eb55bf8ec65257283'
)
    ->entity('g157715bca1f00z')
    ->org(
        't1_org_5fada4629c317f80bc9cb12'
    )
    ->division('t1_div_67c56806728fbbf0bae0b00')
    ->partition('g157713aff9b946')
    ->platform(SecretsPlatformEnum::APPLE)
    ->name('Test1')
    ->description('description1')
    ->locked(SecretLockedEnum::NOTLOCKED)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $secretsController->postSecrets(
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
        "id": "t1_sct_678933d597288379adacez0",
        "created": "2025-01-16 11:29:09.6251",
        "modified": "2025-01-16 11:29:09.6251",
        "creator": "t1_log_63d2cddf694099bfb64e976",
        "modifier": "t1_log_63d2cddf694099bfb64e976",
        "login": "t1_log_63d2cddf694099bfb64e976",
        "entity": "g157715bca1f00z",
        "org": "t1_org_5fada4629c317f80bc9cb12",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "g157713aff9b946",
        "type": "privateKey",
        "platform": "APPLE",
        "name": "Test1",
        "description": "description1",
        "key": "529c5b7ac1d02079fc162a4fe3e32a020057f4b3d7b6225eb55bf8ec65257283",
        "locked": 0,
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

