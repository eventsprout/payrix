# Fee Modifiers

```php
$feeModifiersController = $client->getFeeModifiersController();
```

## Class Name

`FeeModifiersController`

## Methods

* [Get Fee Modifiers Id](../../doc/controllers/fee-modifiers.md#get-fee-modifiers-id)
* [Put Fee Modifiers Id](../../doc/controllers/fee-modifiers.md#put-fee-modifiers-id)
* [Delete Fee Modifiers Id](../../doc/controllers/fee-modifiers.md#delete-fee-modifiers-id)
* [Get Fee Modifiers](../../doc/controllers/fee-modifiers.md#get-fee-modifiers)
* [Post Fee Modifiers](../../doc/controllers/fee-modifiers.md#post-fee-modifiers)


# Get Fee Modifiers Id

Query a Fee Modifier that can change the total amount of the fee or whoever will pay it, such as applying a 10% markup on the fee total for a specific org.

```php
function getFeeModifiersId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): FeeModifiersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource or The Fee Modifier ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`FeeModifiersResponseResult`](../../doc/models/fee-modifiers-response-result.md)

## Example Usage

```php
$id = 't1_fmr_6809dd0aab33df5467c8200';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $feeModifiersController->getFeeModifiersId(
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
        "id": "t1_fmr_6809dd0aab33df5467c8200",
        "created": "2025-04-24 02:41:14.7200",
        "modified": "2025-04-24 02:41:14.7200",
        "creator": "t1_log_670d8844ef246e80758e762",
        "modifier": "t1_log_670d8844ef246e80758e762",
        "fee": "t1_fee_6809dd0aa16f89a3f28ca98",
        "entity": "t1_ent_00c2b1a6102ffdd33f00000",
        "org": "t1_org_00b2ac11ed8bed97fb80000",
        "fromentity": "t1_ent_0088c831a31ca8841c80000",
        "markupUm": 1,
        "markupAmount": 0,
        "inactive": 0,
        "frozen": 0,
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414978f0"
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


# Put Fee Modifiers Id

Update a Fee Modifier that can change the total amount of the fee or whoever will pay it, such as applying a 10% markup on the fee total for a specific org.

```php
function putFeeModifiersId(
    string $id,
    FeeModifiersPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): FeeModifiersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource or The Fee Modifier ID. |
| `body` | [`FeeModifiersPutRequest`](../../doc/models/fee-modifiers-put-request.md) | Body, Required | Update Fee Modifier Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`FeeModifiersResponseResult`](../../doc/models/fee-modifiers-response-result.md)

## Example Usage

```php
$id = 't1_fmr_6809dd0aab33df5467c8200';

$body = FeeModifiersPutRequestBuilder::init()
    ->fee('t1_fee_6809dd0aa16f89a3f28ca98')
    ->entity('t1_ent_00c2b1a6102ffdd33f00000')
    ->org('t1_org_00b2ac11ed8bed97fb80000')
    ->fromentity('t1_ent_0088c831a31ca8841c80000')
    ->markupUm(FeeModifiersMarkupUmEnum::FIXEDAMOUNT)
    ->markupAmount(0)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $feeModifiersController->putFeeModifiersId(
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
        "id": "t1_fmr_6809dd0aab33df5467c8200",
        "created": "2025-04-24 02:41:14.7200",
        "modified": "2025-04-24 02:41:14.7200",
        "creator": "t1_log_670d8844ef246e80758e762",
        "modifier": "t1_log_670d8844ef246e80758e762",
        "fee": "t1_fee_6809dd0aa16f89a3f28ca98",
        "entity": "t1_ent_00c2b1a6102ffdd33f00000",
        "org": "t1_org_00b2ac11ed8bed97fb80000",
        "fromentity": "t1_ent_0088c831a31ca8841c80000",
        "markupUm": 1,
        "markupAmount": 0,
        "inactive": 0,
        "frozen": 0,
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414978f0"
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


# Delete Fee Modifiers Id

Delete a Fee Modifier that can change the total amount of the fee or whoever will pay it, such as applying a 10% markup on the fee total for a specific org.

```php
function deleteFeeModifiersId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): FeeModifiersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The Fee Modifier ID of this resource. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`FeeModifiersResponseResult`](../../doc/models/fee-modifiers-response-result.md)

## Example Usage

```php
$id = 't1_fmr_6809dd0aab33df5467c8200';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $feeModifiersController->deleteFeeModifiersId(
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
        "id": "t1_fmr_6809dd0aab33df5467c8200",
        "created": "2025-04-24 02:41:14.7200",
        "modified": "2025-04-24 02:41:14.7200",
        "creator": "t1_log_670d8844ef246e80758e762",
        "modifier": "t1_log_670d8844ef246e80758e762",
        "fee": "t1_fee_6809dd0aa16f89a3f28ca98",
        "entity": "t1_ent_00c2b1a6102ffdd33f00000",
        "org": "t1_org_00b2ac11ed8bed97fb80000",
        "fromentity": "t1_ent_0088c831a31ca8841c80000",
        "markupUm": 1,
        "markupAmount": 0,
        "inactive": 0,
        "frozen": 0,
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414978f0"
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


# Get Fee Modifiers

Query a Fee Modifier that can change the total amount of the fee or whoever will pay it. For example, a Fee Modifier could apply a 10% markup on the fee total for a specific org.

```php
function getFeeModifiers(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): FeeModifiersResponseResult
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

[`FeeModifiersResponseResult`](../../doc/models/fee-modifiers-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $feeModifiersController->getFeeModifiers(
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
        "id": "t1_fmr_6809dd0aab33df5467c8200",
        "created": "2025-04-24 02:41:14.7200",
        "modified": "2025-04-24 02:41:14.7200",
        "creator": "t1_log_670d8844ef246e80758e762",
        "modifier": "t1_log_670d8844ef246e80758e762",
        "fee": "t1_fee_6809dd0aa16f89a3f28ca98",
        "entity": "t1_ent_00c2b1a6102ffdd33f00000",
        "org": "t1_org_00b2ac11ed8bed97fb80000",
        "fromentity": "t1_ent_0088c831a31ca8841c80000",
        "markupUm": 1,
        "markupAmount": 0,
        "inactive": 0,
        "frozen": 0,
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414978f0"
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


# Post Fee Modifiers

Create a Fee Modifier that can change the total amount of the fee or the party responsible for paying it. For example, a Fee Modifier could apply a 10% markup on the fee total for a specific org.

```php
function postFeeModifiers(
    FeeModifiersPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): FeeModifiersResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`FeeModifiersPostRequest`](../../doc/models/fee-modifiers-post-request.md) | Body, Required | Create Fee Modifier Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`FeeModifiersResponseResult`](../../doc/models/fee-modifiers-response-result.md)

## Example Usage

```php
$body = FeeModifiersPostRequestBuilder::init(
    't1_fee_6809dd0aa16f89a3f28ca98'
)
    ->entity('t1_ent_00c2b1a6102ffdd33f00000')
    ->org('t1_org_00b2ac11ed8bed97fb80000')
    ->fromentity('t1_ent_0088c831a31ca8841c80000')
    ->markupUm(FeeModifiersMarkupUmEnum::FIXEDAMOUNT)
    ->markupAmount(0)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $feeModifiersController->postFeeModifiers(
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
        "id": "t1_fmr_6809dd0aab33df5467c8200",
        "created": "2025-04-24 02:41:14.7200",
        "modified": "2025-04-24 02:41:14.7200",
        "creator": "t1_log_670d8844ef246e80758e762",
        "modifier": "t1_log_670d8844ef246e80758e762",
        "fee": "t1_fee_6809dd0aa16f89a3f28ca98",
        "entity": "t1_ent_00c2b1a6102ffdd33f00000",
        "org": "t1_org_00b2ac11ed8bed97fb80000",
        "fromentity": "t1_ent_0088c831a31ca8841c80000",
        "markupUm": 1,
        "markupAmount": 0,
        "inactive": 0,
        "frozen": 0,
        "division": "t1_div_67c56806728fbbf0bae0b00",
        "partition": "t1_ptn_666834d4d504f21414978f0"
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

