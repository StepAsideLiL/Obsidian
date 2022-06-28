# What is Plugin Header Comment
In WordPress plugin development, a header comment is a comment in the root PHP file. It has a specific format that WordPress can read. The comment contains metadata about the plugin. Without this comment, WordPress can not recognize the file as a plugin.
<br>
In the previous tutorial, we saw the minimum requirement for registering a plugin. That was a header comment containing the name of the plugin.
<br>
In this tutorial, we will see what a header comment should consist of.

<br>
# Writing a Plugin with only Header Comment
The code below in also hosted on [github](https://github.com/StepAsideLiL/wp-plugin-dev)
```php
<?php
/**
 * Plugin Name:       My Plugin Header
 * Plugin URI:        https://github.com/StepAsideLiL/wp-plugin-dev
 * Description:       This plugin shows the metadata of a plugin header comment.
 * Version:           1.0.0
 * Requires at least: 5.2
 * Requires PHP:      7.2
 * Author:            Rifat Khan
 * Author URI:        https://stepasidelil.hashnode.dev/
 * License:           GPL v2 or later
 * License URI:       https://www.gnu.org/licenses/gpl-2.0.html
 * Update URI:        https://github.com/StepAsideLiL/wp-plugin-dev/tree/main/my-plugin-header
 * Text Domain:       my-plugin-header
 * Domain Path:       /languages
 */
```

![my-plugin-header.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1651835609725/fHxw2wJ1g.png align="left")
### Description of Header Field
- **Plugin Name** is the most important plugin header field. WordPress looks up this header field to register the plugin on the *Plugins* page.
- **Plugin URI** is a unique URL of the plugin. This can not be wordpress.org
- **Description** is a short note about the plugin.
- **Version** number represents the current version of the plugin. This number should be updated when you update your plugin.
- **Requires at least** is the lowest version of WordPress that can run your plugin.
- **Requires PHP** is the lowest version of PHP that can run your plugin.
- **Author** is the name of the writer of this plugin.
- **Author URI** is the author's website.
- **License** is the name of the software license. It is a document that provides legally binding guidelines for the use and distribution of software. WordPress plugin must be compatible with the GNU General Public License.
- **License URI** is the link to the license document.
- **Update URI** is the website link of your plugin. If your plugin is hosted on wordpress.org then you don't need to use this header field. Read more about it from [here](https://make.wordpress.org/core/2021/06/29/introducing-update-uri-plugin-header-in-wordpress-5-8/)
- **Text Domain** is a unique identifier to ensure WordPress can distinguish between all loaded translations. Read more about it from [here](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#text-domains)
- **Domain Path** is the path that lets WordPress know where to find the translations. Read more about it from [here](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#domain-path)
<br>
### You can read about details description of each metadata from [here](https://developer.wordpress.org/plugins/plugin-basics/header-requirements/#header-fields)