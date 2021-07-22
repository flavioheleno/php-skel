# php-skel

A very opinionated PHP Skeleton for Projects and Libraries

## Distribution

This skeleton has two distributions: **project** and **library**.

### Project

Use the following files:

- [composer-proj.json](composer-proj.json)
- [phpunit-proj.xml.dist](phpunit-proj.xml.dist)

Update the `composer.json` accordingly.

**Conventions:**

1. Application namespace is: `App\`;
2. Tests are split into *Unit Tests* (`tests/unit`) and *Integration Tests* (`tests/integration`).

### Library

Use the following files:

- [composer-lib.json](composer-lib.json)
- [phpunit-lib.xml.dist](phpunit-lib.xml.dist)

Update the `composer.json` accordingly.

**Conventions:**

1. Tests are grouped as a suite in `tests/`.

## Configuration files

The following configuration files are available:

- [phpunit-lib.xml.dist](phpunit-lib.xml.dist): PHPUnit configuration for Libraries;
- [phpunit-proj.xml.dist](phpunit-proj.xml.dist): PHPUnit configuration for Projects;
- [psaml.xml.dist](psaml.xml.dist): Psalm configuration;
- [ruleset.xml.dist](ruleset.xml.dist): A copy of [flavioheleno/phpcs-ruleset](https://github.com/flavioheleno/phpcs-ruleset).

## Composer scripts

Composer has helper scripts for executing common tasks as seen below.

Script        | Description
--------------|------------
console       | Uses [psy/psysh](https://packagist.org/packages/psy/psysh) to run an interactive shell
infection     | Uses [infection/infection](https://packagist.org/packages/infection/infection) as mutation test framework
lint          | Uses [php-parallel-lint/php-parallel-lint](https://packagist.org/packages/php-parallel-lint/php-parallel-lint) to lint source code
phpcs         | Uses [squizlabs/php_codesniffer](https://packagist.org/packages/squizlabs/php_codesniffer) to check coding style
phpstan       | Uses [phpstan/phpstan](https://packagist.org/packages/phpstan/phpstan) as static analyser
phpunit       | Uses [phpunit/phpunit](https://packagist.org/packages/phpunit/phpunit) as test framework
psalm         | Uses [vimeo/psalm](https://packagist.org/packages/vimeo/psalm) to check for tainted strings
test-ci       | Runs library test suite (for continuous integration)
test-coverage | Runs test-coverage analysis
test          | Runs infection, lint, phpcs, phpstan, phpunit and psalm

## Workflows

### Continuous Integration

Executes project test suite using [phpunit/phpunit](https://packagist.org/packages/phpunit/phpunit) on push and pull request events.

Workflow configuration: `.github/workflows/continuous-integration.yml`.

### Static Analysis

Executes static code analysis using [phpstan/phpstan](https://packagist.org/packages/phpstan/phpstan) on push and pull request events.

Workflow configuration: `.github/workflows/static-analysis.yml`.

### Template sync

Periodically checks for changes in [flavioheleno/php-skel](https://github.com/flavioheleno/php-skel) and, if there are any, creates or updates a pull request in this repository to review the changes.

Workflow configuration: `.github/workflows/template-sync.yml`.

Source: [solvaholic/template](https://github.com/solvaholic/template)

## License

This project is licensed under the [MIT License](LICENSE).
