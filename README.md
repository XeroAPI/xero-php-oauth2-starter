# xero-php-oauth2-starter

This is a starter app with the code to perform OAuth 2.0 authentication

You'll be able to connect to a Xero Organisation and make real API calls - we recommend you connect to the Demo company.

## Getting Started
To run locally, you'll need a local web server with PHP support.  
* MAMP is a good option [Download MAMP](https://www.mamp.info/en/downloads/) 

### Download this code
* Clone this repo into your local server webroot. i.e. `htdocs`
* Launch a terminal app and change to the newly cloned folder `xero-php-oauth2-app`
* Download dependencies with Composer using the folloing comman

```
composer install
```

## Create a Xero App
To obtain your API keys, follow these steps and create a Xero app

* Create a [free Xero user account](https://www.xero.com/us/signup/api/) (if you don't have one)
* Login to [Xero developer center](https://developer.xero.com/myapps)
* Click "New App" link
* Enter your App name, company url, privacy policy url.
* Enter the redirect URI (your callback url - i.e. `http://localhost:8888/xero-php-oauth2-app/callback.php`)
* Agree to terms and condition and click "Create App".
* Click "Generate a secret" button.
* Copy your client id and client secret and save for use later.
* Click the "Save" button. You secret is now hidden.

## Configure API keys
You'll need to update your code where ever there is a clientId, clientSecret or redirectUri

- authoirzation.php
- callback.php
- authorizedResource.php

Sample PHP code from authorization.php
```php

$provider = new \League\OAuth2\Client\Provider\GenericProvider([
	'clientId'                => '__YOUR_CLIENT_ID__',,   
	'clientSecret'            => "__YOUR_CLIENT_SECRET__",
	'redirectUri'             => "__YOUR_REDIRECT_URI__",
	'urlAuthorize'            => 'https://login.xero.com/identity/connect/authorize',
	'urlAccessToken'          => 'https://identity.xero.com/connect/token',
	'urlResourceOwnerDetails' => 'https://api.xero.com/api.xro/2.0/Organisation'
]);

```
## Take it for a spin
Launch your browser and navigate to http://localhost:8888/xero-php-oauth2-starter/ (or whatever the correct path is). 

- You should see a connect to xero link.
- Click the link, login to Xero (if you aren't already)
- Grant access to your user account and select the Demo company to connect to.
- Done - try out the different API calls

## License

This software is published under the [MIT License](http://en.wikipedia.org/wiki/MIT_License).

	Copyright (c) 2020 Xero Limited

	Permission is hereby granted, free of charge, to any person
	obtaining a copy of this software and associated documentation
	files (the "Software"), to deal in the Software without
	restriction, including without limitation the rights to use,
	copy, modify, merge, publish, distribute, sublicense, and/or sell
	copies of the Software, and to permit persons to whom the
	Software is furnished to do so, subject to the following
	conditions:

	The above copyright notice and this permission notice shall be
	included in all copies or substantial portions of the Software.

	THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
	EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES
	OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
	NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
	HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
	WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
	FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
	OTHER DEALINGS IN THE SOFTWARE.

