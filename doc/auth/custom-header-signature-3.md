
# Custom Header Signature



Documentation for accessing and setting credentials for username.

## Auth Credentials

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| USERNAME | `string` | - | `uSERNAME` | `getUSERNAME()` |



**Note:** Auth credentials can be set using `UsernameCredentialsBuilder::init()` in `usernameCredentials` method in the client builder and accessed through `getUsernameCredentials` method in the client instance.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

```php
use PayrixLib\Authentication\UsernameCredentialsBuilder;
use PayrixLib\PayrixClientBuilder;

$client = PayrixClientBuilder::init()
    ->usernameCredentials(
        UsernameCredentialsBuilder::init(
            'USERNAME'
        )
    )
    ->build();
```


