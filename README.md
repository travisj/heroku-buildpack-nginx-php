Heroku Buildpack: Nginx + PHP
=============================

This is a [Heroku Buildpack](http://devcenter.heroku.com/articles/buildpacks) for 
running your own Nginx HTTP server with PHP on Heroku.

Usage
-----

Creating your own Nginx + PHP server:

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
