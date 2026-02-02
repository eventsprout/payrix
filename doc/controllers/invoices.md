# Invoices

Invoices deals with  customer invoice details allowing for presenting charges to a customer and for payments to be made related to certain products or services.

```php
$invoicesController = $client->getInvoicesController();
```

## Class Name

`InvoicesController`

## Methods

* [Get Invoices Id](../../doc/controllers/invoices.md#get-invoices-id)
* [Put Invoices Id](../../doc/controllers/invoices.md#put-invoices-id)
* [Delete Invoices Id](../../doc/controllers/invoices.md#delete-invoices-id)
* [Get Invoices](../../doc/controllers/invoices.md#get-invoices)
* [Post Invoices](../../doc/controllers/invoices.md#post-invoices)


# Get Invoices Id

Query an Invoice or use it for invoicing customers, email the invoice to them, allow them to pay the invoice and track payments with invoices.

```php
function getInvoicesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): InvoicesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this entity. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`InvoicesResponseResult`](../../doc/models/invoices-response-result.md)

## Example Usage

```php
$id = 't1_inv_00b3a1f7e418cd6e378d410';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $invoicesController->getInvoicesId(
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
        "id": "t1_act_67a18bcde1a1b2ec3d9c9az",
        "created": "2025-01-31 08:42:16.7318",
        "modified": "2025-01-31 08:42:16.7318",
        "creator": "t1_log_0092b50e8812b18e41d511s",
        "modifier": "t1_log_0092b50e8812b18e41d511s",
        "login": "t1_log_0092b50e1112b18e41d521e",
        "merchant": "t1_mer_008e7f511d5c5a2d2fade82",
        "customer": "t1_cus_00b39e97b2110ba9075dfda",
        "subscription": "t1_sbn_00fc6fxx7a871bbce685897",
        "number": "10",
        "title": "Test Invoice Alert",
        "message": "Testing the invoice alerts",
        "emails": "erik@test.com",
        "total": 100,
        "tax": 1000,
        "discount": 1000,
        "type": "single",
        "status": "paid",
        "dueDate": 20250217,
        "expirationDate": 20250217,
        "sendOn": 20250217,
        "emailStatus": "pending",
        "inactive": 0,
        "frozen": 0,
        "allowedPaymentMethods": "visa"
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


# Put Invoices Id

Update an Invoice. An Invoice resource is used for invoicing customers, email the invoice to them, allow them to pay the invoice and track payments with invoices.

```php
function putInvoicesId(
    string $id,
    InvoicesPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): InvoicesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this invoice. |
| `body` | [`InvoicesPutRequest`](../../doc/models/invoices-put-request.md) | Body, Required | Update Invoice Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`InvoicesResponseResult`](../../doc/models/invoices-response-result.md)

## Example Usage

```php
$id = 't1_inv_00b3a1f7e418cd6e378d410';

$body = InvoicesPutRequestBuilder::init()
    ->login('t1_log_0092b50e1112b18e41d521e')
    ->merchant('t1_mer_008e7f511d5c5a2d2fade82')
    ->customer('t1_cus_00b39e97b2110ba9075dfda')
    ->subscription('t1_sbn_00fc6fxx7a871bbce685897')
    ->allowedPaymentMethods('visa')
    ->title('Test Invoice Alert')
    ->message('Testing the invoice alerts')
    ->total(100)
    ->tax(1000)
    ->discount(1000)
    ->dueDate(20250217)
    ->expirationDate(20250217)
    ->sendOn(20250217)
    ->status(InvoiceStatusEnum::PAID)
    ->emailStatus(InvoicesEmailStatusEnum::PENDING)
    ->emails('erik@test.com')
    ->type(InvoiceTypeEnum::ONEOFF)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $invoicesController->putInvoicesId(
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
        "id": "t1_act_67a18bcde1a1b2ec3d9c9az",
        "created": "2025-01-31 08:42:16.7318",
        "modified": "2025-01-31 08:42:16.7318",
        "creator": "t1_log_0092b50e8812b18e41d511s",
        "modifier": "t1_log_0092b50e8812b18e41d511s",
        "login": "t1_log_0092b50e1112b18e41d521e",
        "merchant": "t1_mer_008e7f511d5c5a2d2fade82",
        "customer": "t1_cus_00b39e97b2110ba9075dfda",
        "subscription": "t1_sbn_00fc6fxx7a871bbce685897",
        "number": "10",
        "title": "Test Invoice Alert",
        "message": "Testing the invoice alerts",
        "emails": "erik@test.com",
        "total": 100,
        "tax": 1000,
        "discount": 1000,
        "type": "single",
        "status": "paid",
        "dueDate": 20250217,
        "expirationDate": 20250217,
        "sendOn": 20250217,
        "emailStatus": "pending",
        "inactive": 0,
        "frozen": 0,
        "allowedPaymentMethods": "visa"
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


# Delete Invoices Id

Delete an Invoice or use it for invoicing customers, email the invoice to them, allow them to pay the invoice and track payments with invoices.

```php
function deleteInvoicesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): InvoicesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this invoice. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`InvoicesResponseResult`](../../doc/models/invoices-response-result.md)

## Example Usage

```php
$id = 't1_inv_00b3a1f7e418cd6e378d410';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $invoicesController->deleteInvoicesId(
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
        "id": "t1_act_67a18bcde1a1b2ec3d9c9az",
        "created": "2025-01-31 08:42:16.7318",
        "modified": "2025-01-31 08:42:16.7318",
        "creator": "t1_log_0092b50e8812b18e41d511s",
        "modifier": "t1_log_0092b50e8812b18e41d511s",
        "login": "t1_log_0092b50e1112b18e41d521e",
        "merchant": "t1_mer_008e7f511d5c5a2d2fade82",
        "customer": "t1_cus_00b39e97b2110ba9075dfda",
        "subscription": "t1_sbn_00fc6fxx7a871bbce685897",
        "number": "10",
        "title": "Test Invoice Alert",
        "message": "Testing the invoice alerts",
        "emails": "erik@test.com",
        "total": 100,
        "tax": 1000,
        "discount": 1000,
        "type": "single",
        "status": "paid",
        "dueDate": 20250217,
        "expirationDate": 20250217,
        "sendOn": 20250217,
        "emailStatus": "pending",
        "inactive": 0,
        "frozen": 0,
        "allowedPaymentMethods": "visa"
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


# Get Invoices

Query an Invoice or query an Invoice. An Invoice resource is used for invoicing customers, email the invoice to them, allow them to pay the invoice and track payments with invoices.

```php
function getInvoices(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): InvoicesResponseResult
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

[`InvoicesResponseResult`](../../doc/models/invoices-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $invoicesController->getInvoices(
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
        "id": "t1_act_67a18bcde1a1b2ec3d9c9az",
        "created": "2025-01-31 08:42:16.7318",
        "modified": "2025-01-31 08:42:16.7318",
        "creator": "t1_log_0092b50e8812b18e41d511s",
        "modifier": "t1_log_0092b50e8812b18e41d511s",
        "login": "t1_log_0092b50e1112b18e41d521e",
        "merchant": "t1_mer_008e7f511d5c5a2d2fade82",
        "customer": "t1_cus_00b39e97b2110ba9075dfda",
        "subscription": "t1_sbn_00fc6fxx7a871bbce685897",
        "number": "10",
        "title": "Test Invoice Alert",
        "message": "Testing the invoice alerts",
        "emails": "erik@test.com",
        "total": 100,
        "tax": 1000,
        "discount": 1000,
        "type": "single",
        "status": "paid",
        "dueDate": 20250217,
        "expirationDate": 20250217,
        "sendOn": 20250217,
        "emailStatus": "pending",
        "inactive": 0,
        "frozen": 0,
        "allowedPaymentMethods": "visa"
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


# Post Invoices

Create an Invoice, which is used for invoicing customers, emailing the invoice to them, allowing them to pay the invoice and tracking payments with invoices.

```php
function postInvoices(
    InvoicesPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): InvoicesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`InvoicesPostRequest`](../../doc/models/invoices-post-request.md) | Body, Required | Create Invoice Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`InvoicesResponseResult`](../../doc/models/invoices-response-result.md)

## Example Usage

```php
$body = InvoicesPostRequestBuilder::init(
    't1_log_0092b50e1112b18e41d521e',
    '9999888888',
    InvoiceStatusEnum::PAID
)
    ->merchant('t1_mer_008e7f511d5c5a2d2fade82')
    ->customer(
        't1_cus_00b39e97b2110ba9075dfda'
    )
    ->subscription('t1_sbn_00fc6fxx7a871bbce685897')
    ->allowedPaymentMethods('visa')
    ->title('Test Invoice Alert')
    ->message('Testing invoice alerts')
    ->total(100)
    ->tax(1000)
    ->discount(1000)
    ->dueDate(20250217)
    ->expirationDate(20250217)
    ->sendOn(20250217)
    ->emailStatus(InvoicesEmailStatusEnum::PENDING)
    ->emails('erik@test.com')
    ->type(InvoiceTypeEnum::ONEOFF)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->inactive(InactiveEnum::ACTIVE)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $invoicesController->postInvoices(
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
        "id": "t1_act_67a18bcde1a1b2ec3d9c9az",
        "created": "2025-01-31 08:42:16.7318",
        "modified": "2025-01-31 08:42:16.7318",
        "creator": "t1_log_0092b50e8812b18e41d511s",
        "modifier": "t1_log_0092b50e8812b18e41d511s",
        "login": "t1_log_0092b50e1112b18e41d521e",
        "merchant": "t1_mer_008e7f511d5c5a2d2fade82",
        "customer": "t1_cus_00b39e97b2110ba9075dfda",
        "subscription": "t1_sbn_00fc6fxx7a871bbce685897",
        "number": "10",
        "title": "Test Invoice Alert",
        "message": "Testing the invoice alerts",
        "emails": "erik@test.com",
        "total": 100,
        "tax": 1000,
        "discount": 1000,
        "type": "single",
        "status": "paid",
        "dueDate": 20250217,
        "expirationDate": 20250217,
        "sendOn": 20250217,
        "emailStatus": "pending",
        "inactive": 0,
        "frozen": 0,
        "allowedPaymentMethods": "visa"
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

