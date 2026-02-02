# Note Documents

```php
$noteDocumentsController = $client->getNoteDocumentsController();
```

## Class Name

`NoteDocumentsController`

## Methods

* [Get Note Documents Id](../../doc/controllers/note-documents.md#get-note-documents-id)
* [Put Note Documents Id](../../doc/controllers/note-documents.md#put-note-documents-id)
* [Delete Note Documents Id](../../doc/controllers/note-documents.md#delete-note-documents-id)
* [Get Note Documents](../../doc/controllers/note-documents.md#get-note-documents)
* [Post Note Documents](../../doc/controllers/note-documents.md#post-note-documents)


# Get Note Documents Id

Query a Note Document that represents a file that is related to a specific note record.

```php
function getNoteDocumentsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): NoteDocumentsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this note document. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`NoteDocumentsResponseResult`](../../doc/models/note-documents-response-result.md)

## Example Usage

```php
$id = 't1_ntd_67eef7a7ac0627e1fce0000';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $noteDocumentsController->getNoteDocumentsId(
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
        "id": "t1_ntd_67eef7a7ac0627e1fce0000",
        "created": "2025-04-03 17:03:35.7120",
        "modified": "2025-04-03 17:03:36.4841",
        "creator": "t1_log_6310f9e4d21c262e2f1404c",
        "modifier": "t1_log_6310f9e4d21c262e2f1404c",
        "note": "t1_not_67eef7a7a830eb17b0aefd5",
        "custom": "",
        "type": "png",
        "documentType": "voidCheck",
        "name": "Boy1.png",
        "description": "doc description1",
        "status": "processed",
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


# Put Note Documents Id

Update a note document, which represents a file related to a specific note record.

```php
function putNoteDocumentsId(
    string $id,
    NoteDocumentsPutRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): NoteDocumentsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this note document. |
| `body` | [`NoteDocumentsPutRequest`](../../doc/models/note-documents-put-request.md) | Body, Required | Update Note Document Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`NoteDocumentsResponseResult`](../../doc/models/note-documents-response-result.md)

## Example Usage

```php
$id = 't1_ntd_67eef7a7ac0627e1fce0000';

$body = NoteDocumentsPutRequestBuilder::init()
    ->type(NoteDocumentTypeEnum::PNG)
    ->name('Boy1.png')
    ->custom('identifier')
    ->description('doc description1')
    ->status(NoteDocumentStatusEnum::PROCESSED)
    ->documentType(NoteDocumentsDocumentTypeEnum::VOIDCHECK)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $noteDocumentsController->putNoteDocumentsId(
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
        "id": "t1_ntd_67eef7a7ac0627e1fce0000",
        "created": "2025-04-03 17:03:35.7120",
        "modified": "2025-04-03 17:03:36.4841",
        "creator": "t1_log_6310f9e4d21c262e2f1404c",
        "modifier": "t1_log_6310f9e4d21c262e2f1404c",
        "note": "t1_not_67eef7a7a830eb17b0aefd5",
        "custom": "",
        "type": "png",
        "documentType": "voidCheck",
        "name": "Boy1.png",
        "description": "doc description1",
        "status": "processed",
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


# Delete Note Documents Id

Delete a Note Document, which represents a file related to a specific note record.

```php
function deleteNoteDocumentsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null
): NoteDocumentsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this note document. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`NoteDocumentsResponseResult`](../../doc/models/note-documents-response-result.md)

## Example Usage

```php
$id = 't1_ntd_67eef7a7ac0627e1fce0000';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $noteDocumentsController->deleteNoteDocumentsId(
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
        "id": "t1_ntd_67eef7a7ac0627e1fce0000",
        "created": "2025-04-03 17:03:35.7120",
        "modified": "2025-04-03 17:03:36.4841",
        "creator": "t1_log_6310f9e4d21c262e2f1404c",
        "modifier": "t1_log_6310f9e4d21c262e2f1404c",
        "note": "t1_not_67eef7a7a830eb17b0aefd5",
        "custom": "",
        "type": "png",
        "documentType": "voidCheck",
        "name": "Boy1.png",
        "description": "doc description1",
        "status": "processed",
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


# Get Note Documents

Query a Note Document, which represents a file that is related to a specific note record and documents resources.

```php
function getNoteDocuments(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): NoteDocumentsResponseResult
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

[`NoteDocumentsResponseResult`](../../doc/models/note-documents-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $noteDocumentsController->getNoteDocuments(
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
        "id": "t1_ntd_67eef7a7ac0627e1fce0000",
        "created": "2025-04-03 17:03:35.7120",
        "modified": "2025-04-03 17:03:36.4841",
        "creator": "t1_log_6310f9e4d21c262e2f1404c",
        "modifier": "t1_log_6310f9e4d21c262e2f1404c",
        "note": "t1_not_67eef7a7a830eb17b0aefd5",
        "custom": "",
        "type": "png",
        "documentType": "voidCheck",
        "name": "Boy1.png",
        "description": "doc description1",
        "status": "processed",
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


# Post Note Documents

Create a note document, representing a file related to a specific note record.

```php
function postNoteDocuments(
    NoteDocumentsPostRequest $body,
    ?string $token = null,
    ?string $requestToken = null
): NoteDocumentsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`NoteDocumentsPostRequest`](../../doc/models/note-documents-post-request.md) | Body, Required | Create Note Document Request |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`NoteDocumentsResponseResult`](../../doc/models/note-documents-response-result.md)

## Example Usage

```php
$body = NoteDocumentsPostRequestBuilder::init(
    't1_not_67eef7a7a830eb17b0aefd5'
)
    ->type(NoteDocumentTypeEnum::PNG)
    ->name('Boy1.png')
    ->custom('identifier')
    ->description('doc description1')
    ->status(NoteDocumentStatusEnum::PROCESSED)
    ->documentType(NoteDocumentsDocumentTypeEnum::VOIDCHECK)
    ->inactive(InactiveEnum::ACTIVE)
    ->frozen(FrozenEnum::NOTFROZEN)
    ->build();

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $noteDocumentsController->postNoteDocuments(
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
        "id": "t1_ntd_67eef7a7ac0627e1fce0000",
        "created": "2025-04-03 17:03:35.7120",
        "modified": "2025-04-03 17:03:36.4841",
        "creator": "t1_log_6310f9e4d21c262e2f1404c",
        "modifier": "t1_log_6310f9e4d21c262e2f1404c",
        "note": "t1_not_67eef7a7a830eb17b0aefd5",
        "custom": "",
        "type": "png",
        "documentType": "voidCheck",
        "name": "Boy1.png",
        "description": "doc description1",
        "status": "processed",
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

