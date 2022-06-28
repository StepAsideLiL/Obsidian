# `class WC_Post_Types`
```php
class WC_Post_Types {}
```

## functions
##### `init()`
->calls `register_post_types()` => [[class-wc-post-types.php#register_post_types]]
->calls `maybe_flush_rewrite_rules()` => [[class-wc-post-types.php#maybe_flush_rewrite_rules]]
```php
public static function init() {
	add_action( 'init', array( __CLASS__, 'register_post_types' ), 5 );
	add_action( 'woocommerce_after_register_post_type', array( __CLASS__, 'maybe_flush_rewrite_rules' ) );
}
```

##### `register_post_types()`
Register core post types.
```php
public static function register_post_types() {
	register_post_type( 'product', ... );
	
	do_action( 'woocommerce_after_register_post_type' );
}
```

##### `maybe_flush_rewrite_rules()`
Flush rules if the event is queued.
```php
public static function maybe_flush_rewrite_rules() {
	if ( 'yes' === get_option( 'woocommerce_queue_flush_rewrite_rules' ) ) {
		update_option( 'woocommerce_queue_flush_rewrite_rules', 'no' );
		self::flush_rewrite_rules();
	}
}
```

##### `flush_rewrite_rules()`
Flush rewrite rules.
```php
public static function flush_rewrite_rules() {
	flush_rewrite_rules();
}
```