### A simple CPT

```php
<?php
/**
 * Plugin Name: Custom Post Type
 */

add_action( 'init', 'register_cpt' );
function register_cpt() {
    
    /* Set up the arguments for the post type. */
    $args = array(
        /**
         * labels (string[])
         * An array consist of name and label of menu, page, section, and differnet options
         * of post type.
         */
        'labels'              => array(
            'name'                  => __( 'Custom Posts', 'cpt' ),
            'singular_name'         => __( 'Custom Post', 'cpt' ),
            'add_new'               => __( 'Add New', 'cpt' ),
            'add_new_item'          => __( 'Add new Custom Post', 'cpt' ),
            'edit_item'             => __( 'Edit Custom Post', 'cpt' ),
            'new_item'              => __( 'New Custom Post', 'cpt' ),
            'view_item'             => __( 'View Custom Post', 'cpt' ),
            'view_items'            => __( 'View Custom Posts', 'cpt' ),
            'search_items'          => __( 'Search Custom Posts', 'cpt' ),
            'not_found'             => __( 'No Custom Posts found', 'cpt' ),
            'not_found_in_trash'    => __( 'No Custom Posts found in trash', 'cpt' ),
            'all_items'             => __( 'All Custom Posts', 'cpt' ),
            'insert_into_item'      => __( 'Insert into Custom Post', 'cpt' ),
            'uploaded_to_this_item' => __( 'Uploaded to this Custom Post', 'cpt' ),
            'featured_image'        => __( 'Custom Post image', 'cpt' ),
            'set_featured_image'    => __( 'Set Custom Post image', 'cpt' ),
            'remove_featured_image' => __( 'Remove Custom Post image', 'cpt' ),
            'use_featured_image'    => __( 'Use as Custom Post image', 'cpt' ),
            'menu_name'             => _x( 'Custom Posts', 'Admin menu name', 'cpt' ),
            'filter_items_list'     => __( 'Filter Custom Posts', 'cpt' ),
            'items_list_navigation' => __( 'Custom Posts navigation', 'cpt' ),
            'items_list'            => __( 'Custom Posts list', 'cpt' ),
            'item_link'             => __( 'Custom Post Link', 'cpt' ),
            'item_link_description' => __( 'A link to a Custom Post.', 'cpt' ),
        ),

        /**
         * description (string) Default: blank
         * A short descriptive summary of the post type.
         */
        'description'         => __( 'This is where you can browse Custom Posts.', 'cpt' ),

        /**
         * 'public' (boolean) Default: false
         * Controls visibility of the post type.
         * true  - shows custom post menu in admin menu
         * false - custom post menu does not appear in admin menu
         */
        'public'              => true,

        /**
         * 'exclude_from_search' (bool) Default: opposite of public
         * Whether to exclude from front end search results.
         * true  - search result will not include posts of this post type
         * false - search result will include posts of this post type
         */
        'exclude_from_search' => false,

        /**
         * 'publicly_queryable' (bool) Default: same as public
         * Whether queries can be performed on the front end.
         * true  - archive page and single post page exist and shows content
         * false - archive page and single post page doesn't exist
         */
        'publicly_queryable'  => true,

        /**
         * 'show_ui' (bool) Default: same is public
         * Whether to generate an admin menu and edit.php?post_type=custom-post page
         * for managing this post type in the admin.
         * true  - create admin menu and edit.php?post_type=custom-post page
         * false - no UI
         * Note: frontend is not affected.
         */
        'show_ui'             => true,

        /**
         * 'show_in_nav_menus' (bool) Default: same as public
         * Whether post_type is available for selection in navigation menus.
         * ture  - post is selectable from navigation menu.
         * false - post is not selectable from navigation menu.
         */
        'show_in_nav_menus'   => true,

        /**
         * 'show_in_menu' (bool|string) Default: same as show_ui
         * Where to show the post type in the admin menu. show_ui must be true.
         * true   - creates a top level admin menu to display the post type
         * false  - no menu for the post type. But edit.php?post_type=custom-post
         *          is accessible
         * string - top level page. For example tools.php or edit.php?post_type=page
         */
        'show_in_menu'        => true,

        /**
         * 'show_in_admin_bar' (bool) Default: same as show_in_menu
         * Whether to make this post type available in the WordPress admin bar.
         */
        'show_in_admin_bar'   => true,

        /**
         * 'menu_position' (int) Default: null - below Comments
         * The position in the menu order the post type should appear.
         * show_in_menu must be true.
         * 5 – below Posts
         * 10 – below Media
         * 15 – below Links
         * 20 – below Pages
         * 25 – below comments
         * 60 – below first separator
         * 65 – below Plugins
         * 70 – below Users
         * 75 – below Tools
         * 80 – below Settings
         * 100 – below second separator
         */
        'menu_position'       => 7,

        /**
         * 'menu_icon' (string) Default: null - post icon
         * The url to the icon
         * Example: 1. dashicons - 'dashicons-format-video'
         *          2. use image in from current path
         *          3. use <svg> tag directly inside base64_encode() for icon
         */
        'menu_icon'           => 'data:image/svg+xml;base64,' . base64_encode('<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 1792 1792"><path fill="black" d="M1596 380q28 28 48 76t20 88v1152q0 40-28 68t-68 28h-1344q-40 0-68-28t-28-68v-1600q0-40 28-68t68-28h896q40 0 88 20t76 48zm-444-244v376h376q-10-29-22-41l-313-313q-12-12-41-22zm384 1528v-1024h-416q-40 0-68-28t-28-68v-416h-768v1536h1280zm-640-896q52 0 90 38t38 90v384q0 52-38 90t-90 38h-384q-52 0-90-38t-38-90v-384q0-52 38-90t90-38h384zm492 2q20 8 20 30v576q0 22-20 30-8 2-12 2-14 0-23-9l-265-266v-90l265-266q9-9 23-9 4 0 12 2z"/></svg>'),

        /**
         * 'capability_type' (bool|string) Default: 'post'
         * The string to use to build the read, edit, and delete capabilities.
         */
        'capability_type'     => 'post',

        /**
         * 'map_meta_cap' (bool) Default: null
         * Whether to use the internal default meta capability handling.
         * Note: If set it to false then standard admin role can’t edit the posts types.
         */
        'map_meta_cap'        => true,

        /**
         * 'hierarchical' (bool) Default: false
         * Whether the post type can form parent-child relationship.
         * if 'true', 'page-attributes' should be added in supports
         */
        'hierarchical'        => false,

        /**
         * 'supports' (array|bool) Default: array( 'title', 'editor' )
         * Post types have some feature that can be tured on and off. These features are known
         * as supports. There are 11 features in total as of May 2022.
         * ‘title’
         * ‘editor’ (gutenberg) - if you want classic editor, exclude this feature
         * ‘author’
         * ‘thumbnail’ (featured image, current theme must also support post-thumbnails)
         * ‘excerpt’
         * ‘trackbacks’
         * ‘custom-fields’
         * ‘comments’ (also will see comment count balloon on edit screen)
         * ‘revisions’ (will store revisions)
         * ‘page-attributes’ (menu order, hierarchical must be true to show Parent option)
         * ‘post-formats’
         */
        'supports'            => array( 'title', 'editor', 'thumbnail', 'page-attributes' ),

        /**
         * 'has_archive' (bool|string) Default: false
         * Enables post type archives.
         * true   - there will be an archive page (ex: cpt.test/custom-post) listing all post
         *          and archive slug will be same as post type key.
         * false  - no archive page (ex: cpt.test/custom-post)
         * string - archive page will be cpt.test/cpt
         */
        'has_archive'         => true,

        /**
         * 'rewrite' (bool|array) Default: true
         * Handles and changes rewrite rules for archive page and post page.
         * ture  - rewrite rules. Archive page will be cpt.test/cpt
         * false - does not rewrite. Archive page will be cpt.test/?post_type=custom-post
         * array - for specific rewrite rules. 'has_archive' has to be true
         * 'slug'       (string) custom parmalink structure slug. Default: post type key.
         * 'with_front' (bool)   should the permalink structure be prepended with
         *                       the front base. Default: true
         * 'feeds'      (bool)   should a feed permalink structure be built for this
         *                       post type. Default: same as 'has_archive'
         * 'pages'      (bool)   should the permalink structure provide for pagination.
         *                       Default: true
         * 'ep_mask'    (int)    add endpoint. Default: EP_PERMALINK
         */
        'rewrite'             => array(
            'slug'          => 'movie',
            'with_front'    => false,
            'feeds'         => true,
            'pages'         => true,
            'ep_mask'       => EP_PERMALINK,
        ),

        /**
         * 'query_var' (bool|string) Default: true
         * Sets the query_var key for this post type. 'publicly_queryable' has to be true.
         * ture   - set to post type key
         * false  - Disables query_var key use.
         * string - custom query_var_string (anime). Ex: cpt.test/?anime=hello-post
         */
        'query_var'           => 'anime',

        /**
         * 'show_in_rest' (bool) Default: false
         * Whether to expose this post type in the REST API.
         * Must be true to enable the Gutenberg editor.
         */
        'show_in_rest'        => true,

        /**
         * 'rest_base' (string) Default: post type key
         * Change post type slug of REST API.
         */
        'rest_base'           => 'cpt',

        /**
         * 'rest_namespace' (string) Default: 'wp/v2'
         * Change post type namespace URL of REST API.
         * Example - http://cpt.test/wp-json/v2/cpt/
         * Note: Default URL is http://test.test/wp-json/wp/v2/custom-post/
         */
        'rest_namespace'      => 'v2',

        /**
         * 'template' (array) Default: null
         * Blocks to use as the default initial state for an editor session.
         */
        'template'            => array(
            array( 'core/cover' ),
            array( 'core/button' ),
        ),

        /**
         * 'template_lock' (bool|array) Default: false
         * Whether the block template should be locked.
         * true     - the user is able to move, but unable to insert and delete block
         * false    - not locked
         * 'all'    - the user is unable to insert, move and delete block
         * 'insert' - the user is able to move, but unable to insert and delete block
         */
        'template_lock'       => 'insert',
    );

    /**
     * Registers a post type.
     * 
     * @param string        $post_type  Post type key.
     * @param string|array  $args       Arguments for registering a post type.
     */
    register_post_type( 'custom-post', $args );

    /**
     * Remove rewrite rules and then recreate rewrite rules.
     */
    flush_rewrite_rules();
}
```