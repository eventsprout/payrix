# Entities Custom Fields

the Entity Custom Fields feature, designed to empower partners to send identifiers and Risk-requested items using unlimited custom fields.  By leveraging this feature, partners can ensure that their software works seamlessly, leading to increased Boarding Rates. Additionally,  partners can avoid waiting for Risk to request information manually, streamlining their operations.

```php
$entitiesCustomFieldsController = $client->getEntitiesCustomFieldsController();
```

## Class Name

`EntitiesCustomFieldsController`

## Methods

* [Get Entity Custom Fields Id](../../doc/controllers/entities-custom-fields.md#get-entity-custom-fields-id)
* [Put Entity Custom Fields Id](../../doc/controllers/entities-custom-fields.md#put-entity-custom-fields-id)
* [Delete Entity Custom Fields Id](../../doc/controllers/entities-custom-fields.md#delete-entity-custom-fields-id)
* [Get Entity Custom Fields](../../doc/controllers/entities-custom-fields.md#get-entity-custom-fields)
* [Post Entity Custom Fields](../../doc/controllers/entities-custom-fields.md#post-entity-custom-fields)


# Get Entity Custom Fields Id

Query an Entity Custom Field.
Custom Fields can be added to entities associated by the Entity Id.
An Entity Id can have various fields associated to it.

```php
function getEntityCustomFieldsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): EntityCustomFieldsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`EntityCustomFieldsResponseResult`](../../doc/models/entity-custom-fields-response-result.md)

## Example Usage

```php
$id = 't1_ecf_67d3ab7bc5e308c4815100z';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $entitiesCustomFieldsController->getEntityCustomFieldsId(
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
        "id": "t1_ecf_67d3ab7bc5e308c4815100z",
        "created": "2025-03-14 00:07:23.8236",
        "modified": "2025-03-14 00:07:23.8236",
        "creator": "t1_log_67327b89589de7a6d89a665",
        "modifier": "t1_log_67327b89589de7a6d89a665",
        "entity": "t1_ent_67d3ab7bc0ef1d4284d4578",
        "key": "companyId",
        "value": "70bbd35e-8500-f011-90cb-6045bdc7c168",
        "deleted": "2025-03-14 00:07:23"
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


# Put Entity Custom Fields Id

Update an Entity Custom Field.
Custom Fields can be added to entities associated by the Entity Id.
An Entity Id can have various fields associated to it.

```php
function putEntityCustomFieldsId(
    string $id,
    EntityCustomFieldsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): EntityCustomFieldsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `body` | [`EntityCustomFieldsPutRequest`](../../doc/models/entity-custom-fields-put-request.md) | Body, Required | - |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`EntityCustomFieldsResponseResult`](../../doc/models/entity-custom-fields-response-result.md)

## Example Usage

```php
$id = 't1_ecf_67d3ab7bc5e308c4815100z';

$body = EntityCustomFieldsPutRequestBuilder::init()
    ->key('companyId')
    ->value('70bbd35e-8500-f011-90cb-6045bdc7c168')
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $entitiesCustomFieldsController->putEntityCustomFieldsId(
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
        "id": "t1_ecf_67d3ab7bc5e308c4815100z",
        "created": "2025-03-14 00:07:23.8236",
        "modified": "2025-03-14 00:07:23.8236",
        "creator": "t1_log_67327b89589de7a6d89a665",
        "modifier": "t1_log_67327b89589de7a6d89a665",
        "entity": "t1_ent_67d3ab7bc0ef1d4284d4578",
        "key": "companyId",
        "value": "70bbd35e-8500-f011-90cb-6045bdc7c168",
        "deleted": "2025-03-14 00:07:23"
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


# Delete Entity Custom Fields Id

Delete an Entity Custom Field.

```php
function deleteEntityCustomFieldsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): EntityCustomFieldsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`EntityCustomFieldsResponseResult`](../../doc/models/entity-custom-fields-response-result.md)

## Example Usage

```php
$id = 't1_ecf_67d3ab7bc5e308c4815100z';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $entitiesCustomFieldsController->deleteEntityCustomFieldsId(
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
        "id": "t1_ecf_67d3ab7bc5e308c4815100z",
        "created": "2025-03-14 00:07:23.8236",
        "modified": "2025-03-14 00:07:23.8236",
        "creator": "t1_log_67327b89589de7a6d89a665",
        "modifier": "t1_log_67327b89589de7a6d89a665",
        "entity": "t1_ent_67d3ab7bc0ef1d4284d4578",
        "key": "companyId",
        "value": "70bbd35e-8500-f011-90cb-6045bdc7c168",
        "deleted": "2025-03-14 00:07:23"
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


# Get Entity Custom Fields

Query an Entity Custom Field.
Custom Fields can be added to entities associated by the Entity Id.
An Entity Id can have various fields associated to it.

```php
function getEntityCustomFields(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): EntityCustomFieldsResponseResult
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

[`EntityCustomFieldsResponseResult`](../../doc/models/entity-custom-fields-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $entitiesCustomFieldsController->getEntityCustomFields(
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
        "id": "t1_ecf_67d3ab7bc5e308c4815100z",
        "created": "2025-03-14 00:07:23.8236",
        "modified": "2025-03-14 00:07:23.8236",
        "creator": "t1_log_67327b89589de7a6d89a665",
        "modifier": "t1_log_67327b89589de7a6d89a665",
        "entity": "t1_ent_67d3ab7bc0ef1d4284d4578",
        "key": "companyId",
        "value": "70bbd35e-8500-f011-90cb-6045bdc7c168",
        "deleted": "2025-03-14 00:07:23"
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


# Post Entity Custom Fields

Create an Entity Custom Field. Custom Fields can be added to entities associated by the Entity Id. An Entity Id can have various fields associated to it.

```php
function postEntityCustomFields(
    EntityCustomFieldsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): EntityCustomFieldsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`EntityCustomFieldsPostRequest`](../../doc/models/entity-custom-fields-post-request.md) | Body, Required | Add Entity Cutom Field Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`EntityCustomFieldsResponseResult`](../../doc/models/entity-custom-fields-response-result.md)

## Example Usage

```php
$body = EntityCustomFieldsPostRequestBuilder::init()
    ->entity(
        't1_ent_67d3ab7bc0ef1d4284d4578'
    )
    ->key('companyId')
    ->value('70bbd35e-8500-f011-90cb-6045bdc7c168')
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $entitiesCustomFieldsController->postEntityCustomFields(
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
        "id": "t1_ecf_67d3ab7bc5e308c4815100z",
        "created": "2025-03-14 00:07:23.8236",
        "modified": "2025-03-14 00:07:23.8236",
        "creator": "t1_log_67327b89589de7a6d89a665",
        "modifier": "t1_log_67327b89589de7a6d89a665",
        "entity": "t1_ent_67d3ab7bc0ef1d4284d4578",
        "key": "companyId",
        "value": "70bbd35e-8500-f011-90cb-6045bdc7c168",
        "deleted": "2025-03-14 00:07:23"
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

