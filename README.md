## MAMP - Precompiled Extensions for OSX
Are you having issues while compiling extension for MAMP of OSX so here you can find some precompiled extensions so you do not have compile and juggling with lots of compilation errors.

## Extensions compiled
* php7.3.9 - pcntl.so
* php7.4.2 - pcntl.so
* php7.4.2 - mongodb.so

## How to Install compiled extension
1. Create phpinfo.php file <?php phpinfo(); ?> in your localhost and run http://localhost/phpinfo.php
2. Check your php.ini file path from the above url
3. Open the php.in file and your extensio like this `extension=pcntl.so`
4. Restart your server
5. Refersh http://localhost/phpinfo.php and your extension should visible now.

### INSTALL PCNTL (INTL) EXTENSION
* download php from http://www.php.net/releases/
* tar -xzvf php-7.2.1.tar.gz
* cd php-7.2.1/ext/pcntl
* /Applications/MAMP/bin/php/php7.2.1/bin/phpize
* ./configure --prefix=/Applications/MAMP/bin/php/php7.2.1/bin/php
* make && make install
* Then the terminal will shows `Installing shared extensions: /Applications/MAMP/bin/php/php7.2.1/lib/php/extensions/no-debug-non-zts-20170718/`
* Open MAMP PRO menu->File ->Edit Template->PHP->7.2.1 add below line at the end of the php.ini file `extension=pcntl.so`
* Run the command `php --ri pcntl`
 and it will show message `pcntl support => enabled`

## How to set the php cli version same as MAMP Pro
Most of the times MAMP Pro set same php version in the command line does not work so you can set manually the php version
1. Edit yoru ~/.bash_profile
2. Paste this code `export PATH=/Applications/MAMP/bin/php/php7.4.2/bin:$PATH`
3. Save the file and Run this command `source ~/.bash_profile`
4. Check your php version now using command `php -v`

## Change PHHP command line to load the same config as MAMP PRO
Mamp uses different php config files for cli and mamp pro.
NOTE: This is not required anymore for new MAMP Versions
```
ln -s "/Library/Application Support/appsolute/MAMP PRO/conf/php7.3.8.ini" "/Applications/MAMP/bin/php/php7.3.8/conf/php.ini"
```

## CHECK LOADED CONFIGURATION
```
php --ini
```

## If php command line does not shows extension
* php command line was not showing the pcntl extenion because it was loading the different ini file so moved the loaded ini file to .bak and symlinked the MAMP PRO ini file to the loaded file path of php command line
