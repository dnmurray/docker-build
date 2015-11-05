![logo](https://www.phase2technology.com/wp-content/uploads/2015/06/logo-retina.png)

## Description

This image provides the many development tools necessary to build applications
the Phase2 way, bundled with a wide array of tools useful for development and
troubleshooting via the command-line interface. While it is possible to directly
connect via our "web" containers, this is the preferred way to perform "server work".

Contains everything you need to work with Drupal, including use of tools such as
[Grunt-Drupal-Tasks](https://github.com/phase2/grunt-drupal-tasks) and
[Pattern Lab Starter](https://github.com/phase2/pattern-lab-starter/).

## Available Packages & Tools

* Out of the box support for PHP 5.5, Ruby 1.9.3, and Node 0.12.7.
* Global availability of Composer, NPM v2, Bower, Grunt, and Yeoman.

For more details of specific packages, libraries, and utilities, please see the
[Dockerfile](https://bitbucket.org/phase2tech/p2docker/src/master/p2docker-devtools-build/Dockerfile).

## Drush (Drupal Shell) Configuration

There is global configuration for Drush at `/etc/drush/drushrc.php`.

Default configuration in this file provides the following:

* Unlimited memory for PHP operations run via Drush.
* Unlimited execution time for PHP operations run via Drush.
* Drush commands will be looked up in `/etc/drush/commands`.
* Drush aliases will be looked up in `/etc/drush`.

### Additional Commands

* **Registry Rebuild**: `drush rr` is included by default.

## Environment Variables

When you start the devtools-build image, you can adjust the configuration of the
build instance by passing one or more environment variables on the docker run
command-line or via your docker-compose manifest file.

Additional environment variables for commonly customized settings will be considered.

### PHP_MEMORY_LIMIT

Override the default `memory_limit` for general PHP operations.

* **Default**: `256m`

### PHP_OPCACHE_MEMORY

Specify the memory limit for Zend OpCache (`opcache.memory_consumption`). This
setting should be carefully monitored to ensure it is large enough to hold the
full codebase, otherwise thrashing could result in reduced performance.

* **Default**: `192`

### MAX_EXECUTION_TIME

Specify PHP's max execution time.

* **Default**: `30`

## View the Source

For more information about this image and its history, please see [the relevant manifest file (`p2docker-devtools-build`)](https://bitbucket.org/phase2tech/p2docker/src/master/p2docker-devtools-build/). This image is updated via pull requests to [the `p2docker` Bitbucket repo](https://bitbucket.org/phase2tech/p2docker).

For detailed information about the virtual/transfer sizes and individual layers of each of the above supported tags, please see [the `mysql/tag-details.md` file](https://github.com/docker-library/docs/blob/master/mysql/tag-details.md) in [the `docker-library/docs` GitHub repo](https://github.com/docker-library/docs).
