# What is WordPress Plugin
A WordPress plugin is a small application that extends the features and functions of a WordPress site. It is made up of PHP code and includes other files such as images, CSS, and JavaScript. Plugins are what make WordPress so great. There is a plugin for everything.
<br>
WordPress is designed to extend by other developers. The WordPress plugin API offers lots of hooks and filters. Developers can modify existing functionality or add a new one using this API.
<br>
WordPress plugin can be a simple plugin like Hello Dolly or a complex ecommerce plugin like WooCommerce.
![wp-plugin.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1651333522889/El7OpPh9U.png align="left")

<br>
<br>
# Prerequisites for this Tutorial
If you want to follow this series, you need to have some knowledge of ***PHP, HTML, CSS, and JavaScript***.

<br>
<br>
# Writing a plugin
To make a plugin here is what you need to do.
- Go to the plugins directory of your site (`yoursite.com/wp-content/plugins`).
- Create a folder called `my-plugin`.
- In the `my-plugin` folder, create a `my-plugin.php` file. The name of the folder and file has to be the same. And `my-plugin.php` is the entry point of your plugin.
- Open the `my-plugin.php` file and write the code below
```php
<?php
/**
 * Plugin Name: My Plugin
 */
```

Now, if you go to the plugin menu of your site, you will see the `My Plugin` plugin.
![wp-my-plugin.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1651333402196/UomSWSAdr.png align="left")

That is all you need to do to list your plugin in the Plugins menu.