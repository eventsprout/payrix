# Confirmation Codes

```php
$confirmationCodesController = $client->getConfirmationCodesController();
```

## Class Name

`ConfirmationCodesController`

## Methods

* [Get Confirm Codes Id](../../doc/controllers/confirmation-codes.md#get-confirm-codes-id)
* [Delete Confirm Codes Id](../../doc/controllers/confirmation-codes.md#delete-confirm-codes-id)
* [Get Confirm Codes](../../doc/controllers/confirmation-codes.md#get-confirm-codes)
* [Post Confirm Codes](../../doc/controllers/confirmation-codes.md#post-confirm-codes)


# Get Confirm Codes Id

Query a confirmCode resource, which represents a unique confirmation code issued to an email address, either when a user indicates that they have forgotten their password, or when the system needs to verify the email address associated with a login.

```php
function getConfirmCodesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null,
    ?string $search = null
): ConfirmCodesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Confirmation Code ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |
| `search` | `?string` | Header, Optional | Set this header to filter or sort the list of resources that the method returns.<br>See [Searches](page:welcome#searches) for detailed information and examples on how to use search header. |

## Response Type

[`ConfirmCodesResponseResult`](../../doc/models/confirm-codes-response-result.md)

## Example Usage

```php
$id = 'p1_cfc_67dd2714a9a1fc91f994e00';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$result = $confirmationCodesController->getConfirmCodesId(
    $id,
    $token,
    $requestToken,
    null,
    $search
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "p1_cfc_67dd2714a9a1fc91f994e00",
        "created": "2025-03-21 04:45:08.6978",
        "modified": "2025-03-21 04:45:08.6978",
        "creator": "p1_log_00b869779727da108515d99",
        "modifier": "p1_log_00b869779727da108515d99",
        "login": "p1_log_67dd2714959c3331228ffa3",
        "type": "email",
        "key": "fbdf954596b341d18cb4995b70d321f3",
        "email": "vijay.sample@payrix.com",
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


# Delete Confirm Codes Id

Delete a confirmCode resource. A confirmCode resource represents a unique confirmation code issued to an email address, either when a user indicates that they have forgotten their password, or when the system needs to verify the email address associated with a login.

```php
function deleteConfirmCodesId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): ConfirmCodesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this resource and The Confirmation Code ID. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ConfirmCodesResponseResult`](../../doc/models/confirm-codes-response-result.md)

## Example Usage

```php
$id = 'p1_cfc_67dd2714a9a1fc91f994e00';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $confirmationCodesController->deleteConfirmCodesId(
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
        "id": "p1_cfc_67dd2714a9a1fc91f994e00",
        "created": "2025-03-21 04:45:08.6978",
        "modified": "2025-03-21 04:45:08.6978",
        "creator": "p1_log_00b869779727da108515d99",
        "modifier": "p1_log_00b869779727da108515d99",
        "login": "p1_log_67dd2714959c3331228ffa3",
        "type": "email",
        "key": "fbdf954596b341d18cb4995b70d321f3",
        "email": "vijay.sample@payrix.com",
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


# Get Confirm Codes

Query a confirmCode resource. A confirmCode resource represents a unique confirmation code issued to an email address, either when a user indicates that they have forgotten their password, or when the system needs to verify the email address associated with a login.

```php
function getConfirmCodes(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): ConfirmCodesResponseResult
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

[`ConfirmCodesResponseResult`](../../doc/models/confirm-codes-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $confirmationCodesController->getConfirmCodes(
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
        "id": "p1_cfc_67dd2714a9a1fc91f994e00",
        "created": "2025-03-21 04:45:08.6978",
        "modified": "2025-03-21 04:45:08.6978",
        "creator": "p1_log_00b869779727da108515d99",
        "modifier": "p1_log_00b869779727da108515d99",
        "login": "p1_log_67dd2714959c3331228ffa3",
        "type": "email",
        "key": "fbdf954596b341d18cb4995b70d321f3",
        "email": "vijay.sample@payrix.com",
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


# Post Confirm Codes

Create a confirmCode resource that represents a unique confirmation code issued to an email address, either when a user indicates that they have forgotten their password, or when the system needs to verify the email address associated with a login.

```php
function postConfirmCodes(
    ConfirmCodesPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): ConfirmCodesResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`ConfirmCodesPostRequest`](../../doc/models/confirm-codes-post-request.md) | Body, Required | Create Confirmation Code Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ConfirmCodesResponseResult`](../../doc/models/confirm-codes-response-result.md)

## Example Usage

```php
$body = ConfirmCodesPostRequestBuilder::init(
    'p1_log_67dd2714959c3331228ffa3',
    ConfirmCodeTypeEnum::EMAIL,
    'fbdf954596b341d18cb4995b70d321f3'
)
    ->email('vijay.sample@payrix.com')
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $confirmationCodesController->postConfirmCodes(
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
        "id": "p1_cfc_67dd2714a9a1fc91f994e00",
        "created": "2025-03-21 04:45:08.6978",
        "modified": "2025-03-21 04:45:08.6978",
        "creator": "p1_log_00b869779727da108515d99",
        "modifier": "p1_log_00b869779727da108515d99",
        "login": "p1_log_67dd2714959c3331228ffa3",
        "type": "email",
        "key": "fbdf954596b341d18cb4995b70d321f3",
        "email": "vijay.sample@payrix.com",
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

