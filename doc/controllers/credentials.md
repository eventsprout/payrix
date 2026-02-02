# Credentials

Represents an authorization that a given Entity has to connect to an integration to perform a particular action, such as send Transactions to the processor, or board a Merchant with the processor.

```php
$credentialsController = $client->getCredentialsController();
```

## Class Name

`CredentialsController`

## Methods

* [Get Credentials Id](../../doc/controllers/credentials.md#get-credentials-id)
* [Put Credentials Id](../../doc/controllers/credentials.md#put-credentials-id)
* [Delete Credentials Id](../../doc/controllers/credentials.md#delete-credentials-id)
* [Get Credentials](../../doc/controllers/credentials.md#get-credentials)
* [Post Credentials](../../doc/controllers/credentials.md#post-credentials)


# Get Credentials Id

Query a Credential resource that represents an authorization that a given Entity has to connect to an integration to perform a particular action, such as send Transactions to the processor, or board a Merchant with the processor.

```php
function getCredentialsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): CredentialsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Credential ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`CredentialsResponseResult`](../../doc/models/credentials-response-result.md)

## Example Usage

```php
$id = 't1_cdt_67e152d9f0ef564f9b2c0d0';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $credentialsController->getCredentialsId(
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
        "id": "t1_cdt_67e152d9f0ef564f9b2c0d0",
        "created": "2025-03-24 08:40:57.9902",
        "modified": "2025-03-24 08:40:57.9902",
        "creator": "t1_log_67e152cfb94fe8d3c4bc950",
        "modifier": "t1_log_67e152cfb94fe8d3c4bc950",
        "entity": "t1_ent_67e152cfd598c814ed8f2e0",
        "name": "",
        "description": "",
        "username": "JDoe123",
        "password": "password1",
        "connectUsername": "",
        "connectPassword": "password",
        "integration": "VANTIV",
        "type": "transaction",
        "inactive": 0,
        "frozen": 0,
        "secret": ""
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


# Put Credentials Id

Update a Credential resource represents an authorization that a given Entity has to connect to an integration to perform a particular action.

```php
function putCredentialsId(
    string $id,
    CredentialsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): CredentialsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Credential ID. |
| `body` | [`CredentialsPutRequest`](../../doc/models/credentials-put-request.md) | Body, Required | Update Credential Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`CredentialsResponseResult`](../../doc/models/credentials-response-result.md)

## Example Usage

```php
$id = 't1_cdt_67e152d9f0ef564f9b2c0d0';

$body = CredentialsPutRequestBuilder::init()
    ->name('name of Credential resource')
    ->description('description of Credential resource')
    ->username('JDoe123')
    ->password('password')
    ->connectUsername('username connecting to integration')
    ->connectPassword('password')
    ->secret('secret resource identifier')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $credentialsController->putCredentialsId(
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
        "id": "t1_cdt_67e152d9f0ef564f9b2c0d0",
        "created": "2025-03-24 08:40:57.9902",
        "modified": "2025-03-24 08:40:57.9902",
        "creator": "t1_log_67e152cfb94fe8d3c4bc950",
        "modifier": "t1_log_67e152cfb94fe8d3c4bc950",
        "entity": "t1_ent_67e152cfd598c814ed8f2e0",
        "name": "",
        "description": "",
        "username": "JDoe123",
        "password": "password1",
        "connectUsername": "",
        "connectPassword": "password",
        "integration": "VANTIV",
        "type": "transaction",
        "inactive": 0,
        "frozen": 0,
        "secret": ""
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


# Delete Credentials Id

Delete a Credential resource. A Credential resource represents an authorization that a given Entity has to connect to an integration to perform a particular action, such as delete a Credential resource.

```php
function deleteCredentialsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): CredentialsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Credential ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`CredentialsResponseResult`](../../doc/models/credentials-response-result.md)

## Example Usage

```php
$id = 't1_cdt_67e152d9f0ef564f9b2c0d0';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $credentialsController->deleteCredentialsId(
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
        "id": "t1_cdt_67e152d9f0ef564f9b2c0d0",
        "created": "2025-03-24 08:40:57.9902",
        "modified": "2025-03-24 08:40:57.9902",
        "creator": "t1_log_67e152cfb94fe8d3c4bc950",
        "modifier": "t1_log_67e152cfb94fe8d3c4bc950",
        "entity": "t1_ent_67e152cfd598c814ed8f2e0",
        "name": "",
        "description": "",
        "username": "JDoe123",
        "password": "password1",
        "connectUsername": "",
        "connectPassword": "password",
        "integration": "VANTIV",
        "type": "transaction",
        "inactive": 0,
        "frozen": 0,
        "secret": ""
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


# Get Credentials

Query a Credential resource. A Credential resource represents an authorization that a given Entity has to connect to an integration to perform a particular action, such as send Transactions to the processor, or board a Merchant with the processor

```php
function getCredentials(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): CredentialsResponseResult
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

[`CredentialsResponseResult`](../../doc/models/credentials-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $credentialsController->getCredentials(
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
        "id": "t1_cdt_67e152d9f0ef564f9b2c0d0",
        "created": "2025-03-24 08:40:57.9902",
        "modified": "2025-03-24 08:40:57.9902",
        "creator": "t1_log_67e152cfb94fe8d3c4bc950",
        "modifier": "t1_log_67e152cfb94fe8d3c4bc950",
        "entity": "t1_ent_67e152cfd598c814ed8f2e0",
        "name": "",
        "description": "",
        "username": "JDoe123",
        "password": "password1",
        "connectUsername": "",
        "connectPassword": "password",
        "integration": "VANTIV",
        "type": "transaction",
        "inactive": 0,
        "frozen": 0,
        "secret": ""
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


# Post Credentials

Create a Credential resource that represents an authorization that a given Entity has to connect to an integration to perform a particular action, such as send Transactions to the processor, or board a Merchant with the processor.

```php
function postCredentials(
    CredentialsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): CredentialsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CredentialsPostRequest`](../../doc/models/credentials-post-request.md) | Body, Required | Create Credential Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`CredentialsResponseResult`](../../doc/models/credentials-response-result.md)

## Example Usage

```php
$body = CredentialsPostRequestBuilder::init(
    't1_ent_67e152cfd598c814ed8f2e0',
    'JDoe123',
    CredentialIntegrationEnum::VANTIV,
    CredentialTypeEnum::TRANSACTION
)
    ->name('name of Credential resource')
    ->description('description of Credential resource')
    ->password('password')
    ->connectUsername('username connecting to integration')
    ->connectPassword('password')
    ->secret('secret resource identifier')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $credentialsController->postCredentials(
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
        "id": "t1_cdt_67e152d9f0ef564f9b2c0d0",
        "created": "2025-03-24 08:40:57.9902",
        "modified": "2025-03-24 08:40:57.9902",
        "creator": "t1_log_67e152cfb94fe8d3c4bc950",
        "modifier": "t1_log_67e152cfb94fe8d3c4bc950",
        "entity": "t1_ent_67e152cfd598c814ed8f2e0",
        "name": "",
        "description": "",
        "username": "JDoe123",
        "password": "password1",
        "connectUsername": "",
        "connectPassword": "password",
        "integration": "VANTIV",
        "type": "transaction",
        "inactive": 0,
        "frozen": 0,
        "secret": ""
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

