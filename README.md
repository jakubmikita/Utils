[![Latest Stable Version](https://poser.pugx.org/underdev/utils/v/stable)](https://packagist.org/packages/underdev/utils) [![Total Downloads](https://poser.pugx.org/underdev/utils/downloads)](https://packagist.org/packages/underdev/utils) [![Latest Unstable Version](https://poser.pugx.org/underdev/utils/v/unstable)](https://packagist.org/packages/underdev/utils)

WordPress utilities classes for plugin development

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

Helper for AJAX requests.

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

## Files

Helper for plugin's files.

```php
use underDEV\Utils\Files;

// argument should be the main plugin file
$files = new Files( __FILE__ );

// get asset url
// will return: your-plugin/assets/dist/css/style.css
$files->asset_url( 'css', 'style.css' )

// get vendor asset url
// will return: your-plugin/assets/vendor/vendor_name/asset.css
$files->vendor_asset_url( 'vendor_name', 'asset.css' )
```

For all methods please check the class source.

## View

Helper for loading views. Uses the Files class.

```php
use underDEV\Utils\Files;
use underDEV\Utils\View;

// argument should be the main plugin file
$files = new Files( __FILE__ );
$view  = new View( $files );

// set some view var
$view->set_var( 'var_name', 'value' );

// load view
// this will load ./views/parts/menu.php
$view->get_view( 'parts/menu' );
```

In template file you can get vars

```html
<div><?php echo $this->get_var( 'var_name' ); ?></div>
```

To have different scopes in templates you have to instantinate different classes.
