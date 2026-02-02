# Invoice Results

```php
$invoiceResultsController = $client->getInvoiceResultsController();
```

## Class Name

`InvoiceResultsController`

## Methods

* [Get Invoice Results Id](../../doc/controllers/invoice-results.md#get-invoice-results-id)
* [Get Invoice Results](../../doc/controllers/invoice-results.md#get-invoice-results)
* [Post Invoice Results](../../doc/controllers/invoice-results.md#post-invoice-results)


# Get Invoice Results Id

Query an invoiceResults resource that represents the result of an invoice processing, which is generated when a customer pays for an invoice.

```php
function getInvoiceResultsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): InvoiceResultsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this invoice result. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`InvoiceResultsResponseResult`](../../doc/models/invoice-results-response-result.md)

## Example Usage

```php
$id = 't1_inr_00a18bcde1a1b2ec3d9c9az';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $invoiceResultsController->getInvoiceResultsId(
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
        "id": "t1_inr_00a18bcde1a1b2ec3d9c9az",
        "created": "2025-01-31 08:42:16.7318",
        "modified": "2025-01-31 08:42:16.7318",
        "creator": "t1_log_0092b50e8812b18e41d511s",
        "modifier": "t1_log_0092b50e8812b18e41d511s",
        "invoice": "t1_inv_67b7c41d9d166b99ac02b36",
        "txn": "p1_txn_00b7c41d9d166b99ac01b10",
        "status": "success",
        "message": "Invoice Paid",
        "shippingFirst": "John",
        "shippingMiddle": "M",
        "shippingLast": "Doe",
        "shippingCompany": "Doe Shipping Co.",
        "shippingAddress1": "123 Main st.",
        "shippingAddress2": "Suite 100",
        "shippingCity": "Springfield",
        "shippingState": "TX",
        "shippingZip": "62701",
        "shippingCountry": "USA",
        "shippingPhone": "+11234567845",
        "shippingFax": "+11234567845",
        "authorization": "Test Authorization with a field name = :field: and a replace text = :replace:",
        "authorizationData": "{\"field\":\"field\",\"replace\":\"replace\"}",
        "signature": "/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAYEBQYFBAYGBQYHB7A1mFUdV1dy+LOL9C6HE7XK5uPW945ne06NVJ+dt4HsRr9u33igKE411GteR5/fsVtkFVJNZmAz1gaDAX7AdGDvYcCSORyWv"
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


# Get Invoice Results

Query InvoiceResults resource that represents the result of an invoice processing. In other words, when the customer pays for an invoice it will then generate an invoice result.

```php
function getInvoiceResults(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): InvoiceResultsResponseResult
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

[`InvoiceResultsResponseResult`](../../doc/models/invoice-results-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $invoiceResultsController->getInvoiceResults(
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
        "id": "t1_inr_00a18bcde1a1b2ec3d9c9az",
        "created": "2025-01-31 08:42:16.7318",
        "modified": "2025-01-31 08:42:16.7318",
        "creator": "t1_log_0092b50e8812b18e41d511s",
        "modifier": "t1_log_0092b50e8812b18e41d511s",
        "invoice": "t1_inv_67b7c41d9d166b99ac02b36",
        "txn": "p1_txn_00b7c41d9d166b99ac01b10",
        "status": "success",
        "message": "Invoice Paid",
        "shippingFirst": "John",
        "shippingMiddle": "M",
        "shippingLast": "Doe",
        "shippingCompany": "Doe Shipping Co.",
        "shippingAddress1": "123 Main st.",
        "shippingAddress2": "Suite 100",
        "shippingCity": "Springfield",
        "shippingState": "TX",
        "shippingZip": "62701",
        "shippingCountry": "USA",
        "shippingPhone": "+11234567845",
        "shippingFax": "+11234567845",
        "authorization": "Test Authorization with a field name = :field: and a replace text = :replace:",
        "authorizationData": "{\"field\":\"field\",\"replace\":\"replace\"}",
        "signature": "/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAYEBQYFBAYGBQYHB7A1mFUdV1dy+LOL9C6HE7XK5uPW945ne06NVJ+dt4HsRr9u33igKE411GteR5/fsVtkFVJNZmAz1gaDAX7AdGDvYcCSORyWv"
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


# Post Invoice Results

create a invoiceResult.

```php
function postInvoiceResults(
    InvoiceResultPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): InvoiceResultsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`InvoiceResultPostRequest`](../../doc/models/invoice-result-post-request.md) | Body, Required | Create Invoice Result Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`InvoiceResultsResponseResult`](../../doc/models/invoice-results-response-result.md)

## Example Usage

```php
$body = InvoiceResultPostRequestBuilder::init(
    't1_inv_00b62cb82db90057aae4157'
)
    ->txn('p1_txn_67b7c41d9d166b99ac02b36')
    ->status(InvoiceResultStatusEnum::SUCCESS)
    ->message('Invoice Paid')
    ->shippingFirst('John')
    ->shippingMiddle('M')
    ->shippingLast('Doe')
    ->shippingCompany('Doe Shippin Co.')
    ->shippingAddress1('123 Mai st.')
    ->shippingAddress2('Suite 10')
    ->shippingCity('Springfield')
    ->shippingState('TX')
    ->shippingZip('62701')
    ->shippingCountry(CountryEnum::USA)
    ->shippingPhone('+1123456784')
    ->shippingFax('+1123456784')
    ->authorization('Test Authorization with a field name = :field: and a replace text = :replace:')
    ->authorizationData('{"field":"field", "replace":"replace"}')
    ->signature('/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAYEBQYFBAYGBQYHBwYIChAKCgkJChQODwwQFxQYGBcUFhYaHSUfGhsjHBYWICwgIyYnKSop')
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $invoiceResultsController->postInvoiceResults(
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
        "id": "t1_inr_00a18bcde1a1b2ec3d9c9az",
        "created": "2025-01-31 08:42:16.7318",
        "modified": "2025-01-31 08:42:16.7318",
        "creator": "t1_log_0092b50e8812b18e41d511s",
        "modifier": "t1_log_0092b50e8812b18e41d511s",
        "invoice": "t1_inv_67b7c41d9d166b99ac02b36",
        "txn": "p1_txn_00b7c41d9d166b99ac01b10",
        "status": "success",
        "message": "Invoice Paid",
        "shippingFirst": "John",
        "shippingMiddle": "M",
        "shippingLast": "Doe",
        "shippingCompany": "Doe Shipping Co.",
        "shippingAddress1": "123 Main st.",
        "shippingAddress2": "Suite 100",
        "shippingCity": "Springfield",
        "shippingState": "TX",
        "shippingZip": "62701",
        "shippingCountry": "USA",
        "shippingPhone": "+11234567845",
        "shippingFax": "+11234567845",
        "authorization": "Test Authorization with a field name = :field: and a replace text = :replace:",
        "authorizationData": "{\"field\":\"field\",\"replace\":\"replace\"}",
        "signature": "/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAYEBQYFBAYGBQYHB7A1mFUdV1dy+LOL9C6HE7XK5uPW945ne06NVJ+dt4HsRr9u33igKE411GteR5/fsVtkFVJNZmAz1gaDAX7AdGDvYcCSORyWv"
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

