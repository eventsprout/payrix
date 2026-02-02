# Fraud Sight Enablements

```php
$fraudSightEnablementsController = $client->getFraudSightEnablementsController();
```

## Class Name

`FraudSightEnablementsController`

## Methods

* [Get Fraud Sight Enablements Id](../../doc/controllers/fraud-sight-enablements.md#get-fraud-sight-enablements-id)
* [Put Fraud Sight Enablements Id](../../doc/controllers/fraud-sight-enablements.md#put-fraud-sight-enablements-id)
* [Delete Fraud Sight Enablements Id](../../doc/controllers/fraud-sight-enablements.md#delete-fraud-sight-enablements-id)
* [Get Fraud Sight Enablements](../../doc/controllers/fraud-sight-enablements.md#get-fraud-sight-enablements)
* [Post Fraud Sight Enablements](../../doc/controllers/fraud-sight-enablements.md#post-fraud-sight-enablements)
* [Get Fraud Sight Available Rule Groups by Id](../../doc/controllers/fraud-sight-enablements.md#get-fraud-sight-available-rule-groups-by-id)


# Get Fraud Sight Enablements Id

Query a fraudSightEnablements.

```php
function getFraudSightEnablementsId(
    string $id,
    ?string $requestToken = null,
    ?string $embed = null
): FraudSightEnablementsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this Fraud Sight Enablements. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`FraudSightEnablementsResponseResult`](../../doc/models/fraud-sight-enablements-response-result.md)

## Example Usage

```php
$id = 't1_frs_67ea5cb2c4be3c25dbc1zz0';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $fraudSightEnablementsController->getFraudSightEnablementsId(
    $id,
    $requestToken
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_frs_67ea5cb2c4be3c25dbc1zz0",
        "created": "2025-03-31 05:13:22.8143",
        "modified": "2025-03-31 05:13:22.9880",
        "creator": "t1_log_6705400bf224a9c0b4ee098",
        "modifier": "t1_log_6705400bf224a9c0b4ee098",
        "entity": "t1_ent_681238635755abf676f300f",
        "groupName": "PIECPA",
        "description": "Post Network -Decision Non EMV CP & Inform remaining CP",
        "enablementDate": "2025-07-27 11:54:19",
        "org": "t1_org_00b2ac11ed8bed97fb80000",
        "inactive": 0,
        "frozen": 0,
        "deleted": "2025-04-30 12:00:09",
        "deleter": "t1_log_6705400bf224a9c0b4ee098"
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


# Put Fraud Sight Enablements Id

Update a fraudSightEnablements.

```php
function putFraudSightEnablementsId(
    string $id,
    FraudSightEnablementsPutRequest $body,
    ?string $requestToken = null
): FraudSightEnablementsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this Fraud Sight Enablements. |
| `body` | [`FraudSightEnablementsPutRequest`](../../doc/models/fraud-sight-enablements-put-request.md) | Body, Required | Create Fraud Sight Enablements |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`FraudSightEnablementsResponseResult`](../../doc/models/fraud-sight-enablements-response-result.md)

## Example Usage

```php
$id = 't1_frs_67ea5cb2c4be3c25dbc1zz0';

$body = FraudSightEnablementsPutRequestBuilder::init(
    't1_ent_5a1pf5a1234531155a12345',
    GroupNameEnum::PIECPA,
    'The description of the Group Name.'
)->build();

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $fraudSightEnablementsController->putFraudSightEnablementsId(
    $id,
    $body,
    $requestToken
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_frs_67ea5cb2c4be3c25dbc1zz0",
        "created": "2025-03-31 05:13:22.8143",
        "modified": "2025-03-31 05:13:22.9880",
        "creator": "t1_log_6705400bf224a9c0b4ee098",
        "modifier": "t1_log_6705400bf224a9c0b4ee098",
        "entity": "t1_ent_681238635755abf676f300f",
        "groupName": "PIECPA",
        "description": "Post Network -Decision Non EMV CP & Inform remaining CP",
        "enablementDate": "2025-07-27 11:54:19",
        "org": "t1_org_00b2ac11ed8bed97fb80000",
        "inactive": 0,
        "frozen": 0,
        "deleted": "2025-04-30 12:00:09",
        "deleter": "t1_log_6705400bf224a9c0b4ee098"
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


# Delete Fraud Sight Enablements Id

Delete a fraudSightEnablements.

```php
function deleteFraudSightEnablementsId(
    string $id,
    ?string $requestToken = null
): FraudSightEnablementsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of this Fraud Sight Enablements. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`FraudSightEnablementsResponseResult`](../../doc/models/fraud-sight-enablements-response-result.md)

## Example Usage

```php
$id = 't1_frs_67ea5cb2c4be3c25dbc1zz0';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $fraudSightEnablementsController->deleteFraudSightEnablementsId(
    $id,
    $requestToken
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_frs_67ea5cb2c4be3c25dbc1zz0",
        "created": "2025-03-31 05:13:22.8143",
        "modified": "2025-03-31 05:13:22.9880",
        "creator": "t1_log_6705400bf224a9c0b4ee098",
        "modifier": "t1_log_6705400bf224a9c0b4ee098",
        "entity": "t1_ent_681238635755abf676f300f",
        "groupName": "PIECPA",
        "description": "Post Network -Decision Non EMV CP & Inform remaining CP",
        "enablementDate": "2025-07-27 11:54:19",
        "org": "t1_org_00b2ac11ed8bed97fb80000",
        "inactive": 0,
        "frozen": 0,
        "deleted": "2025-04-30 12:00:09",
        "deleter": "t1_log_6705400bf224a9c0b4ee098"
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


# Get Fraud Sight Enablements

Retrieve FraudSight Enablements.

```php
function getFraudSightEnablements(
    ?string $requestToken = null,
    ?string $search = null,
    ?string $totals = null,
    ?int $pageNumber = null,
    ?int $pageLimit = null,
    ?string $embed = null
): FraudSightEnablementsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |
| `search` | `?string` | Header, Optional | Set this header to filter or sort the list of resources that the method returns.<br>See [Searches](page:welcome#searches) for detailed information and examples on how to use search header. |
| `totals` | `?string` | Header, Optional | To configure a request to return a total for all instances of a field in a result set,  use the totals header in the format `totals={operator}[]={key}`.  This will calculate the desired total and return it in the `details > totals` object of the response.  For instance, if you want to sum the `total` field of all transactions,  you would use the `sum` operator. The response will include the result set,  along with the calculated total in the `details` section. See [Collection Operators](page:welcome#collection-operators) for detailed information and examples on how to use totals header. |
| `pageNumber` | `?int` | Query, Optional | Set this path parameter to request a specific page of records.<br>For example, set `?page[number]=2` to retrieve the second page of records for this request. |
| `pageLimit` | `?int` | Query, Optional | Set this path parameter to request up to a specific amount of records. By default 30 records are retrieved per page. The maximum limit that can be set is 100.<br>For example, set `?page[limit]=50` to retrieve up to 50 records for this request. |
| `embed` | `?string` | Query, Optional | Use the embed query parameter to include full object(s) of related resource(s) directly within the API response. This allows retrieval of associated resources in a single request, reducing the need for multiple round-trips.<br>Format: GET https://{server}.payrix.com/{endpoint}?embed={relatedObject} |

## Response Type

[`FraudSightEnablementsResponseResult`](../../doc/models/fraud-sight-enablements-response-result.md)

## Example Usage

```php
$requestToken = '20250423-yourmerchant-refunds-001';

$search = 'created[greater]=2025-01-01';

$totals = 'count[]=id';

$pageNumber = Liquid error: Value cannot be null. (Parameter 'key');

$pageLimit = Liquid error: Value cannot be null. (Parameter 'key');

$result = $fraudSightEnablementsController->getFraudSightEnablements(
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
        "id": "t1_frs_67ea5cb2c4be3c25dbc1zz0",
        "created": "2025-03-31 05:13:22.8143",
        "modified": "2025-03-31 05:13:22.9880",
        "creator": "t1_log_6705400bf224a9c0b4ee098",
        "modifier": "t1_log_6705400bf224a9c0b4ee098",
        "entity": "t1_ent_681238635755abf676f300f",
        "groupName": "PIECPA",
        "description": "Post Network -Decision Non EMV CP & Inform remaining CP",
        "enablementDate": "2025-07-27 11:54:19",
        "org": "t1_org_00b2ac11ed8bed97fb80000",
        "inactive": 0,
        "frozen": 0,
        "deleted": "2025-04-30 12:00:09",
        "deleter": "t1_log_6705400bf224a9c0b4ee098"
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


# Post Fraud Sight Enablements

Enable FraudSight

```php
function postFraudSightEnablements(
    FraudSightEnablementsPostRequest $body,
    ?string $requestToken = null
): FraudSightEnablementsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`FraudSightEnablementsPostRequest`](../../doc/models/fraud-sight-enablements-post-request.md) | Body, Required | Create a FraudSight enablement to activate the FraudSight service for an entity. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`FraudSightEnablementsResponseResult`](../../doc/models/fraud-sight-enablements-response-result.md)

## Example Usage

```php
$body = FraudSightEnablementsPostRequestBuilder::init(
    't1_ent_5a1pf5a1234531155a12345',
    GroupNameEnum::PIECPA,
    'The description of the Group Name.'
)->build();

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $fraudSightEnablementsController->postFraudSightEnablements(
    $body,
    $requestToken
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "data": [
      {
        "id": "t1_frs_67ea5cb2c4be3c25dbc1zz0",
        "created": "2025-03-31 05:13:22.8143",
        "modified": "2025-03-31 05:13:22.9880",
        "creator": "t1_log_6705400bf224a9c0b4ee098",
        "modifier": "t1_log_6705400bf224a9c0b4ee098",
        "entity": "t1_ent_681238635755abf676f300f",
        "groupName": "PIECPA",
        "description": "Post Network -Decision Non EMV CP & Inform remaining CP",
        "enablementDate": "2025-07-27 11:54:19",
        "org": "t1_org_00b2ac11ed8bed97fb80000",
        "inactive": 0,
        "frozen": 0,
        "deleted": "2025-04-30 12:00:09",
        "deleter": "t1_log_6705400bf224a9c0b4ee098"
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


# Get Fraud Sight Available Rule Groups by Id

Returns the list of available FraudSight rule groups for a given entity ID. This response is used to populate the rule group dropdown when creating or updating a FraudSight Enablement for a Merchant or Org.

```php
function getFraudSightAvailableRuleGroupsById(
    string $entityId,
    ?string $requestToken = null
): FraudSightAvailableRuleGroupsResponseResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `entityId` | `string` | Template, Required | The unique identifier of the entity for which FraudSight rule groups should be retrieved. |
| `requestToken` | `?string` | Header, Optional | A custom, one-time identifier for any API request (GET, PUT, POST, or DELETE). Blocks future requests with the same token for 48 hours, ensuring only the first request is processed. Valid values can contain 1-100 alphanumeric and special characters. See <a href="/apis/payrix/dev-int-guide/references/authentication/request-tokens" target="_blank">Request Tokens</a>  for more information. |

## Response Type

[`FraudSightAvailableRuleGroupsResponseResult`](../../doc/models/fraud-sight-available-rule-groups-response-result.md)

## Example Usage

```php
$entityId = 't1_ent_123abc4d567890efg1h2i34';

$requestToken = '20250423-yourmerchant-refunds-001';

$result = $fraudSightEnablementsController->getFraudSightAvailableRuleGroupsById(
    $entityId,
    $requestToken
);
```

## Example Response *(as JSON)*

```json
{
  "response": {
    "ruleGroups": [
      {
        "groupName": "PIECPA",
        "description": "Post Network -Decision Non EMV CP & Inform remaining CP"
      },
      {
        "groupName": "PICNP",
        "description": "Post Network - Decision CNP only & Inform CP"
      },
      {
        "groupName": "PACPA",
        "description": "Post Network - Decision All CP Authorizations"
      },
      {
        "groupName": "INCNP",
        "description": "Pre Network -Decision Non-Recurring CNP & Inform CP"
      },
      {
        "groupName": "PIKCPA",
        "description": "Post Network -Decision Key Entered CP & Inform remaining CP"
      },
      {
        "groupName": "IECNP",
        "description": "Pre Network -Decision CNP and Non EMV CP & Inform remaining CP"
      },
      {
        "groupName": "ACPA",
        "description": "Pre Network - Decision All CP Authorizations"
      },
      {
        "groupName": "PACNP",
        "description": "Post Network - Decision All Authorizations (CNP & CP)"
      },
      {
        "groupName": "PIECNP",
        "description": "Post Network -Decision CNP and Non EMV CP & Inform remaining CP"
      },
      {
        "groupName": "IKCPA",
        "description": "Pre Network -Decision Key Entered CP & Inform remaining CP"
      },
      {
        "groupName": "ACNP",
        "description": "Pre Network - Decision All Authorizations (CNP & CP)"
      },
      {
        "groupName": "PINCNP",
        "description": "Post Network -Decision Non-Recurring CNP & Inform CP"
      },
      {
        "groupName": "IECPA",
        "description": "Pre Network -Decision Non EMV CP & Inform remaining CP"
      },
      {
        "groupName": "ICNP",
        "description": "Pre Network - Decision CNP only & Inform CP"
      }
    ],
    "httpStatusCode": "200",
    "httpStatusMessage": "OK",
    "correlationId": "string"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Error | [`ErrorFourHundredException`](../../doc/models/error-four-hundred-exception.md) |

