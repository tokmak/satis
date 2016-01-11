## Install composer

```
cd ~
mkdir composer
cd composer
curl -sS https://getcomposer.org/installer | php
```
## Composer can be executed by doing:

```
php ~/composer/composer.phar
```
add the following to ~/.bash_profile to make your life easier: 

```
alias composer="php ~/composer/composer.phar"
```

## Installing local composer server

```
mkdir -p ~/digital-spin
cd ~/digital-spin
git clone https://github.com/tokmak/satis
```

## Install Composer dependencies

```
cd ~/digital-spin/satis
composer install
```

## Create new vhost (depend on your local setup): 
```
"http://local-composer" with root directory: ~/digital-spin/satis
```

## Add magic function to ~/,bash_profile:

```
function satis() {
    start_time=`date +%s`
    cd ~/digital-spin/satis/
    rm -r web
    bin/satis build config.json web -v
}
```

~/digital-spin/satis/config.json holds all the private packages, you can add new by adding new element, see the file for example...