Twitter Bootstrap- Modular Compass
================================

Bootstrap is a toolkit from Twitter designed to kickstart development of webapps and sites.
It includes base CSS and HTML for typography, forms, buttons, tables, grids, navigation, and more.: <http://twitter.github.com/bootstrap/>

* This code is consistent with 2.2.2 version of Bootstrap  
------------------------------------------------------------

This plugin adds the Bootstrap to [Compass](http://compass-style.org/).

## Changing the theme color:
-----------------------------

Create your _preboot.sccs and you will see the entire list of colors, you can change those in order to apply your own color scheme

    // VARIABLES
    // ---------

    // / Links
    $linkColor:         #0069d6;
    $linkColorHover:    darken($linkColor, 10);

    // Grays
    $black:             #000;
    $grayDark:          lighten($black, 25%);
    $gray:              lighten($black, 50%);
    $grayLight:         lighten($black, 75%);
    $grayLighter:       lighten($black, 90%);
    $white:             #fff;

    // Accent Colors
    $blue:              #049CDB;
    $blueDark:          #0064CD;
    $green:             #46a546;
    $red:               #9d261d;
    $yellow:            #ffc40d;
    $orange:            #f89406;
    $pink:              #c3325f;
    $purple:            #7a43b6;

    // Baseline grid
    $baseFontSize:          13px;
    $baseLineHeight:          18px;

    // Griditude
    $gridColumns:       16;
    $gridColumnWidth:   40px;
    $gridGutterWidth:   20px;
    $extraSpace:        ($gridGutterWidth * 2); // For our grid calculations
    $siteWidth:         ($gridColumns * $gridColumnWidth) + ($gridGutterWidth * ($gridColumns - 1));

## Importing certain modules
-----------------------------
All modules are mixin separated, including individula files will not output any CSS code. In order to include components in your main scss file, import

    @import "modules/modules";


Then you can include all modules on by one. Here is an example of module inclusion. Please keep in mind that the order matters

    // CSS Reset
    @include reset();

    // Grid system and page structure
    @include scaffolding();
    @include gridSystem(responsive);
    @include layouts(responsive);

    // Base CSS
    @include typography(true, true, true);
    @include codes();
    @include forms();
    @include tables();

    // Components: common
    @include iconography();
    @include dropdowns();
    @include wells();
    @include component-anims();
    @include close();

    // Components: Buttons & Alerts
    @include buttons();
    @include bootstrap-alternate-buttons();
    /**
    * Declare own button names
      @include alternate-buttons(primary, $primaryButtonBackground, adjust-hue($primaryButtonBackground, 20));
      @include alternate-buttons(secondary, lighten($orange, 15%), $orange);
    */
    @include button-groups();
    @include alerts();

    // Components: Nav
    @include navigation();
    @include navigationbar();
    @include breadcrumbs();
    @include pagination();
    @include pager();

    // Components: Popovers
    @include modals();
    @include tooltips();
    @include popovers();

    // Components: Misc
    @include thumbnails();
    @include labels();
    @include progress-bars();
    @include accordions();
    @include carousels();
    @include hero-units();

    // Utility classes
    @include utility-classes();



    /*Different breakpoints can be generated.
    * These mixins mimic twitter bootstrap functionality*/

    // RESPONSIVE CLASSES
    // ------------------
    @include responsive-utilities();


    // MEDIA QUERIES
    // ------------------

    // Large desktops
    @include responsive1200-max();

    // Tablets to regular desktops
    @include responsive768-979();.

    // Phones to portrait tablets and narrow desktops
    @include responsive();


    // RESPONSIVE NAVBAR
    // ------------------

    // From 979px and below, show a button to toggle navbar contents
    @include responsive-navbar();




## Extending bootstrap
-----------------------------

There are mixins provided to extend the semantics of bootstrap.

### Buttons
You can declare your own button names with the following mixin:

    alternate-buttons($name, $primaryBgr, $alternateBgr, $textColor, $activeColor)

All bootstrap buttons are declared via the same mixin. Here is how it is done:

    @include alternate-buttons(danger, #ee5f5b, #bd362f);
    @include alternate-buttons(success, #62c462, #51a351);
    @include alternate-buttons(info, #5bc0de, #2f96b4);

### Progress bars
You can declare your own progress bars with the following mixin:
    
    colored-progress-bars($name, $color1, $color2)

$color1 and $color2 are linear gradient components

Examples:  

    @include colored-progress-bars(danger, #ee5f5b, #c43c35);
    @include colored-progress-bars(success, #62c462, #57a957);
    @include colored-progress-bars(info, #5bc0de, #339bb9);    
