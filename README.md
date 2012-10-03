# About

An extension of the [CakePHP's EmailComponent](http://book.cakephp.org/1.3/en/view/1283/Email) using SwiftMailer as sending engine.

You can use swiftmailer as easily as CakePHP's Email Component =)


## Install

First [you will need to download SwiftMailer](http://swiftmailer.org/download) if you have not downloaded it yet.

Decompress the folder "lib" inside your app/vendors folder and then change its name to "swiftmailer".

Copy the swift_mailer.php file to app/controllers/components and then load the component as normally loaded. Check out [the official documentation for more details](http://book.cakephp.org/1.3/en/view/1284/Class-Attributes-and-Variables).

Here you have how shoud it be:

	/app/vendors/swiftmailer
	/app/vendors/swiftmailer/classes/*
	/app/vendors/swiftmailer/dependency_maps/*
	/app/vendors/swiftmailer/mime_types.php
	/app/vendors/swiftmailer/preferences.php
	/app/vendors/swiftmailer/swift_init.php
	/app/vendors/swiftmailer/swift_required.php
	/app/vendors/swiftmailer/swift_required_pear.php

	/app/controllers/components/swift_mailer.php

Now, if you were using default's CakePHP component you will need to change all your `$this->Email->` to `$this->SwiftMailer->` and everything else should work as using the default EmailComponent.

Otherwise, configure the component as specified in CakePHP's EmailComponent documentation and create your templates/views.

Don't forget to configure the sendtype options (`$this->SwiftMailer->smtpOptions` if necessary).

## Changes from original EmailComponent

As I said, this component tries to use the default CakePHP's EmailComponent logic. There are only a few things you maybe would know:

* There are three public methods that doesn't exist in the original component: `addTo`, `addCc` and `addBcc`, This methods work the same way they do in SwiftMailer.
* If you want to use SSL/TLS connections over SMTP you can do it by two ways: setting it as `sslsmtp` or `tlssmtp` in the `delivery` option or you can also use `smtp` as delivery method and then specify `ssl` or `tls` for encryption value.

## LICENSE

```
This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
```
