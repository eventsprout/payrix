
# Custom Header Signature



Documentation for accessing and setting credentials for txnSessionKey.

## Auth Credentials

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| TXNSESSIONKEY | `string` | - | `tXNSESSIONKEY` | `getTXNSESSIONKEY()` |



**Note:** Auth credentials can be set using `TxnSessionKeyCredentialsBuilder::init()` in `txnSessionKeyCredentials` method in the client builder and accessed through `getTxnSessionKeyCredentials` method in the client instance.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

```php
use PayrixLib\Authentication\TxnSessionKeyCredentialsBuilder;
use PayrixLib\PayrixClientBuilder;

$client = PayrixClientBuilder::init()
    ->txnSessionKeyCredentials(
        TxnSessionKeyCredentialsBuilder::init(
            'TXNSESSIONKEY'
        )
    )
    ->build();
```


