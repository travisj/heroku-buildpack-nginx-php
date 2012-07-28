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

Builds
------

In the `builds` directory you can find the scripts used to create the executables. 
If you need to build either with additional support, fork this project, update
the build scripts and run:

    $ ./builds/php 5.4.5
    ...
    (available at http://php54-with-fpm.herokuapp.com/output/fcb93b5c-89ce-4cd3-b8a3-aa34305d3cab)
    ...

Look for the url where this new build is available and update `bin/compile` with 
your build. 

If this is your first time creating a build for Heroku, you will need to install
[Vulcan](https://github.com/heroku/vulcan/) and run:

    $ vulcan create APP_NAME

Please send a pull request if you are adding functionality that you think anyone
would benefit from.
