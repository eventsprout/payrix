# Customers

Customers deals with merchant customer information. Customers may be associated with tokens to create a stored method of payment or with invoices for billing.

```php
$customersController = $client->getCustomersController();
```

## Class Name

`CustomersController`

## Methods

* [Get Customers Id](../../doc/controllers/customers.md#get-customers-id)
* [Put Customers Id](../../doc/controllers/customers.md#put-customers-id)
* [Delete Customers Id](../../doc/controllers/customers.md#delete-customers-id)
* [Get Customers](../../doc/controllers/customers.md#get-customers)
* [Post Customers](../../doc/controllers/customers.md#post-customers)


# Get Customers Id

Query a Customer, which is a record that stores data about a particular customer of a Merchant and can be used to associate payment data or with other API features.

```php
function getCustomersId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): CustomersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this customer. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`CustomersResponseResult`](../../doc/models/customers-response-result.md)

## Example Usage

```php
$id = 't1_cus_67a527f32862c3e51bcce51';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $customersController->getCustomersId(
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
        "id": "t1_cus_67a527f32862c3e51bcce51",
        "created": "2025-02-06 16:21:55.1821",
        "modified": "2025-02-06 16:21:55.1821",
        "creator": "t1_log_62fd0aa37c3d8ec3a9dcea8",
        "modifier": "t1_log_62fd0aa37c3d8ec3a9dcea8",
        "login": "t1_log_6789616d2294ec86ba6076c",
        "merchant": "t1_mer_64415e924c58c616f8a119b",
        "first": "John",
        "middle": "M",
        "last": "Doe",
        "company": "Doe Enterprises",
        "email": "somename@emaol.com",
        "fax": "+11234567845",
        "phone": "+11324567845",
        "country": "USA",
        "zip": "75001",
        "state": "TX",
        "city": "Shelbyville",
        "address2": "Apt 4B",
        "address1": "456 Secondary Ave",
        "inactive": 0,
        "frozen": 0,
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
        "custom": "Customer's custom data",
        "authTokenCustomer": "912ae8b2f7e868eb6abb8b1a23b967ff",
        "entity": "t1_ent_64415e922e9000ef8bf3c1d"
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


# Put Customers Id

Update a Customer. A Customer is a record that is used to store data about a particular customer of a Merchant, which you can use to associate payment data or for use with other API features.

```php
function putCustomersId(
    string $id,
    CustomersPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): CustomersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this customer. |
| `body` | [`CustomersPutRequest`](../../doc/models/customers-put-request.md) | Body, Required | Update Customer Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`CustomersResponseResult`](../../doc/models/customers-response-result.md)

## Example Usage

```php
$id = 't1_cus_67a527f32862c3e51bcce51';

$body = CustomersPutRequestBuilder::init()
    ->login('t1_log_0089616d2294ec86ba6076c')
    ->merchant('t1_mer_00415e924c58c616f8a119b')
    ->entity('t1_ent_64415e922e9000ef8bf3c1d')
    ->first('John')
    ->middle('M')
    ->last('Doe')
    ->company('Doe Enterprises')
    ->email('somename@emaol.com')
    ->shippingFirst('John')
    ->shippingMiddle('M')
    ->shippingLast('Doe')
    ->shippingCompany('Doe Shipping Co.')
    ->shippingAddress1('123 Main st.')
    ->shippingAddress2('Apt 4B')
    ->shippingCity('Shelbyville')
    ->shippingState('TX')
    ->shippingZip('75001')
    ->shippingCountry(CountryEnum::USA)
    ->shippingPhone('+11234567845')
    ->shippingFax('+11234567845')
    ->custom('Customer\'s custom data')
    ->address1('456 Secondary Ave')
    ->address2('Apt 4B')
    ->city('Shelbyville')
    ->state('TX')
    ->zip('75001')
    ->country(CountryEnum::USA)
    ->phone('+11324567845')
    ->fax('+11234567845')
    ->frozen(FrozenEnum::NOTFROZEN)
    ->inactive(InactiveEnum::ACTIVE)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $customersController->putCustomersId(
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
        "id": "t1_cus_67a527f32862c3e51bcce51",
        "created": "2025-02-06 16:21:55.1821",
        "modified": "2025-02-06 16:21:55.1821",
        "creator": "t1_log_62fd0aa37c3d8ec3a9dcea8",
        "modifier": "t1_log_62fd0aa37c3d8ec3a9dcea8",
        "login": "t1_log_6789616d2294ec86ba6076c",
        "merchant": "t1_mer_64415e924c58c616f8a119b",
        "first": "John",
        "middle": "M",
        "last": "Doe",
        "company": "Doe Enterprises",
        "email": "somename@emaol.com",
        "fax": "+11234567845",
        "phone": "+11324567845",
        "country": "USA",
        "zip": "75001",
        "state": "TX",
        "city": "Shelbyville",
        "address2": "Apt 4B",
        "address1": "456 Secondary Ave",
        "inactive": 0,
        "frozen": 0,
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
        "custom": "Customer's custom data",
        "authTokenCustomer": "912ae8b2f7e868eb6abb8b1a23b967ff",
        "entity": "t1_ent_64415e922e9000ef8bf3c1d"
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


# Delete Customers Id

Delete a Customer. A Customer is a record that is used to store data about a particular customer of a Merchant. You can use it to associate payment data to the Customer, or for use with other API features.

```php
function deleteCustomersId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): CustomersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this customer. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`CustomersResponseResult`](../../doc/models/customers-response-result.md)

## Example Usage

```php
$id = 't1_cus_67a527f32862c3e51bcce51';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $customersController->deleteCustomersId(
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
        "id": "t1_cus_67a527f32862c3e51bcce51",
        "created": "2025-02-06 16:21:55.1821",
        "modified": "2025-02-06 16:21:55.1821",
        "creator": "t1_log_62fd0aa37c3d8ec3a9dcea8",
        "modifier": "t1_log_62fd0aa37c3d8ec3a9dcea8",
        "login": "t1_log_6789616d2294ec86ba6076c",
        "merchant": "t1_mer_64415e924c58c616f8a119b",
        "first": "John",
        "middle": "M",
        "last": "Doe",
        "company": "Doe Enterprises",
        "email": "somename@emaol.com",
        "fax": "+11234567845",
        "phone": "+11324567845",
        "country": "USA",
        "zip": "75001",
        "state": "TX",
        "city": "Shelbyville",
        "address2": "Apt 4B",
        "address1": "456 Secondary Ave",
        "inactive": 0,
        "frozen": 0,
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
        "custom": "Customer's custom data",
        "authTokenCustomer": "912ae8b2f7e868eb6abb8b1a23b967ff",
        "entity": "t1_ent_64415e922e9000ef8bf3c1d"
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


# Get Customers

Query customers. Each Customer record stores data about a particular customer of a Merchant and can be used to associate payment data to the Customer and for other API features.

```php
function getCustomers(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): CustomersResponseResult
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

[`CustomersResponseResult`](../../doc/models/customers-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $customersController->getCustomers(
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
        "id": "t1_cus_67a527f32862c3e51bcce51",
        "created": "2025-02-06 16:21:55.1821",
        "modified": "2025-02-06 16:21:55.1821",
        "creator": "t1_log_62fd0aa37c3d8ec3a9dcea8",
        "modifier": "t1_log_62fd0aa37c3d8ec3a9dcea8",
        "login": "t1_log_6789616d2294ec86ba6076c",
        "merchant": "t1_mer_64415e924c58c616f8a119b",
        "first": "John",
        "middle": "M",
        "last": "Doe",
        "company": "Doe Enterprises",
        "email": "somename@emaol.com",
        "fax": "+11234567845",
        "phone": "+11324567845",
        "country": "USA",
        "zip": "75001",
        "state": "TX",
        "city": "Shelbyville",
        "address2": "Apt 4B",
        "address1": "456 Secondary Ave",
        "inactive": 0,
        "frozen": 0,
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
        "custom": "Customer's custom data",
        "authTokenCustomer": "912ae8b2f7e868eb6abb8b1a23b967ff",
        "entity": "t1_ent_64415e922e9000ef8bf3c1d"
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


# Post Customers

Create a Customer record to store data about a particular customer of a Merchant, and to associate payment data to the Customer and for other API features.

```php
function postCustomers(
    CustomersPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): CustomersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CustomersPostRequest`](../../doc/models/customers-post-request.md) | Body, Required | Create Customer Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`CustomersResponseResult`](../../doc/models/customers-response-result.md)

## Example Usage

```php
$body = CustomersPostRequestBuilder::init(
    't1_log_0089616d2294ec86ba6076c'
)
    ->merchant('t1_mer_00415e924c58c616f8a119b')
    ->entity('t1_ent_64415e922e9000ef8bf3c1d')
    ->first('John')
    ->middle('M')
    ->last('Doe')
    ->company('Doe Enterprises')
    ->email('somename@emaol.com')
    ->shippingFirst('John')
    ->shippingMiddle('M')
    ->shippingLast('Doe')
    ->shippingCompany('Doe Shipping Co.')
    ->shippingAddress1('123 Main st.')
    ->shippingAddress2('Apt 4B')
    ->shippingCity('Shelbyville')
    ->shippingState('TX')
    ->shippingZip('75001')
    ->shippingCountry(CountryEnum::USA)
    ->shippingPhone('+11234567845')
    ->shippingFax('+11234567845')
    ->custom('Customer\'s custom data')
    ->address1('456 Secondary Ave')
    ->address2('Apt 4B')
    ->city('Shelbyville')
    ->state('TX')
    ->zip('75001')
    ->country(CountryEnum::USA)
    ->phone('+11324567845')
    ->fax('+11234567845')
    ->frozen(FrozenEnum::NOTFROZEN)
    ->inactive(InactiveEnum::ACTIVE)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $customersController->postCustomers(
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
        "id": "t1_cus_67a527f32862c3e51bcce51",
        "created": "2025-02-06 16:21:55.1821",
        "modified": "2025-02-06 16:21:55.1821",
        "creator": "t1_log_62fd0aa37c3d8ec3a9dcea8",
        "modifier": "t1_log_62fd0aa37c3d8ec3a9dcea8",
        "login": "t1_log_6789616d2294ec86ba6076c",
        "merchant": "t1_mer_64415e924c58c616f8a119b",
        "first": "John",
        "middle": "M",
        "last": "Doe",
        "company": "Doe Enterprises",
        "email": "somename@emaol.com",
        "fax": "+11234567845",
        "phone": "+11324567845",
        "country": "USA",
        "zip": "75001",
        "state": "TX",
        "city": "Shelbyville",
        "address2": "Apt 4B",
        "address1": "456 Secondary Ave",
        "inactive": 0,
        "frozen": 0,
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
        "custom": "Customer's custom data",
        "authTokenCustomer": "912ae8b2f7e868eb6abb8b1a23b967ff",
        "entity": "t1_ent_64415e922e9000ef8bf3c1d"
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

