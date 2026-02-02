
# Custom Header Signature



Documentation for accessing and setting credentials for apiKey.

## Auth Credentials

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| APIKEY | `string` | - | `aPIKEY` | `getAPIKEY()` |



**Note:** Auth credentials can be set using `ApiKeyCredentialsBuilder::init()` in `apiKeyCredentials` method in the client builder and accessed through `getApiKeyCredentials` method in the client instance.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

```php
use PayrixLib\Authentication\ApiKeyCredentialsBuilder;
use PayrixLib\PayrixClientBuilder;

$client = PayrixClientBuilder::init()
    ->apiKeyCredentials(
        ApiKeyCredentialsBuilder::init(
            'APIKEY'
        )
    )
    ->build();
```


