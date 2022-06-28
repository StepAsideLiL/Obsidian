# `class WooCommerce`
single instance of this class
```php
class WooCommerce {}
```
___
## variables
##### `$_instance`
->single instance of this class
```php
protected static $_instance = null;
```


## functions
##### `instance()`
Main WooCommerce Instance
->return `WooCommerce` - Main Instance
```php
public static function instance() {
	if ( is_null( self::$_instance ) ) {
		self::$_instance = new self();
	}
	return self::$_instance;
}
```

##### `__construct()`
WooCommerce constructor
```php
public function __construct() {
	$this->define_constants();
	$this->define_tables();
	$this->includes();
	$this->init_hooks();
}
```

##### `define_constants()`
Define WooCommerce constants
```php
private function define_constants() {
	$this->define( 'WC_ABSPATH', dirname( WC_PLUGIN_FILE ) . '/' );
}
```

##### `define( $name, $value )`
```php
private function define( $name, $value ) {
	if ( ! defined( $name ) ) {
		define( $name, $value );
	}
}
```

##### `define_tables()`
Register custom tables within $wpdb object.
```php
private function define_tables() {}
```

##### `includes()`
Include required core files used in admin and on the frontend.
```php
public function includes() {
	include_once WC_ABSPATH . 'includes/class-wc-post-types.php';
	include_once WC_ABSPATH . 'includes/class-wc-install.php';
}
```

##### `init_hooks()`
->calls `WC_Install::install` => [[class-wc-install.php#install]]
```php
private function init_hooks() {
	register_activation_hook( WC_PLUGIN_FILE, array( 'WC_Install', 'install' ) );
}
```