##### Atom and all repositories under Atom will be archived on December 15, 2022. Learn more in our [official announcement](https://github.blog/2022-06-08-sunsetting-atom/)
 [![build status](https://secure.travis-ci.org/vojtajina/grunt-coffeelint.svg)](http://travis-ci.org/vojtajina/grunt-coffeelint)
# grunt-coffeelint

**Lint your CoffeeScript with [CoffeeLint].**

## Installation

Install npm package, next to your project's `Gruntfile.js` file:

    npm install grunt-coffeelint

Add this line to your project's `Gruntfile.js`:

    grunt.loadNpmTasks('grunt-coffeelint');

## Options

A few additional options are supported:

### force
Type: `Boolean`
Default value: `false`

Set `force` to `true` to report CoffeeLint errors but not fail the task.

## Configuration

`coffeelint` is a multitask, so you can use it similary to `lint`, `watch` etc...

````javascript
grunt.initConfig({
    ...
    coffeelint: {
      app: ['app/*.coffee', 'scripts/*.coffee']
    },
    ...
});
````

### Options per target

````javascript
grunt.initConfig({
    ...
    coffeelint: {
      app: ['app/*.coffee', 'scripts/*.coffee'],
      tests: {
        files: {
          src: ['tests/*.coffee']
        },
        options: {
          'no_trailing_whitespace': {
            'level': 'error'
          }
        }
      }
    },
    ...
});
````

### Global - default options

````javascript
grunt.initConfig({
    ...
    coffeelint: {
      options: {
        'no_trailing_whitespace': {
          'level': 'error'
        }
      }
    },
    ...
});
````

### Loading external config

````javascript
grunt.initConfig({
    ...
    coffeelint: {
      options: {
        configFile: 'coffeelint.json'
      }
    },
    ...
});
````
Task `options` take precedence over `configFile` options.

For available options see [coffeelint homepage].

[CoffeeLint]: http://www.coffeelint.org/
[coffeelint homepage]: http://www.coffeelint.org/
