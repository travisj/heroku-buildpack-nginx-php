Heroku Buildpack: Nginx + PHP
=============================

This is a [Heroku Buildpack](http://devcenter.heroku.com/articles/buildpacks) for 
running your own Nginx HTTP server with PHP on Heroku.

Versions
--------

Nginx: 1.3.3  
PHP: 5.4.5

Usage
-----

Creating your own Nginx + PHP server is easy. You configure any application that
currently runs on Nginx + PHP to easily run on Heroku with this buildpack. You need
to add a `_config` directory to the root of your project and include three config
files. 

    $ ls _config/
    nginx.conf.erb   php-fpm.conf   php.ini
    $ heroku create --buildpack http://github.com/travisj/heroku-buildpack-nginx-php
    $ git push heroku master
    ...
    -----> Heroku receiving push
    -----> Fetching custom buildpack... done
    -----> Nginx/PHP app detected
    -----> Installing Nginx
    -----> Bundling Nginx v1.3.3
    -----> Installing PHP
    -----> Bundling PHP v5.4.5
    -----> Installing boot script
    -----> Done with compile
    -----> Discovering process types
           Procfile declares types     -> (none)
           Default types for Nginx/PHP -> web

Config Files
------------

The buildpack requires that you have three config files: nginx.conf.erb, php-fpm.conf
and php.ini.

Example configs files are included in the examples directory, but you are free to
make any PHP or Nginx config changes you want.

Contributing
------------

Please send me pull requests for additional example configs and I would be happy
to include them in this project.
