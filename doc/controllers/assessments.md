# Assessments

Assessments represents a record of fees charged by processors or other third-parties to Entities or Orgs. These can represent either charges that are levied on a one-off, regularly scheduled, or event-driven basis.

```php
$assessmentsController = $client->getAssessmentsController();
```

## Class Name

`AssessmentsController`

## Methods

* [Get Assessments Id](../../doc/controllers/assessments.md#get-assessments-id)
* [Get Assessments](../../doc/controllers/assessments.md#get-assessments)


# Get Assessments Id

Query an Assessment resource that represents a record of fees charged by processors or other third parties to Entities or Orgs. Fees can represent charges that are levied on a one-off, regularly scheduled, or event-driven basis.

```php
function getAssessmentsId(
    string $id,
    ?string $token = null,
    ?string $requestToken = null,
    ?string $embed = null
): AssessmentsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this assessment. |
| `token` | `?string` | Header, Optional | A single-use, limited authentication layer in addition to an API Key or Session Key to authorize sensitive operations. <a href="/apis/payrix/dev-int-guide/references/authentication/auth-tokens" target="_blank">Auth Tokens</a> add security by requiring one-time approval for specific actions. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`AssessmentsResponseResult`](../../doc/models/assessments-response-result.md)

## Example Usage

```php
$id = 't1_ast_12a003cde5d6b2ec3d9canb';

$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $assessmentsController->getAssessmentsId(
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
        "id": "t1_ast_11ad1aca636fb9f4a1abc00",
        "created": "2025-02-13 01:01:46.4073",
        "modified": "2025-02-13 01:01:46.4073",
        "creator": "000000000000001",
        "modifier": "000000000000001",
        "entity": "t1_ent_5b3bdeac000c06c43505a00",
        "onentity": "t1_ent_5b3bdeac000c06c43505a01",
        "forentity": "t1_ent_5b3bdeac000c06c43505a02",
        "partition": "a100003azz9b911",
        "opposingAssessment": "t1_ast_11ad8aca6269fc70a81cfaa",
        "fee": "t1_fee_5b3bdeac000c06c43505a00",
        "disbursement": "t1_dbm_121cb1111e11d00a1fac5b1",
        "txn": "t1_txn_9a0aa0000f08553bcc1aaa9",
        "chargeback": "t1_chb_111cb1111e11d00a1fac5b0",
        "merchant": "t1_mer_111cb1111e11d00a1fac5b0",
        "event": 6,
        "eventId": "t1_txn_9a0aa0000f08553bcc1aaa9",
        "description": "AUTH fee schedule",
        "amount": 30,
        "platform": "VANTIV",
        "currency": "USD"
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


# Get Assessments

Query an Assessment resource that represents a record of fees charged by processors or other third parties to Entities or Orgs. These fees are levied on a one-off, regularly scheduled, or event-driven basis.

```php
function getAssessments(
    ?string $token = null,
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): AssessmentsResponseResult
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

[`AssessmentsResponseResult`](../../doc/models/assessments-response-result.md)

## Example Usage

```php
$token = 'a12bc3d4e56f789g0h1ij23kl456789';

$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $assessmentsController->getAssessments(
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
        "id": "t1_ast_11ad1aca636fb9f4a1abc00",
        "created": "2025-02-13 01:01:46.4073",
        "modified": "2025-02-13 01:01:46.4073",
        "creator": "000000000000001",
        "modifier": "000000000000001",
        "entity": "t1_ent_5b3bdeac000c06c43505a00",
        "onentity": "t1_ent_5b3bdeac000c06c43505a01",
        "forentity": "t1_ent_5b3bdeac000c06c43505a02",
        "partition": "a100003azz9b911",
        "opposingAssessment": "t1_ast_11ad8aca6269fc70a81cfaa",
        "fee": "t1_fee_5b3bdeac000c06c43505a00",
        "disbursement": "t1_dbm_121cb1111e11d00a1fac5b1",
        "txn": "t1_txn_9a0aa0000f08553bcc1aaa9",
        "chargeback": "t1_chb_111cb1111e11d00a1fac5b0",
        "merchant": "t1_mer_111cb1111e11d00a1fac5b0",
        "event": 6,
        "eventId": "t1_txn_9a0aa0000f08553bcc1aaa9",
        "description": "AUTH fee schedule",
        "amount": 30,
        "platform": "VANTIV",
        "currency": "USD"
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

