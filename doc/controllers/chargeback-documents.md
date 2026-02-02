# Chargeback Documents

```php
$chargebackDocumentsController = $client->getChargebackDocumentsController();
```

## Class Name

`ChargebackDocumentsController`

## Methods

* [Get Chargeback Documents Id](../../doc/controllers/chargeback-documents.md#get-chargeback-documents-id)
* [Put Chargeback Documents Id](../../doc/controllers/chargeback-documents.md#put-chargeback-documents-id)
* [Delete Chargeback Documents Id](../../doc/controllers/chargeback-documents.md#delete-chargeback-documents-id)
* [Get Chargeback Documents](../../doc/controllers/chargeback-documents.md#get-chargeback-documents)
* [Post Chargeback Documents](../../doc/controllers/chargeback-documents.md#post-chargeback-documents)


# Get Chargeback Documents Id

Query a chargebackDocument. A chargebackDocument resource represents a file related to a Chargeback.

```php
function getChargebackDocumentsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): ChargebackDocumentsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this chargeback document. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`ChargebackDocumentsResponseResult`](../../doc/models/chargeback-documents-response-result.md)

## Example Usage

```php
$id = 't1_chd_679a4a2ba49405540af4856';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $chargebackDocumentsController->getChargebackDocumentsId(
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
        "id": "p1_chd_67b31fca23feed2b88d8a59",
        "created": "2025-02-17 06:38:50.1502",
        "modified": "2025-02-17 06:38:50.1502",
        "creator": "t1_log_5d49bbb9bd62b95c1378542",
        "modifier": "t1_log_5d49bbb9bd62b95c1378542",
        "chargeback": "t1_chb_679918b34232ae6145ec03e",
        "ref": "p1_chd_67b31fca23feed2b88d8a59.pdf",
        "type": "pdf",
        "name": "Test PDF  copy.pdf",
        "description": "Test PDF  copy.pdf",
        "inactive": 0,
        "frozen": 0,
        "status": "created",
        "documentSource": "merchant"
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


# Put Chargeback Documents Id

Update a chargebackDocument. A chargebackDocument resource represents a file related to a Chargeback.

```php
function putChargebackDocumentsId(
    string $id,
    ChargebacksDocumentsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): ChargebackDocumentsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this chargeback document. |
| `body` | [`ChargebacksDocumentsPutRequest`](../../doc/models/chargebacks-documents-put-request.md) | Body, Required | Update Chargeback Document Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ChargebackDocumentsResponseResult`](../../doc/models/chargeback-documents-response-result.md)

## Example Usage

```php
$id = 't1_chd_679a4a2ba49405540af4856';

$body = ChargebacksDocumentsPutRequestBuilder::init()
    ->type(ChargebackDocumentTypeEnum::PDF)
    ->ref('p1_chd_67b31fca23feed2b88d8a59.pdf')
    ->description('Test PDF  copy.pdf')
    ->name('Test PDF  copy.pdf')
    ->documentSource(ChargebackDocumentsDocumentSourceEnum::MERCHANT)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $chargebackDocumentsController->putChargebackDocumentsId(
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
        "id": "p1_chd_67b31fca23feed2b88d8a59",
        "created": "2025-02-17 06:38:50.1502",
        "modified": "2025-02-17 06:38:50.1502",
        "creator": "t1_log_5d49bbb9bd62b95c1378542",
        "modifier": "t1_log_5d49bbb9bd62b95c1378542",
        "chargeback": "t1_chb_679918b34232ae6145ec03e",
        "ref": "p1_chd_67b31fca23feed2b88d8a59.pdf",
        "type": "pdf",
        "name": "Test PDF  copy.pdf",
        "description": "Test PDF  copy.pdf",
        "inactive": 0,
        "frozen": 0,
        "status": "created",
        "documentSource": "merchant"
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


# Delete Chargeback Documents Id

Delete a chargebackDocument. A chargebackDocument resource represents a file related to a Chargeback.

```php
function deleteChargebackDocumentsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): ChargebackDocumentsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this chargeback document. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ChargebackDocumentsResponseResult`](../../doc/models/chargeback-documents-response-result.md)

## Example Usage

```php
$id = 't1_chd_679a4a2ba49405540af4856';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $chargebackDocumentsController->deleteChargebackDocumentsId(
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
        "id": "p1_chd_67b31fca23feed2b88d8a59",
        "created": "2025-02-17 06:38:50.1502",
        "modified": "2025-02-17 06:38:50.1502",
        "creator": "t1_log_5d49bbb9bd62b95c1378542",
        "modifier": "t1_log_5d49bbb9bd62b95c1378542",
        "chargeback": "t1_chb_679918b34232ae6145ec03e",
        "ref": "p1_chd_67b31fca23feed2b88d8a59.pdf",
        "type": "pdf",
        "name": "Test PDF  copy.pdf",
        "description": "Test PDF  copy.pdf",
        "inactive": 0,
        "frozen": 0,
        "status": "created",
        "documentSource": "merchant"
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


# Get Chargeback Documents

Query chargebackDocuments, each representing a file related to a Chargeback.

```php
function getChargebackDocuments(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): ChargebackDocumentsResponseResult
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

[`ChargebackDocumentsResponseResult`](../../doc/models/chargeback-documents-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $chargebackDocumentsController->getChargebackDocuments(
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
        "id": "p1_chd_67b31fca23feed2b88d8a59",
        "created": "2025-02-17 06:38:50.1502",
        "modified": "2025-02-17 06:38:50.1502",
        "creator": "t1_log_5d49bbb9bd62b95c1378542",
        "modifier": "t1_log_5d49bbb9bd62b95c1378542",
        "chargeback": "t1_chb_679918b34232ae6145ec03e",
        "ref": "p1_chd_67b31fca23feed2b88d8a59.pdf",
        "type": "pdf",
        "name": "Test PDF  copy.pdf",
        "description": "Test PDF  copy.pdf",
        "inactive": 0,
        "frozen": 0,
        "status": "created",
        "documentSource": "merchant"
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


# Post Chargeback Documents

Create a chargebackDocument resource that represents a file related to a Chargeback.

```php
function postChargebackDocuments(
    ChargebackDocumentsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): ChargebackDocumentsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`ChargebackDocumentsPostRequest`](../../doc/models/chargeback-documents-post-request.md) | Body, Required | Create Chargeback Document Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`ChargebackDocumentsResponseResult`](../../doc/models/chargeback-documents-response-result.md)

## Example Usage

```php
$body = ChargebackDocumentsPostRequestBuilder::init(
    't1_chb_679918b34232ae6145ec03e'
)
    ->type(ChargebackDocumentTypeEnum::PDF)
    ->ref('p1_chd_67b31fca23feed2b88d8a59.pdf')
    ->description('Test PDF  copy.pdf')
    ->name('Test PDF  copy.pdf')
    ->documentSource(ChargebackDocumentsDocumentSourceEnum::MERCHANT)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $chargebackDocumentsController->postChargebackDocuments(
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
        "id": "p1_chd_67b31fca23feed2b88d8a59",
        "created": "2025-02-17 06:38:50.1502",
        "modified": "2025-02-17 06:38:50.1502",
        "creator": "t1_log_5d49bbb9bd62b95c1378542",
        "modifier": "t1_log_5d49bbb9bd62b95c1378542",
        "chargeback": "t1_chb_679918b34232ae6145ec03e",
        "ref": "p1_chd_67b31fca23feed2b88d8a59.pdf",
        "type": "pdf",
        "name": "Test PDF  copy.pdf",
        "description": "Test PDF  copy.pdf",
        "inactive": 0,
        "frozen": 0,
        "status": "created",
        "documentSource": "merchant"
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

