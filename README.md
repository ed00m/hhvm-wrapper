**This project is no longer maintained as Facebook removed the functionality it was built on from HHVM.**

# hhvm-wrapper

**hhvm-wrapper** is a convenience wrapper for [HHVM](http://github.com/facebook/hhvm/).

[![Latest Stable Version](https://poser.pugx.org/sebastian/hhvm-wrapper/v/stable.png)](https://packagist.org/packages/sebastian/hhvm-wrapper)
[![Dependency Status](https://www.versioneye.com/php/sebastian:hhvm-wrapper/dev-master/badge.png)](https://www.versioneye.com/php/sebastian:hhvm-wrapper/dev-master)

## Installation

### PHP Archive (PHAR)

The easiest way to obtain hhvm-wrapper is to download a [PHP Archive (PHAR)](http://php.net/phar) that has all required dependencies of hhvm-wrapper bundled in a single file:

    wget https://phar.phpunit.de/hhvm-wrapper.phar
    chmod +x hhvm-wrapper.phar
    mv hhvm-wrapper.phar /usr/local/bin/hhvm-wrapper

You can also immediately use the PHAR after you have downloaded it, of course:

    wget https://phar.phpunit.de/hhvm-wrapper.phar
    php hhvm-wrapper.phar

### Composer

Simply add a dependency on `sebastian/hhvm-wrapper` to your project's `composer.json` file if you use [Composer](http://getcomposer.org/) to manage the dependencies of your project. Here is a minimal example of a `composer.json` file that just defines a development-time dependency on hhvm-wrapper:

    {
        "require-dev": {
            "sebastian/hhvm-wrapper": "*"
        }
    }

For a system-wide installation via Composer, you can run:

    composer global require 'sebastian/hhvm-wrapper=2.0'

Make sure you have `~/.composer/vendor/bin/` in your path.

## Usage Example

### Compilation

    ➜  ~  hhvm-wrapper compile --target application.hhbc /path/to/source
    hhvm-wrapper 2.0.2 by Sebastian Bergmann.

### Static Code Analysis

    ➜  ~  hhvm-wrapper analyze src
    hhvm-wrapper 2.0.2 by Sebastian Bergmann.

    Using ruleset phar://hhvm-wrapper-2.0.2.phar/ruleset.xml

    /usr/local/src/hhvm-wrapper/src/CLI/AnalyzeCommand.php
      72    Call to unknown method: $this->setName('analyze')

    /usr/local/src/hhvm-wrapper/src/CLI/BaseCommand.php
      67    Call to unknown method: $this->setDefinition(array(new
            Symfony\Component\Console\Input\InputArgument('values',
            Symfony\Component\Console\Input\InputArgument::IS_ARRAY)))

    /usr/local/src/hhvm-wrapper/src/CLI/CompileCommand.php
      68    Call to unknown method: $this->setName('compile')

    Found 3 violations in 3 files (out of 12 total files).

