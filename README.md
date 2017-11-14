# UnitTesting WordPress theme and Plugins with PHPUnit #

This repository is a test base for setting up unit testing of wordpress theme and plugins. 

### Installation Requirements ### 

1. A development environment for WordPress application development, LAMP , WAMP,  MAMP, XAMPP all supported , But best results can be achieved with virtual machines eg. https://github.com/Varying-Vagrant-Vagrants/VVV
2. PHPUnit latest version installed. Please check this link for help https://phpunit.de/getting-started.html
3. A blank mysql database and database user 
4. Shell or Terminal access to execute command line tools.   
                    
### Setup and Integration ### 

1. Clone the current repository and place in the web server root directory of your development environment.
2. Copy wp-test-config-sample.php and create a file wp-test-config.php 
3. Update wp-test-config.php 

    define( 'WP_DEFAULT_THEME', ‘your-default-theme' );

    define( 'WP_DEFAULT_THEME_DIR', ‘your-wordpress-theme-directory-path' );

   Please provide the full path of the theme directory which is to be unit tested in WP_DEFAULT_THEME_DIR.
   
   Update the database details for testing , Never use your production database for testing , it will be wiped out. Please use a separate blank database for testing 

   define( 'DB_NAME', 'youremptytestdbnamehere' );

   define( 'DB_USER', 'yourusernamehere' );

   define( 'DB_PASSWORD', 'yourpasswordhere' );

   define( 'DB_HOST', 'localhost' );

   define( 'DB_CHARSET', 'utf8' );
   
   define( 'DB_COLLATE', '' );

   Update other details in wp-config-test.php if required.

4. Update phpunit.xml.dist 
            
    Update the file path to point out the directory with unit test cases placed for your plugin or theme

    <testsuite>
        <directory suffix=".php">tests/phpunit/tests</directory>
        ….

    update the path on above line , replacing "tests/phpunit/tests” with your test files. 

### Execute UnitTests ### 

    Go to the root of repository and execute “phpunit” to see the test results   
    e.g.  i-mac: wordpress-develop my-user$ phpunit 

### References ### 

https://phpunit.de/getting-started.html

https://make.wordpress.org/core/handbook/testing/automated-testing/phpunit/
