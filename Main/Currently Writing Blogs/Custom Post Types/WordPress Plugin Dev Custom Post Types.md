# What is 'Post Types'
As we know, WordPress is a Content Management System(CMS). There are different types of content on a website, such as blogs, news reports, product pages, recipes, etc. These contents are referred to as 'Post Types' in WordPress.
All of the Post Types are stored in the same place — in the `wp_posts` database table — but are differentiated by a database column called `post_type`. You can also create Custom Post Types.
In classic theme, the content of a post type is rendered by `Template files`. The perpose of Template file is to display content in certain way in the fornt end. The perpose of post type is to categorize what type of content you are dealing with. In a e-commerce site, products are the content. So you will need a template file which will properly render product page of that website.

# Default Post Type
There are several default Post Types readily available to users or internally used by the WordPress installation. The most common are:
-   Post (Post Type: ‘post’)
-   Page (Post Type: ‘page’)
-   Attachment (Post Type: ‘attachment’)
-   Revision (Post Type: ‘revision’)
-   Navigation menu (Post Type: ‘nav_menu_item’)
-   Block templates (Post Type: ‘wp_template’)
-   Template parts (Post Type: ‘wp_template_part’)