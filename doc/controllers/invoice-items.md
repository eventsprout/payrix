# Invoice Items

```php
$invoiceItemsController = $client->getInvoiceItemsController();
```

## Class Name

`InvoiceItemsController`

## Methods

* [Get Invoice Items Id](../../doc/controllers/invoice-items.md#get-invoice-items-id)
* [Put Invoice Items Id](../../doc/controllers/invoice-items.md#put-invoice-items-id)
* [Delete Invoice Items Id](../../doc/controllers/invoice-items.md#delete-invoice-items-id)
* [Get Invoice Items](../../doc/controllers/invoice-items.md#get-invoice-items)
* [Post Invoice Items](../../doc/controllers/invoice-items.md#post-invoice-items)


# Get Invoice Items Id

Query an Invoice Item or query Invoice Items.

```php
function getInvoiceItemsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): InvoiceItemsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this invoice item. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`InvoiceItemsResponseResult`](../../doc/models/invoice-items-response-result.md)

## Example Usage

```php
$id = 't1_ini_67a18bcde1a1b2ec3d9c9az';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $invoiceItemsController->getInvoiceItemsId(
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
        "id": "t1_ini_67a18bcde1a1b2ec3d9c9az",
        "created": "2025-01-31 08:42:16.7318",
        "modified": "2025-01-31 08:42:16.7318",
        "creator": "t1_log_8ad114b7edbf6f641b7c2f2",
        "modifier": "t1_log_00d114b7edbf6f641b7c2f2",
        "login": "t1_log_5ed514b7edbf6f641b7c2f2",
        "item": "Jay",
        "description": "Jay",
        "custom": "Sample custom field 1",
        "um": "kilogram",
        "commodityCode": "03000",
        "productCode": "SKU23456",
        "price": 150000,
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


# Put Invoice Items Id

Update an Invoice Item, A InvoiceItem is a resource that stores line item details for an invoice.

```php
function putInvoiceItemsId(
    string $id,
    InvoiceItemsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): InvoiceItemsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this invoice item. |
| `body` | [`InvoiceItemsPutRequest`](../../doc/models/invoice-items-put-request.md) | Body, Required | Update Invoice Item Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`InvoiceItemsResponseResult`](../../doc/models/invoice-items-response-result.md)

## Example Usage

```php
$id = 't1_ini_67a18bcde1a1b2ec3d9c9az';

$body = InvoiceItemsPutRequestBuilder::init()
    ->login('t1_log_00d514abedbf6f641b7c2f2')
    ->item('Test Custom Links')
    ->description('Test Custom Links')
    ->custom('Sample custom field 1')
    ->price(1666)
    ->um('kilogram')
    ->commodityCode('03000')
    ->productCode('SKU23456')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $invoiceItemsController->putInvoiceItemsId(
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
        "id": "t1_ini_67a18bcde1a1b2ec3d9c9az",
        "created": "2025-01-31 08:42:16.7318",
        "modified": "2025-01-31 08:42:16.7318",
        "creator": "t1_log_8ad114b7edbf6f641b7c2f2",
        "modifier": "t1_log_00d114b7edbf6f641b7c2f2",
        "login": "t1_log_5ed514b7edbf6f641b7c2f2",
        "item": "Jay",
        "description": "Jay",
        "custom": "Sample custom field 1",
        "um": "kilogram",
        "commodityCode": "03000",
        "productCode": "SKU23456",
        "price": 150000,
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


# Delete Invoice Items Id

Delete an Invoice Item or a resource that stores line item details for an invoice.

```php
function deleteInvoiceItemsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): InvoiceItemsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this invoice item. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`InvoiceItemsResponseResult`](../../doc/models/invoice-items-response-result.md)

## Example Usage

```php
$id = 't1_ini_67a18bcde1a1b2ec3d9c9az';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $invoiceItemsController->deleteInvoiceItemsId(
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
        "id": "t1_ini_67a18bcde1a1b2ec3d9c9az",
        "created": "2025-01-31 08:42:16.7318",
        "modified": "2025-01-31 08:42:16.7318",
        "creator": "t1_log_8ad114b7edbf6f641b7c2f2",
        "modifier": "t1_log_00d114b7edbf6f641b7c2f2",
        "login": "t1_log_5ed514b7edbf6f641b7c2f2",
        "item": "Jay",
        "description": "Jay",
        "custom": "Sample custom field 1",
        "um": "kilogram",
        "commodityCode": "03000",
        "productCode": "SKU23456",
        "price": 150000,
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


# Get Invoice Items

Query an Invoice Item. A Invoice Item is a resource that stores line item details for an invoice.

```php
function getInvoiceItems(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): InvoiceItemsResponseResult
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

[`InvoiceItemsResponseResult`](../../doc/models/invoice-items-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $invoiceItemsController->getInvoiceItems(
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
        "id": "t1_ini_67a18bcde1a1b2ec3d9c9az",
        "created": "2025-01-31 08:42:16.7318",
        "modified": "2025-01-31 08:42:16.7318",
        "creator": "t1_log_8ad114b7edbf6f641b7c2f2",
        "modifier": "t1_log_00d114b7edbf6f641b7c2f2",
        "login": "t1_log_5ed514b7edbf6f641b7c2f2",
        "item": "Jay",
        "description": "Jay",
        "custom": "Sample custom field 1",
        "um": "kilogram",
        "commodityCode": "03000",
        "productCode": "SKU23456",
        "price": 150000,
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


# Post Invoice Items

Create an Invoice Item, a resource that stores line item details for an invoice.

```php
function postInvoiceItems(
    InvoiceItemsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): InvoiceItemsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`InvoiceItemsPostRequest`](../../doc/models/invoice-items-post-request.md) | Body, Required | Create Invoice Item Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`InvoiceItemsResponseResult`](../../doc/models/invoice-items-response-result.md)

## Example Usage

```php
$body = InvoiceItemsPostRequestBuilder::init(
    't1_log_00d514abedbf6f641b7c2f2',
    'Test Custom Links'
)
    ->description('Test Custom Links')
    ->custom('Sample custom field 1')
    ->price(1666)
    ->um('kilogram')
    ->commodityCode('03000')
    ->productCode('SKU23456')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $invoiceItemsController->postInvoiceItems(
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
        "id": "t1_ini_67a18bcde1a1b2ec3d9c9az",
        "created": "2025-01-31 08:42:16.7318",
        "modified": "2025-01-31 08:42:16.7318",
        "creator": "t1_log_8ad114b7edbf6f641b7c2f2",
        "modifier": "t1_log_00d114b7edbf6f641b7c2f2",
        "login": "t1_log_5ed514b7edbf6f641b7c2f2",
        "item": "Jay",
        "description": "Jay",
        "custom": "Sample custom field 1",
        "um": "kilogram",
        "commodityCode": "03000",
        "productCode": "SKU23456",
        "price": 150000,
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

