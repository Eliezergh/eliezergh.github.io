+++
title = 'How-To - Modify Wordpress roles to allow see private posts'
date = 2024-03-28T21:42:44Z
draft = false
+++

Recently I've been working on a small project which uses wordpress to serve a static website. 

The website, have some pages with a lot of information and now I need to take advatange of the wordpress blog functionality. 

The main topic is that I need that blog to be private, this mean that only logged in users should be able to see the "Posts" section.

By default, Wordpress allow private posts/pages to be seen just by Administrator & Editor roles but I need this also for Subscriber & Contributor roles. 

In order to achieve that functionality, I've added the following code to **functions.php** file:
```
//Allow work with private pages
$subRole = get_role( 'subscriber' );
    $subRole->add_cap( 'read_private_posts' );
$subRole = get_role( 'contributor' );
    $subRole->add_cap( 'read_private_posts' );

// Redirect subscribers to home page on login
function loginRedirect( $redirect_to, $request_redirect_to, $user ) {
    if ( is_a( $user, 'WP_User' ) && $user->has_cap( 'edit_posts' )
    === false ) {
        return get_bloginfo( 'siteurl' );
    }
    return $redirect_to; 
}
add_filter( 'login_redirect', 'loginRedirect', 10, 3 );
```
Now both Subscriber & Contributor roles will be able to see pages and posts tagged as "Private". 

Also, as I need a completely private blog section, I need a private page to be used on main wordpress menu.

By default, Wordpress doesn't show private pages on menu pages selector so the following code has been added to **functions.php** file to show private pages:
```
function steele_show_private_pages_menu_selection( $args ){
    if( $args->name == 'page' ) {
        $args->_default_query['post_status'] = array('publish','private');
    }
    return $args;
}
add_filter( 'nav_menu_meta_box_object','steele_show_private_pages_menu_selection', 9999 );
```

Now you should have available private pages on menu selector.

Hope this helps anyone to configure a Wordpress blog using private posts and pages.