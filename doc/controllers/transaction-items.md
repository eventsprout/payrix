# Transaction Items

```php
$transactionItemsController = $client->getTransactionItemsController();
```

## Class Name

`TransactionItemsController`

## Methods

* [Get Items Id](../../doc/controllers/transaction-items.md#get-items-id)
* [Put Items Id](../../doc/controllers/transaction-items.md#put-items-id)
* [Delete Items Id](../../doc/controllers/transaction-items.md#delete-items-id)
* [Get Items](../../doc/controllers/transaction-items.md#get-items)
* [Post Items](../../doc/controllers/transaction-items.md#post-items)


# Get Items Id

Query an Item.
An Item is a line item that is associated with a particular Transaction. It allows you to describe the cost, quantity and other details of each line in the Transaction.

```php
function getItemsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): ItemsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`ItemsResponseResult`](../../doc/models/items-response-result.md)

## Example Usage

```php
$id = 't1_itm_67b48390abd89e15be2d000';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $transactionItemsController->getItemsId(
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
        "id": "t1_itm_67b48390abd89e15be2d000",
        "created": "2025-02-18 07:56:48.7124",
        "modified": "2025-02-18 07:56:48.7124",
        "creator": "t1_log_5f49777509d5d1d7c22e000",
        "modifier": "t1_log_5f49777509d5d1d7c22e000",
        "txn": "t1_txn_67b483904b280af5311234a",
        "item": "Line Item 21",
        "description": "A description of this Item",
        "custom": "Identifier",
        "quantity": 1,
        "price": 471,
        "inactive": 0,
        "frozen": 0,
        "um": "EACH",
        "commodityCode": "9717123",
        "total": 471,
        "discount": 0,
        "productCode": "Prorated Tenant Protection Fee"
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


# Put Items Id

Update an Item.
An Item is a line item that is associated with a particular Transaction. It allows you to describe the cost, quantity and other details of each line in the Transaction.

```php
function putItemsId(
    string $id,
    ItemsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): ItemsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `body` | [`ItemsPutRequest`](../../doc/models/items-put-request.md) | Body, Required | Update Item Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ItemsResponseResult`](../../doc/models/items-response-result.md)

## Example Usage

```php
$id = 't1_itm_67b48390abd89e15be2d000';

$body = ItemsPutRequestBuilder::init()
    ->item('Line Item 21')
    ->description('A description of Item')
    ->custom('Identifier')
    ->quantity(1)
    ->price(471)
    ->um('EACH')
    ->total(471)
    ->commodityCode('9717123')
    ->productCode('Prorated Tenant Protection Fee')
    ->discount(0)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $transactionItemsController->putItemsId(
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
        "id": "t1_itm_67b48390abd89e15be2d000",
        "created": "2025-02-18 07:56:48.7124",
        "modified": "2025-02-18 07:56:48.7124",
        "creator": "t1_log_5f49777509d5d1d7c22e000",
        "modifier": "t1_log_5f49777509d5d1d7c22e000",
        "txn": "t1_txn_67b483904b280af5311234a",
        "item": "Line Item 21",
        "description": "A description of this Item",
        "custom": "Identifier",
        "quantity": 1,
        "price": 471,
        "inactive": 0,
        "frozen": 0,
        "um": "EACH",
        "commodityCode": "9717123",
        "total": 471,
        "discount": 0,
        "productCode": "Prorated Tenant Protection Fee"
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


# Delete Items Id

Delete an Item.
An Item is a line item that is associated with a particular Transaction. It allows you to describe the cost, quantity and other details of each line in the Transaction.

```php
function deleteItemsId(string $id, ?string $token = null, ?string $requestToken = null): ItemsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ItemsResponseResult`](../../doc/models/items-response-result.md)

## Example Usage

```php
$id = 't1_itm_67b48390abd89e15be2d000';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $transactionItemsController->deleteItemsId(
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
        "id": "t1_itm_67b48390abd89e15be2d000",
        "created": "2025-02-18 07:56:48.7124",
        "modified": "2025-02-18 07:56:48.7124",
        "creator": "t1_log_5f49777509d5d1d7c22e000",
        "modifier": "t1_log_5f49777509d5d1d7c22e000",
        "txn": "t1_txn_67b483904b280af5311234a",
        "item": "Line Item 21",
        "description": "A description of this Item",
        "custom": "Identifier",
        "quantity": 1,
        "price": 471,
        "inactive": 0,
        "frozen": 0,
        "um": "EACH",
        "commodityCode": "9717123",
        "total": 471,
        "discount": 0,
        "productCode": "Prorated Tenant Protection Fee"
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


# Get Items

Query an Item.
An Item is a line item that is associated with a particular Transaction. It allows you to describe the cost, quantity and other details of each line in the Transaction.

```php
function getItems(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): ItemsResponseResult
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

[`ItemsResponseResult`](../../doc/models/items-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $transactionItemsController->getItems(
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
        "id": "t1_itm_67b48390abd89e15be2d000",
        "created": "2025-02-18 07:56:48.7124",
        "modified": "2025-02-18 07:56:48.7124",
        "creator": "t1_log_5f49777509d5d1d7c22e000",
        "modifier": "t1_log_5f49777509d5d1d7c22e000",
        "txn": "t1_txn_67b483904b280af5311234a",
        "item": "Line Item 21",
        "description": "A description of this Item",
        "custom": "Identifier",
        "quantity": 1,
        "price": 471,
        "inactive": 0,
        "frozen": 0,
        "um": "EACH",
        "commodityCode": "9717123",
        "total": 471,
        "discount": 0,
        "productCode": "Prorated Tenant Protection Fee"
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


# Post Items

Create an Item.
An Item is a line item that is associated with a particular Transaction. It allows you to describe the cost, quantity and other details of each line in the Transaction.

```php
function postItems(
    ItemsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): ItemsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`ItemsPostRequest`](../../doc/models/items-post-request.md) | Body, Required | Create an Item Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ItemsResponseResult`](../../doc/models/items-response-result.md)

## Example Usage

```php
$body = ItemsPostRequestBuilder::init(
    't1_txn_00b483904b280af5316218a',
    'Line Item 21',
    1,
    471
)
    ->description('A description of Item')
    ->custom('Identifier')
    ->um('EACH')
    ->total(471)
    ->commodityCode('9717123')
    ->productCode('Prorated Tenant Protection Fee')
    ->discount(0)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $transactionItemsController->postItems(
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
        "id": "t1_itm_67b48390abd89e15be2d000",
        "created": "2025-02-18 07:56:48.7124",
        "modified": "2025-02-18 07:56:48.7124",
        "creator": "t1_log_5f49777509d5d1d7c22e000",
        "modifier": "t1_log_5f49777509d5d1d7c22e000",
        "txn": "t1_txn_67b483904b280af5311234a",
        "item": "Line Item 21",
        "description": "A description of this Item",
        "custom": "Identifier",
        "quantity": 1,
        "price": 471,
        "inactive": 0,
        "frozen": 0,
        "um": "EACH",
        "commodityCode": "9717123",
        "total": 471,
        "discount": 0,
        "productCode": "Prorated Tenant Protection Fee"
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

