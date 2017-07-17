[![Latest Stable Version](https://poser.pugx.org/underdev/utils/v/stable)](https://packagist.org/packages/underdev/utils) [![Total Downloads](https://poser.pugx.org/underdev/utils/downloads)](https://packagist.org/packages/underdev/utils) [![Latest Unstable Version](https://poser.pugx.org/underdev/utils/v/unstable)](https://packagist.org/packages/underdev/utils)

WordPress utilities classes

# Usage example

Include the Composer's autoloader first.

```
require_once( 'vendor/autoload.php' );
```

## Singleton

```
use underDEV\Utils\Singleton;

class Example extends Singleton {}

Example::get();

```
