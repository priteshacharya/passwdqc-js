# Passwdqc-js
=============

## About

Passwdqc-js is a JavaScript port of [passwdqc](http://openwall.com/passwdqc/), the brilliant password quality checker library, made by [Parallels](https://www.parallels.com/). Passwdqc-js supports AMD and NodeJS/CommonJS module format. So it runs on both client and server.

## Compatibilty w/ Passwdqc

Passwdqc-js was tested for compatibility with original passwdqc. We used following password databases in order to guarantee that both accept the **same** subset of passwords:

* 14M unique RockYou passwords from 2009 leak
* 10K random 10-character symbolic passwords
* 10K random pass phrases, generated by pwqgen (part of original passwdqc)

## Usage
Use `passwdqc.check(newpass, [oldpass], [login], [gecos])` function to check password quality.

**Parameters**

* **newpass**: password to check
* **oldpass**: old password to check if new password is based on it
* **login**: user's login name to check that password is not based on it  
* **gecos**: any other personal information to check
* **params**: custom parameters for passwdqc algorithm, [see](http://www.openwall.com/passwdqc/README.shtml)

**Return value**

* Empty string if password is considered good;
* The reason why password is considered weak, otherwise.

### Example

	var passwdqc = require('passwdqc');

	var rv = passwdqc.check(password, old_password);

	if (!rv) {
		// Password is of good quality
		// ...
	} else {
		// The "rv" now contains reason why password considered weak
	}

## TODO
* More examples
* Reference implementation for password meter with visual feedback
* Random password/passphrase generator