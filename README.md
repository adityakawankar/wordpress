# wordpress
Wordpress Repository
// Use shortcode in a PHP file 
echo do_shortcode( '' );
// Use shortcodes in form like Landing Page Template.
echo do_shortcode( '[contact-form-7 id="91" title="quote"]' );
// Store the short code in a variable.
$var = do_shortcode( '' );
echo $var;
 
Function: Load footer template.
get_footer();
get_header();
 
 
<?php
if ( is_home() ) :
    get_footer( 'home' );
elseif ( is_404() ) :
    get_footer( '404' );
else :
    get_footer();
endif;
?>




// To Display the post title 
<?php the_title(); ?>

// To Display the post thumbnail
<?php if ( has_post_thumbnail() && ! post_password_required() ) : ?> // It’s Condition for if Feature image is available 
     <?php the_post_thumbnail(); ?>                
<?php endif; ?>

// If you want to get excerpt short content up to limit 400 words which is added in content area
<?php $content = get_the_excerpt(); echo mb_strimwidth($content, 0, 400, '...');?>

// If you want to get content short content up to limit 400 words which is added in content area
<?php $content = get_the_content(); echo mb_strimwidth($content, 0, 400, '...');?>

// If you want to display excerpt content which is added in excerpt textarea
<?php echo the_excerpt(); ?>

// If you want to display full content with proper HTML Format 
<?php echo the_content(); ?>

/* How To Print Theme Url Using short code  */
<?php echo cb_theme_url('/') ?>

/* Echo the the site name ot title for logo */
<?php echo esc_attr(get_bloginfo('name', 'display')); ?>

/* How to print the menu and add class to menu bar */
<?php wp_nav_menu( array( 'theme_location' => 'primary', 'menu_class' => 'nav-menu nav navbar-nav' ) ); ?>
