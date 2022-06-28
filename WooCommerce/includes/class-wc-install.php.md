# `class WC_Install`
```php
class WC_Install {}
```

### `functions`
##### `install()`
Install WooCommerce
```php
public static function install() {
	if ( 'yes' === get_transient( 'wc_installing' ) ) {
		return;
	}
	set_transient( 'wc_installing', 'yes', MINUTE_IN_SECONDS * 10 );
	wc_maybe_define_constant( 'WC_INSTALLING', true );
	
	self::setup_environment();
	
	delete_transient( 'wc_installing' );
	
	do_action( 'woocommerce_flush_rewrite_rules' );
	do_action( 'woocommerce_installed' );
}
```

##### `setup_environment()`
Setup WC environment - post types, taxonomies, endpoints.
->calls `WC_Post_types::register_post_types()` => [[class-wc-post-types.php#register_post_types]]
```php
private static function setup_environment() {
	WC_Post_types::register_post_types();
}
```