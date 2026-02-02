# Mappings

Mappings enable the re-mapping of fields in the API for either in or out, using a set of JSON field mappings.  For example, if your system uses a different format for out data that it will send to the API, then you can re-map the in fields for the API using a Mapping resource.

```php
$mappingsController = $client->getMappingsController();
```

## Class Name

`MappingsController`

## Methods

* [Get Mappings Id](../../doc/controllers/mappings.md#get-mappings-id)
* [Put Mappings Id](../../doc/controllers/mappings.md#put-mappings-id)
* [Delete Mappings Id](../../doc/controllers/mappings.md#delete-mappings-id)
* [Get Mappings](../../doc/controllers/mappings.md#get-mappings)
* [Post Mappings](../../doc/controllers/mappings.md#post-mappings)


# Get Mappings Id

Query a Mapping resource.

```php
function getMappingsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): MappingsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Mapping ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`MappingsResponseResult`](../../doc/models/mappings-response-result.md)

## Example Usage

```php
$id = 't1_map_63d6a1df609e000f10b00d0';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $mappingsController->getMappingsId(
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
        "id": "t1_map_63d6a1df609e000f10b00d0",
        "created": "2023-01-29 11:42:07.3959",
        "modified": "2023-01-29 11:42:07.3959",
        "creator": "t1_log_63d25f51ea7ddb271d78304",
        "modifier": "t1_log_63d25f51ea7ddb271d78304",
        "login": "t1_log_63d25f51ea7ddb271d78304",
        "name": "Test1",
        "description": "Test1",
        "input": "{\"mappingsCreate\":{\"requests\":[{\"name\":{\"__path__\":\"mappings2Create;mappings2Request;name\"}}]}}",
        "output": "{\"mappings2CreateResponse\":{\"mappings2Responses\":[{\"name\":{\"__path__\":\"mappingsCreateResponse;requests;[];name\"}}]}}",
        "namespace": "XML namespace of input and output"
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


# Put Mappings Id

Update a Mapping. A Mapping represents a way to re-map the fields in the API for either input or output, using a set of JSON field mappings. For example, if your system uses a different format for output data that it will send to the API, then you can re-map the input fields for the API using a Mapping.

```php
function putMappingsId(
    string $id,
    MappingsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): MappingsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Mapping ID. |
| `body` | [`MappingsPutRequest`](../../doc/models/mappings-put-request.md) | Body, Required | Update Mapping Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`MappingsResponseResult`](../../doc/models/mappings-response-result.md)

## Example Usage

```php
$id = 't1_map_63d6a1df609e000f10b00d0';

$body = MappingsPutRequestBuilder::init()
    ->login('t1_log_63d25f51ea7ddb271d78304')
    ->name('Test1')
    ->description('Test1')
    ->input('{\\"mappingsCreate\\":{\\"requests\\":[{\\"name\\":{\\"__path__\\":\\"mappings2Create;mappings2Request;name\\"}}]}}')
    ->output('{\\"mappings2CreateResponse\\":{\\"mappings2Responses\\":[{\\"name\\":{\\"__path__\\":\\"mappingsCreateResponse;requests;[];name\\"}}]}}')
    ->namespace('XML namespace of input and output')
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $mappingsController->putMappingsId(
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
        "id": "t1_map_63d6a1df609e000f10b00d0",
        "created": "2023-01-29 11:42:07.3959",
        "modified": "2023-01-29 11:42:07.3959",
        "creator": "t1_log_63d25f51ea7ddb271d78304",
        "modifier": "t1_log_63d25f51ea7ddb271d78304",
        "login": "t1_log_63d25f51ea7ddb271d78304",
        "name": "Test1",
        "description": "Test1",
        "input": "{\"mappingsCreate\":{\"requests\":[{\"name\":{\"__path__\":\"mappings2Create;mappings2Request;name\"}}]}}",
        "output": "{\"mappings2CreateResponse\":{\"mappings2Responses\":[{\"name\":{\"__path__\":\"mappingsCreateResponse;requests;[];name\"}}]}}",
        "namespace": "XML namespace of input and output"
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


# Delete Mappings Id

Delete a Mapping. A Mapping represents a way to re-map the fields in the API for either input or output, using a set of JSON field mappings.

```php
function deleteMappingsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): MappingsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Mapping ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`MappingsResponseResult`](../../doc/models/mappings-response-result.md)

## Example Usage

```php
$id = 't1_map_63d6a1df609e000f10b00d0';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $mappingsController->deleteMappingsId(
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
        "id": "t1_map_63d6a1df609e000f10b00d0",
        "created": "2023-01-29 11:42:07.3959",
        "modified": "2023-01-29 11:42:07.3959",
        "creator": "t1_log_63d25f51ea7ddb271d78304",
        "modifier": "t1_log_63d25f51ea7ddb271d78304",
        "login": "t1_log_63d25f51ea7ddb271d78304",
        "name": "Test1",
        "description": "Test1",
        "input": "{\"mappingsCreate\":{\"requests\":[{\"name\":{\"__path__\":\"mappings2Create;mappings2Request;name\"}}]}}",
        "output": "{\"mappings2CreateResponse\":{\"mappings2Responses\":[{\"name\":{\"__path__\":\"mappingsCreateResponse;requests;[];name\"}}]}}",
        "namespace": "XML namespace of input and output"
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


# Get Mappings

Query a Mapping resource.
A Mapping resource represents a way to re-map the fields in the API for either input or output, using a set of JSON field mappings.
For example, if your system uses a different format for output data that it will send to the API, then you can re-map the input fields for the API using a Mapping resource.

```php
function getMappings(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): MappingsResponseResult
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

[`MappingsResponseResult`](../../doc/models/mappings-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $mappingsController->getMappings(
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
        "id": "t1_map_63d6a1df609e000f10b00d0",
        "created": "2023-01-29 11:42:07.3959",
        "modified": "2023-01-29 11:42:07.3959",
        "creator": "t1_log_63d25f51ea7ddb271d78304",
        "modifier": "t1_log_63d25f51ea7ddb271d78304",
        "login": "t1_log_63d25f51ea7ddb271d78304",
        "name": "Test1",
        "description": "Test1",
        "input": "{\"mappingsCreate\":{\"requests\":[{\"name\":{\"__path__\":\"mappings2Create;mappings2Request;name\"}}]}}",
        "output": "{\"mappings2CreateResponse\":{\"mappings2Responses\":[{\"name\":{\"__path__\":\"mappingsCreateResponse;requests;[];name\"}}]}}",
        "namespace": "XML namespace of input and output"
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


# Post Mappings

Create a Mapping resource.
A Mapping resource represents a way to re-map the fields in the API for either input or output, using a set of JSON field mappings.
For example, if your system uses a different format for output data that it will send to the API, then you can re-map the input fields for the API using a Mapping resource.

```php
function postMappings(
    MappingsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): MappingsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`MappingsPostRequest`](../../doc/models/mappings-post-request.md) | Body, Required | Create Mapping Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`MappingsResponseResult`](../../doc/models/mappings-response-result.md)

## Example Usage

```php
$body = MappingsPostRequestBuilder::init(
    't1_log_63d25f51ea7ddb271d78304'
)
    ->name('Test1')
    ->description('Test1')
    ->input('{\\"mappingsCreate\\":{\\"requests\\":[{\\"name\\":{\\"__path__\\":\\"mappings2Create;mappings2Request;name\\"}}]}}')
    ->output('{\\"mappings2CreateResponse\\":{\\"mappings2Responses\\":[{\\"name\\":{\\"__path__\\":\\"mappingsCreateResponse;requests;[];name\\"}}]}}')
    ->namespace('XML namespace of input and output')
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $mappingsController->postMappings(
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
        "id": "t1_map_63d6a1df609e000f10b00d0",
        "created": "2023-01-29 11:42:07.3959",
        "modified": "2023-01-29 11:42:07.3959",
        "creator": "t1_log_63d25f51ea7ddb271d78304",
        "modifier": "t1_log_63d25f51ea7ddb271d78304",
        "login": "t1_log_63d25f51ea7ddb271d78304",
        "name": "Test1",
        "description": "Test1",
        "input": "{\"mappingsCreate\":{\"requests\":[{\"name\":{\"__path__\":\"mappings2Create;mappings2Request;name\"}}]}}",
        "output": "{\"mappings2CreateResponse\":{\"mappings2Responses\":[{\"name\":{\"__path__\":\"mappingsCreateResponse;requests;[];name\"}}]}}",
        "namespace": "XML namespace of input and output"
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

