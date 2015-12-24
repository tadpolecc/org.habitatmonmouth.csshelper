#CSS Helper for CiviCRM and WordPress
Tadpole's CiviCRM css override that allows the theme to control the CSS on frontend CiviCRM pages.
This includes a templates directory to override selectors where they are lacking.

This extension replaces the core civicrm css file with it's own.

This extension supports 4.6

Version 1.2 is based on the civicrm.css from the 4.6 release


#Overrides
You can now replace this extension's CSS file  with a custom one from your theme.  This makes use of the tc_civicss_override filter.  Add the below function to your theme's functions.php or add a your own plugin to do this.   You will need to have the images directory /i  available at the same level as your civicrm.css file to show credit card icons and other images.

Example Code:


    function tc_civicrm_theme_css( ) {
        $tc_css = get_bloginfo( 'stylesheet_directory' ) .'/includes/css/civicrm.css';

        return $tc_css;
    }

    add_filter( 'tc_civicss_override', 'tc_civicrm_theme_css' ); 
You can also just add additional css in yout theme. Add the below function to your theme's functions.php or add a your own plugin to do this.   You will need to have the images directory /i  available at the same level as your civicrm.css file to show credit card icons and other images.

Example Code:


    function tc_civicrm_theme_css( ) {
    	wp_enqueue_style( 'tc_civi_style', get_template_directory_uri() . '/civicrm/civicrm.css' );
    
    }
    
    add_action( 'wp_print_styles', 'tc_civicrm_theme_css', 199 ); 