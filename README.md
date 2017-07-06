# Laravel Passport Facebook Login
Provides a new Laravel Passport Grant Client named `facebook_login`, allowing you to log a user in with just their Facebook Login token

Note: A new User **will be created** if an existing user was not found for the given token

## Installation:
Install with composer  `composer require danjdewhurst/laravel-passport-facebook-login`

### Versions:
* Laravel 5.4 and Passport 2.0 only supported at this time

## Setup:
* Add `Danjdewhurst\PassportFacebookLogin\FacebookLoginGrantProvider::class` to your list of providers **after** `Laravel\Passport\PassportServiceProvider`.
* Add `Danjdewhurst\PassportFacebookLogin\FacebookLoginTrait` Trait to your `User` model (or whatever model you have configured to work with Passport).
* Run `php artisan vendor:publish` and enter your Facebook App details in `config/facebook.php`.

## How To Use:

* Make a **POST** request to `https://your-site.com/oauth/token`, just like you would a **Password** or **Refresh** grant.
* The POST body should contain `grant_type` = `facebook_login` and `fb_token` = `{token from facebook login}`.
* An `access_token` and `refresh_token` will be returned if successful.

## Notes:
It is assumed that your `User` model has `name`, 'username', `email` and `password` fields.

## Credits:
* https://github.com/mirkco/Laravel-Passport-Facebook-Login
* https://github.com/mikemclin/passport-custom-request-grant
