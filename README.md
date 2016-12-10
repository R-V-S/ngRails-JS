# ngRails (JavaScript)

An easy starter project for a Rails 5 / Angular 2 build. This is the JavaScript version. There is also a [TypeScript version](https://github.com/R-V-S/ngRails). Features:

* [webpack](https://webpack.github.io/) serves assets.
* [Babel](https://babeljs.io) enables ES6/7 JavaScript language features using the [Latest preset](https://babeljs.io/docs/plugins/preset-latest/).
* [Sass](http://sass-lang.com/) makes styling smart, and smart styling easy.
* [Foreman](https://github.com/ddollar/foreman) runs webpack and Rails server concurrently with just one command.
* [Heroku](https://www.heroku.com/) deployment is a cinch.

## Prerequisites

* [Node.js and npm](https://docs.npmjs.com/getting-started/installing-node)
* [Ruby 2.3.3](https://www.ruby-lang.org/en/). Consider [RVM](https://rvm.io/), if not already installed.
* [Rails 5](http://rubyonrails.org/)
* [Bundler](https://bundler.io/)
* (Optional) [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli)

## Installation

### Fork or clone this repository

If you choose to clone, you can run this command to clone this repo into a new project folder (e.g. `my-proj`):

```sh
git clone https://github.com/R-V-S/ngRails-JS.git my-proj
cd my-proj
```

### Install the node modules for webpack and Babel

```sh
npm install
```

### Install gems

```sh
bundle
```

### Run

```sh
foreman start
```

## Development

### Angular

Angular's files are contained in `app/client`. No testing platform is installed. Consider [Karma](https://karma-runner.github.io/1.0/index.html).

[Decorators](https://angular.io/docs/ts/latest/api/core/index/Component-decorator.html) are supported through the [Babel Legacy Decorator plugin](https://github.com/loganfsmyth/babel-plugin-transform-decorators-legacy).

Templates and stylesheets should be required inline rather than using Angular's `templateUrl` or `styleUrls`.

Stylesheets for components _must_ end in `.component.css` or `.component.scss`. This is because component stylesheets, which are included inline, must be run through Babel's [raw loader](https://github.com/webpack/raw-loader).

### Webpack

Webpack's configuration is in `config/webpack.config.js`

### Rails

Rails is installed without Sprockets (-S) and without Minitest (-T). [Rspec](http://rspec.info/) is installed as a testing platform.

### Databases

By default, **sqlite3** is configured to run locally and **postgresql** is configured for production.

## Deployment

Deploying to Heroku is easy.

### Install the Heroku CLI

[Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli)

### Create a new Heroku app

```sh
heroku create
```

### Configure buildpacks

```sh
heroku buildpacks:add --index 1 heroku/nodejs
heroku buildpacks:add --index 2 heroku/ruby
heroku buildpacks:add --index 3 https://github.com/febeling/webpack-rails-buildpack.git
```

### Push your code / Deploy

```sh
git push heroku master
```

### Open

```sh
heroku open
```
