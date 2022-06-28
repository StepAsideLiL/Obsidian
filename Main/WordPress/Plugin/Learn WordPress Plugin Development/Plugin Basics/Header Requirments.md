# my-plugin.php
Minimum header comment you have to write to appear your plugin in the WordPress Plugins menu
```php
<?php
/**
 * Plugin Name: My Plugin
 */
```

<br>

These are the available header fields
```php
<?php
/**
 * Plugin Name:       My Plugin
 * Plugin URI:        https://my-plugin.com/
 * Description:       My Plugin is a besic learning plugin.
 * Version:           0.0.1
 * Requires at least: 5.9
 * Requires PHP:      7.4
 * Author:            Myself
 * Author URI:        https://my.self/
 * License:           GPL v2 or later
 * License URI:       https://www.gnu.org/licenses/gpl-2.0.html
 * Update URI:        https://my.self/my-plugin/
 * Text Domain:       my-plugin
 * Domain Path:       /languages
 */
```

for more info: [Header Requirements | Plugin Developer Handbook | WordPress Developer Resources](https://developer.wordpress.org/plugins/plugin-basics/header-requirements/)

<br>

### Exit if the plugin is accessed directly.
```php
// Exit if the plugin is accessed directly.
if ( !defined( 'ABSPATH' ) || !function_exists( 'add_action' ) ) {
    echo 'You are not supposed to call me directly.';
    exit;
}
```

<br>

### Define some plugin constent
```php
define( 'MYPLUGIN_VERSION', '4.2.2' );
define( 'MYPLUGIN_MINIMUM_WP_VERSION', '5.9' );
define( 'MYPLUGIN_MINIMUM_PHP_VERSION', '7.4' );
define( 'MYPLUGIN_PLUGIN_DIR', plugin_dir_path( __FILE__ ) );
```

```php
// my-plugin.php
// In windows system (local development)
var_dump( __FILE__ );
// "....\wp-content\plugins\my-plugin\my-plugin.php"

echo '<br>';
var_dump( plugin_dir_path( __FILE__ ) );
// "....\wp-content\plugins\my-plugin/"

echo '<br>';
var_dump( dirname( __FILE__ ) );
// "....\wp-content\plugins\my-plugin"
```

for more info: [Determining Plugin and Content Directories « WordPress Codex](https://codex.wordpress.org/Determining_Plugin_and_Content_Directories)

<br>
<br>

# index.php
```php
<?php
// Silence is golden
```
