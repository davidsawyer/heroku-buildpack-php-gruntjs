Heroku: Apache + PHP + Grunt
====================

This is a buildpack combining the [PHP](https://github.com/heroku/heroku-buildpack-php) and [NodeJS](https://github.com/heroku/heroku-buildpack-nodejs) buildpacks, which allows for an on-deploy Grunt build.

Configuration
-------------

Refer to [this repo](https://github.com/gcpantazis/template-heroku-php-gruntjs) for a working template that utilizes this project.

Use the following command (more info [here](https://devcenter.heroku.com/articles/buildpacks#using-a-custom-buildpack)) to initialize heroku with the buildpack:

`$ heroku create --buildpack https://github.com/gcpantazis/heroku-buildpack-php-gruntjs.git`

The buildpack expects that you set a package.json file at your project's root for node/npm configuration as well as grunt info. Gruntfile.(js|coffee) should also live in the root.

Sass will be installed prior to any grunt installs so you can use the grunt-contrib-sass plugin.

On deploy to heroku, this configuration installs grunt globally, and will run `npm install` at the root.

License
-------

Copyright (c) 2012 George Pantazis Licensed under the MIT license.
