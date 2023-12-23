
# How To Make Country Wise Website Redirect- on Same Domain

Please Flow this Step


## Used By

Country Wise Website Using PHP | Hello everyone ,welcome to another fresh article ,in this article I will teach you how to make a simple country wise website on php, for example, visitor visit your website in Bangladesh, so it’s automatic redirect to Bangladesh version like domian.com/hi and if visitor visit your website outside of Bangladesh like in us and another country so it automatically redirects to root domain or domian.com/en.

it’s a very simple process, here is simple code, you can use in your index file, just copy and paste below code in your website index file it’s automatic worked, on Bangladesh and us ,also you can modify this code as per your choice ,mean’s you can add more country on switch case.

- Login To Cpanel
- Find [index.php] File
- Edit index.php File 






## Examples

```php
<?php

define( 'WP_USE_THEMES', true );
require __DIR__ . '/wp-blog-header.php';
```


## Step 1 Examples

```php
<?php

  $user_ip = getenv('REMOTE_ADDR');
  $geo = unserialize(file_get_contents("http://www.geoplugin.net/php.gp?ip=$user_ip"));
  $country = $geo["geoplugin_countryName"];

  switch ($country) {
    case "Bangladesh":
        header('Location:http://domain.com/hi');
        break;
    default:
    define( 'WP_USE_THEMES', true );
    require __DIR__ . '/wp-blog-header.php';
```

## Step 2 Examples

```php
<?php

  $user_ip = getenv('REMOTE_ADDR');
  $geo = unserialize(file_get_contents("http://www.geoplugin.net/php.gp?ip=$user_ip"));
  $country = $geo["geoplugin_countryName"];

  switch ($country) {
    case "Bangladesh":
    define( 'WP_USE_THEMES', true );
    require __DIR__ . '/wp-blog-header.php';
        break;
    default:
    header('Location:http://domain.com/');
```
## Exjample More Code


```php
<?php

  $user_ip = getenv('REMOTE_ADDR');
  $geo = unserialize(file_get_contents("http://www.geoplugin.net/php.gp?ip=$user_ip"));
  $country = $geo["geoplugin_countryName"];

  switch ($country) {
    case "India":
        header('Location:http://domain.com/hi');
        break;
    case "United States":
        header('Location:http://domain.com/en');
        break;
    default:   
        header('Location:http://domain.com');  
  }

?>
```
Reference Link : https://youtu.be/qn1jVQ27EIg

