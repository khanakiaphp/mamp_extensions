## MAMP - Precompiled Extensions for OSX

## Extensions compiled
* php7.3.9 - pcntl.so
* php7.4.2 - pcntl.so
* php7.4.2 - mongodb.so

### INSTALL PCNTL (INTL) EXTENSION =====================
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

## CHANGE PHP COMMAND LINE TO load the same config as MAMP PRO
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
