[![Latest Stable Version](https://poser.pugx.org/underdev/utils/v/stable)](https://packagist.org/packages/underdev/utils) [![Total Downloads](https://poser.pugx.org/underdev/utils/downloads)](https://packagist.org/packages/underdev/utils) [![Latest Unstable Version](https://poser.pugx.org/underdev/utils/v/unstable)](https://packagist.org/packages/underdev/utils)

WordPress utilities classes

# Usage example

Include the Composer's autoloader first.

```php
require_once( 'vendor/autoload.php' );
```

## Singleton

```php
use underDEV\Utils\Singleton;

class Example extends Singleton {}

Example::get();
```

## AJAX

```php
use underDEV\Utils\Ajax;

function ajax_callback() {

	$ajax = new Ajax();

	// verify nonce
	// you can pass the $_REQUEST array key for nonce as the second argument
	$ajax->verify_nonce( 'key_for_nonce' );

	// do stuff
	// ...

	// send output
	// if errors array will not be empty, it's considered as an error respose
	$ajax->response( $success = 'success message', $errors = array() );

}
```
