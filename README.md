# QR Code Generator Bundle for Laravel

This bundle will allow you to easily generate QR code images. The draw function echos out an html image tag; however, this bundle can easily be manipulated to fit your app needs.

## Installation

To install the bundle, run the following command

```PHP
php artisan bundle:install qr
```

Next, we will tell the application to auto load the bundle. In your application/bundles.php file add the following line to the array

```PHP
'qr' => array('auto' => true),
```

Or, if we set 'auto' to `false`, we could manually start the bundle wherever we needed to use it by adding the following line:

```PHP
Bundle::start('qr');
```

## Example usage

If we were to add the following route to our application:

```PHP
Route::get('generate', function(){

	$qr = new QR();
	$qr->url("www.laravel.com");
	$qr->draw();

});
```

Now, by going to our APP_NAME/bundle/ URL you will see a new QR Code generated on the screen. Simply use a QR code scanner and you will see that the QR code redirects to our specified URL


## OPTIONS

You can use all the following options to generate a QR code that fits your needs:

```PHP
// bookmark 
$qr->boomark("title", "url"); 

// contact 
$qr->contact("name", "address", "phone", "email"); 

// content 
$qr->content("type", "size", "content"); 

// email 
$qr->email("email", "subject", "message"); 

// geo location 
$qr->geo("lat", "lon", "height"); 

// phone 
$qr->phone("phone"); 

// sms 
$qr->sms("phone", "text"); 

// text 
$qr->text("text"); 

// URL 
$qr->url("url"); 

// wifi connection 
$qr->wifi("type", "ssid", "password");
```

## Credits

This file has been updated and manipulated to work with the new Google API and put into a Laravel Bundle. The original outdated version was created by a (shayanderson)[http://www.shayanderson.com/php/php-qr-code-generator-class.htm]

