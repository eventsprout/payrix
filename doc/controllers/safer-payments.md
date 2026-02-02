# Safer Payments

```php
$saferPaymentsController = $client->getSaferPaymentsController();
```

## Class Name

`SaferPaymentsController`

## Methods

* [Get Safer Payments Id](../../doc/controllers/safer-payments.md#get-safer-payments-id)
* [Put Safer Payments Id](../../doc/controllers/safer-payments.md#put-safer-payments-id)
* [Get Safer Payments](../../doc/controllers/safer-payments.md#get-safer-payments)
* [Post Safer Payments](../../doc/controllers/safer-payments.md#post-safer-payments)


# Get Safer Payments Id

Query Safer Payment.

```php
function getSaferPaymentsId(
    string $id,
    ?string $token = null,
    ?string $embed = null
): SaferPaymentsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource, or the (unknown) ID associated with the Safer Payments. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`SaferPaymentsResponseResult`](../../doc/models/safer-payments-response-result.md)

## Example Usage

```php
$id = 't1_saf_67f4d59664ed122a5915300';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$result = $saferPaymentsController->getSaferPaymentsId(
    $id,
    $token
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_vas_65de13bb68f138dc751dc0z",
        "created": "2024-02-27 11:54:19.4389",
        "modified": "2024-02-27 11:54:19.4389",
        "creator": "t1_log_633455983e5e7fe16fb078b",
        "modifier": "t1_log_633455983e5e7fe16fb078b",
        "entity": "t1_ent_65de12aabb1f58e2a3441f7",
        "status": "compliance",
        "enablementDate": "2024-02-27 11:54:19",
        "pciNonValidationFeeEnabled": 0,
        "org": "t1_org_00b2ac11ed8bed97fb80000",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414978z5",
        "program": "basic",
        "deleted": "2024-02-27 11:54:19",
        "deleter": "",
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


# Put Safer Payments Id

Update Safer Payment.

```php
function putSaferPaymentsId(
    string $id,
    SaferPaymentsPutRequest $body,
    ?string $token = null
): SaferPaymentsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource, or the (unknown) ID associated with the Safer Payment. |
| `body` | [`SaferPaymentsPutRequest`](../../doc/models/safer-payments-put-request.md) | Body, Required | Update Safer Payment Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |

## Response Type

[`SaferPaymentsResponseResult`](../../doc/models/safer-payments-response-result.md)

## Example Usage

```php
$id = 't1_saf_67f4d59664ed122a5915300';

$body = SaferPaymentsPutRequestBuilder::init()
    ->entity('t1_ent_65de12aabb1f58e2a3441f7')
    ->status(SaferPaymentStatusEnum::COMPLIANCE)
    ->enablementDate('2024-02-27 11:54:19')
    ->pciNonValidationFeeEnabled(SaferPaymentPciNonValidationFeeEnabledEnum::ENUM_0)
    ->org('t1_org_00b2ac11ed8bed97fb80000')
    ->division('t1_div_67c56806728fbbf0bae0b00')
    ->partition('t1_ptn_666834d4d504f21414978z5')
    ->program(SaferPaymentProgramEnum::BASIC)
    ->deleted('2024-02-27 11:54:19')
    ->deleter('')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$result = $saferPaymentsController->putSaferPaymentsId(
    $id,
    $body,
    $token
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_vas_65de13bb68f138dc751dc0z",
        "created": "2024-02-27 11:54:19.4389",
        "modified": "2024-02-27 11:54:19.4389",
        "creator": "t1_log_633455983e5e7fe16fb078b",
        "modifier": "t1_log_633455983e5e7fe16fb078b",
        "entity": "t1_ent_65de12aabb1f58e2a3441f7",
        "status": "compliance",
        "enablementDate": "2024-02-27 11:54:19",
        "pciNonValidationFeeEnabled": 0,
        "org": "t1_org_00b2ac11ed8bed97fb80000",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414978z5",
        "program": "basic",
        "deleted": "2024-02-27 11:54:19",
        "deleter": "",
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


# Get Safer Payments

Query Safer Payments.

```php
function getSaferPayments(
    ?string $token = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): SaferPaymentsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `search` | `?string` | Header, Optional | Set this header to filter or sort the list of resources that the method returns.<br>See [Searches](page:welcome#searches) for detailed information and examples on how to use search header. |
| `totals` | `?string` | Header, Optional | To configure a request to return a total for all instances of a field in a result set,  use the totals header in the format `totals={operator}[]={key}`.  This will calculate the desired total and return it in the `details > totals` object of the response.  For instance, if you want to sum the `total` field of all transactions,  you would use the `sum` operator. The response will include the result set,  along with the calculated total in the `details` section. See [Collection Operators](page:welcome#collection-operators) for detailed information and examples on how to use totals header. |
| `pageNumber` | `?int` | Query, Optional | Set this path parameter to request a specific page of records.<br>For example, set `?page[number]=2` to retrieve the second page of records for this request. |
| `pageLimit` | `?int` | Query, Optional | Set this path parameter to request up to a specific amount of records. By default 30 records are retrieved per page. The maximum limit that can be set is 100.<br>For example, set `?page[limit]=50` to retrieve up to 50 records for this request. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`SaferPaymentsResponseResult`](../../doc/models/safer-payments-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $saferPaymentsController->getSaferPayments(
    $token,
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
        "id": "t1_vas_65de13bb68f138dc751dc0z",
        "created": "2024-02-27 11:54:19.4389",
        "modified": "2024-02-27 11:54:19.4389",
        "creator": "t1_log_633455983e5e7fe16fb078b",
        "modifier": "t1_log_633455983e5e7fe16fb078b",
        "entity": "t1_ent_65de12aabb1f58e2a3441f7",
        "status": "compliance",
        "enablementDate": "2024-02-27 11:54:19",
        "pciNonValidationFeeEnabled": 0,
        "org": "t1_org_00b2ac11ed8bed97fb80000",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414978z5",
        "program": "basic",
        "deleted": "2024-02-27 11:54:19",
        "deleter": "",
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


# Post Safer Payments

Create a Safer Payment.

```php
function postSaferPayments(SaferPaymentsPostRequest $body): SaferPaymentsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SaferPaymentsPostRequest`](../../doc/models/safer-payments-post-request.md) | Body, Required | Create Safer Payment Request |

## Response Type

[`SaferPaymentsResponseResult`](../../doc/models/safer-payments-response-result.md)

## Example Usage

```php
$body = SaferPaymentsPostRequestBuilder::init()
    ->entity('t1_ent_65de12aabb1f58e2a3441f7')
    ->status(SaferPaymentStatusEnum::COMPLIANCE)
    ->enablementDate('2024-02-27 11:54:19')
    ->pciNonValidationFeeEnabled(SaferPaymentPciNonValidationFeeEnabledEnum::ENUM_0)
    ->org('t1_org_00b2ac11ed8bed97fb80000')
    ->division('t1_div_67c56806728fbbf0bae0b00')
    ->partition('t1_ptn_666834d4d504f21414978z5')
    ->program(SaferPaymentProgramEnum::BASIC)
    ->deleted('2024-02-27 11:54:19')
    ->deleter('')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$result = $saferPaymentsController->postSaferPayments($body);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_vas_65de13bb68f138dc751dc0z",
        "created": "2024-02-27 11:54:19.4389",
        "modified": "2024-02-27 11:54:19.4389",
        "creator": "t1_log_633455983e5e7fe16fb078b",
        "modifier": "t1_log_633455983e5e7fe16fb078b",
        "entity": "t1_ent_65de12aabb1f58e2a3441f7",
        "status": "compliance",
        "enablementDate": "2024-02-27 11:54:19",
        "pciNonValidationFeeEnabled": 0,
        "org": "t1_org_00b2ac11ed8bed97fb80000",
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414978z5",
        "program": "basic",
        "deleted": "2024-02-27 11:54:19",
        "deleter": "",
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

