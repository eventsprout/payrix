
# Custom Header Signature



Documentation for accessing and setting credentials for sessionKey.

## Auth Credentials

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| SESSIONKEY | `string` | - | `sESSIONKEY` | `getSESSIONKEY()` |



**Note:** Auth credentials can be set using `SessionKeyCredentialsBuilder::init()` in `sessionKeyCredentials` method in the client builder and accessed through `getSessionKeyCredentials` method in the client instance.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

```php
use PayrixLib\Authentication\SessionKeyCredentialsBuilder;
use PayrixLib\PayrixClientBuilder;

$client = PayrixClientBuilder::init()
    ->sessionKeyCredentials(
        SessionKeyCredentialsBuilder::init(
            'SESSIONKEY'
        )
    )
    ->build();
```


