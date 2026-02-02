
# Custom Header Signature



Documentation for accessing and setting credentials for password.

## Auth Credentials

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| PASSWORD | `string` | - | `pASSWORD` | `getPASSWORD()` |



**Note:** Auth credentials can be set using `PasswordCredentialsBuilder::init()` in `passwordCredentials` method in the client builder and accessed through `getPasswordCredentials` method in the client instance.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

```php
use PayrixLib\Authentication\PasswordCredentialsBuilder;
use PayrixLib\PayrixClientBuilder;

$client = PayrixClientBuilder::init()
    ->passwordCredentials(
        PasswordCredentialsBuilder::init(
            'PASSWORD'
        )
    )
    ->build();
```


