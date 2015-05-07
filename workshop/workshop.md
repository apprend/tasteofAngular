# A Taste of Angular.js

The Superheroic JavaScript Framework

![Angular Logo](https://www.codementor.io/assets/tutorial_icon/angularjs.png)

## Hi, I'm Alan

 * 8 Years of development experience
 * I've taught for Girl Develop It, Grand Circus, Apigee
 * I started Apprend
 * Freelance as 13protons -  Web Dev & Graphic Design

 Contact Me: [@apprenddetroit]() -or- [alan@apprend.org]()

## This Is A Test

![space jam](https://media.giphy.com/media/RqPWMAWfT50cM/giphy.gif)

Our workshops are a way of testing out curriculum ideas and having fun before fully developing longer, paid classes.

## [**Building Interactive Websites**](http://apprend.org/events/2015/jQuery-Bootstrap/)
**Monday May 11 - Wednesday May 20**
Go further by building interactivity into your websites

![BADW](http://apprend.org/images/banners/intermediate_js.png)

## Goals for today

  * Environment setup
  * Getting Started
  * Two-way data binding
  * Filters
  * Doing real work - Directives
  * Controllers
  * doing more...

# Environment Setup

### Environment Setup

  Use either of these two free tools for code editing:

  * **Atom** - [atom.io](https://atom.io/)
  * Sublime - [sublimetext.com/](http://www.sublimetext.com/)

  Use Chrome for your browser, if you can

  * **Chrome** - [google.com/chrome](http://www.google.com/chrome/)

  Use Safari if you can't or don't want to use Chrome

  * Safari - [support.apple.com/downloads/#safari](https://support.apple.com/downloads/#safari)

# Getting Started

![Core Sample](http://www.suntrek.org/blog/wp-content/uploads/2012/04/ice-core.jpg)

### Download

[https://github.com/apprend/tasteofAngular](https://github.com/apprend/tasteofAngular)

![Download Repo](http://apprend.github.io/tasteofAngular/images/download_repo.gif)

### Let's Test it

  * Unzip `tasteofAngular-master.zip`
  * Find `/workshop/0-bare-bones.html`
  * Open [that file](http://apprend.github.io/tasteofAngular/workshop/0-bare-bones.html) in your code editor *and* web browser

```html
<script src=".../angular.min.js"></script>
...
<body ng-app>
    <p><input ng-model="words" /></p>
    <p>{{ words }}</p>
</body></html>
```

# Data Binding

![Two Way](http://upload.wikimedia.org/wikipedia/commons/8/86/W081_Two-Way_Traffic_Crrossing_-_Warning_Sign_Ireland.png)

---

Data binding in angular is said to be "two-way", meaning updates in your model immediately and automatically update the view, and vice-versa.

Let's play with simple one-way binding for now - syncing **from** view **to** model.

### Example

Open [1-data-binding.html](http://apprend.github.io/tasteofAngular/workshop/1-data-binding.html) in your code editor *and* web browser

![Download Repo](http://apprend.github.io/tasteofAngular/images/data-binding.gif)

### What's going on?

This is essentially the same as our bare-bones example - two variables declared with `ng-model` that are rendered inside
`{{ }}` templates, plus a little bootstrap to pretty things up.

Here's the important code:

```html
<h1>My first {{ noun || "__" }} was {{ adj || "__" }}!</h1>
...
<input class="form-control" ng-model="noun" placeholder="a thing" />
<input class="form-control" ng-model="adj" placeholder="something about it" />
```

> so what is is this [ng-model](https://docs.angularjs.org/api/ng/directive/ngModel) voodoo magic ??

# Filters

![Cinderella](http://cdn.mamamia.com.au/wp/wp-content/uploads/2015/05/Tumblr_static_cinderella_dress_transformation_gif.gif)

### Filters take data and transform it
Angular comes with a number of built in filters to handle some of the most common tasks

### Examples

To use a built in filter, put the filter name and a pipe `|` after your mustache template expresion

`{{ expression | filter }}`

Open [2-filter.html](http://apprend.github.io/tasteofAngular/workshop/2-filter.html) in your code editor *and* web browser

### uppercase

In the first example, notice that we use the `uppercase` filter which, unsurprisingly, transforms the string values to all caps regardless of how they are stored in the array. There is a similar filter for lowercase.

> It works just like JavaScript's `.toUpperCase()` string method

### orderBy : expression

In the second example, we can apply the filter `orderBy: member` to our `{{ member }}` expression. This transforms the order of the array based on an expression. If that expression is a property then it will order the elements alphabetically.

We can also specify ascending or descending order by prepending the `+` or `-` operators to the expression. Note that you have to wrap the expression in quotes when you add these operators.

### filter : expression

You can also implement a very simple in-client search on more complex objects. Here we have a collection of objects with two properties. When we add the `filter : membersNameOrInstrument` we can perform a fuzzy search on the object.

In this case, we are filtering based on an `ng-model=membersNameOrInstrument` which is data bound to the text input. Try typing in the text input. It will instantly filter the object based on what's in the text field. By default, the filter is a fuzzy search but it can be adapted to filter on specific properties.

### limitTo

As a bonus, we can limit the number of elements that are displayed in our `ng-repeat` by using the `limitTo` filter. Passing a number to this filter will limit the array to that many.

# Directives

![Picard](http://www.cinemablend.com/images/news_img/69362/patrick_stewart_69362.jpg)

---

Directives give angular it's expressive power - they give you a way to author new HTML elements and enhance others.

## Matching

The biggest "gotchya" to those new to angular is how directive names are normalized and matched. Each of the following is a valid way of declaring the `ng-bind` directive:

```html
  <span ng-bind="name"></span>
  <span ng:bind="name"></span>
  <span ng_bind="name"></span>
  <span data-ng-bind="name"></span>
  <span x-ng-bind="name"></span>
```

> For consistency, pick **one** way of declaring directives and stick to it. `ng-bind` (prefix dash name) is preferred.

## Compile

To add to the confusion, there are multiple ways to attach a custom directive to a view. Here are the two most common:

```html
<my-dir></my-dir>
<span my-dir="exp"></span>
```

> Any element could be substituted for the `span` element. Best practice is to use the second form i.e. adding the directive as an element attribute

## Documentation

The last confusing thing to know about directives is that they are usually referred to as camel case in the docs:

For example, you'll see the `ng-if` directive referred to as `ngIf` in the angular docs.

Remember that `ng-if` == `ngIf` == `data-ng-if` == `ng_if` etc... == `extra work for you when trying to read your own code`

## Built in Directives

Angular has a large library of built-in directives to handle most of your single page application needs right out of the box

### Example

Open [3-angular-directives.html](http://apprend.github.io/tasteofAngular/workshop/3-angular-directives.html) in your code editor *and* web browser

### ng-init

`ng-init` is a way of creating variables right in your view. It takes an "angular expression", which for most purposes looks just like regular JavaScript with. A few bits are missing, like the `var` and `;` you'd normally write).

```html
<!-- the ng-init directive creates a variable in the current scope -->
<div ng-init="beatles=['John', 'Paul', 'George', 'Ringo']" class="container">
```

### ng-repeat

`ng-repeat` let's you execute a `for/in` loop in your view, using the HTML element that you declare it on as a template. This `ng-repeat` will create 4 `<li>` elements because `beatles` was created as an array with 4 items in our `ng-init` directive

```html
<!-- the ng-repeat directive loops over a collection, using an element as a template -->
<li ng-repeat="name in beatles" class="list-group-item">
```

### ng-show

`ng-show` hides an element by adding the class `ng-hide` to it if you supply a "falsey" (false, undefined, null, NaN etc.) expression. This means the element is still on the page, but has it's css to set to `display: none`.

This particular code will only be visible when `name` is equal to `Ringo`, the last element in our `ng-init` array.

```html
<!-- the ng-show directive hides/shows an element based on truthiness of an expression -->
<span ng-show="name=='Ringo'" class="glyphicon glyphicon-star"></span>
```

### ng-if

`ng-if` removes an element from the DOM if you supply it with a "falsey" expression. The element cannot trigger or respond to events.

```html
<!-- the ng-if directive adds/removes an element based on truthiness of an expression -->
<span ng-if="name=='John'" class="glyphicon glyphicon-heart" ></span>
```

# Controllers

![Cockpit](http://www.acclaimimages.com/_gallery/_free_images/0420-0904-2711-5734_two_pilots_inside_the_cockpit_of_an_aircraft_o.jpg)

---

Controllers are a powerful abstraction for isolating business logic and managing dependencies.

Until now, we've been using `ng-init` to interact with the default controller created by the `ng-app` direactive. Let's create our own app and controllers to take more control of the situation.

## Rewriting our directive with a controller

Let's move our `ng-init="beatles=..."` into it's own controller. Angular requires that controllers be bound to apps, so we need to create one of those too.

Open [4-simple-controller.html](http://apprend.github.io/tasteofAngular/workshop/4-simple-controller.html) in your code editor *and* web browser

### Example

You can see our `ng-app` directive now points to a named app, and our `ng-init` has been replaced with the `ng-controller` directive.

```html
<body ng-app='Beatles' >
  <div ng-controller="BeatlesController" class="container">
```

The app and controller have been defined in our `<script>` tag at the bottom of the page:

```javascript
  var app = angular.module('Beatles', []);

  app.controller('BeatlesController', ['$scope', function ($scope) {
    $scope.beatles=['John', 'Paul', 'George', 'Ringo', false];
  }]);
```

## Anatomy of our controller

A controller is a constructor function, and the controller API allows you to attach a controller to a given app and inject dependancies. Angular intentionally hides global scope from code inside your controllers, so use angular's build in `$window` and other `$` prefixed functions to interface with object you'd expect to be in the global scope.

## Anatomy of our controller

```javascript
app.controller('name', ...);
```

You must first name your controller so you can access it in your view. Controller names should be unique to your app.

## Anatomy of our controller

```javascript
app.controller(..., ['$scope', function ($scope) { ... }] );
app.controller(..., ['$scope', 'anotherDependancy', function ($scope, anotherDependancy) { ... }] );
```

Dependencies are declared with a pattern that is meant to survive minification. Create an array where the last element is your controller function, and each preceding array item is a dependency name.

## Anatomy of our controller

```javascript
$scope.beatles=...;
```
```html
<li ng-repeat="name in beatles" ...>
```

Anything property attached to your controller's scope object becomes accessible by that name in your view. This is equivalent to our `ng-init=` directive, except that it happens inside a real JS function, rather than an HTML attribute.

## Why, oh why?!

Controllers do **NOT** allow you to write less code, but they **DO** allow you to separate different types of code into modular, maintainable, testable units.

# Going Further

We've only scratched the surface of what you can do with angular.js. It's a full fledged client-side MV* framework and includes tons of other features such as:

> Data Binding, Controllers, Services, Scopes, Dependency Injection, Templates, Expressions, Filters, Forms, Directives, Animations, Modules, HTML Compiler, Providers, Unit Testing, E2E Testing, Promises, Validation engine, and much more...

## [**Create a Website with Angular.js**](https://apprend.org/events/2015/Angular/)
**Saturday, June 6**

Create modern, dynamic experiences without having to rely on a web server for rendering your user interface.

![BADW](http://apprend.org/images/banners/angular_header.png)

# Thank You!

  * [apprend.org/](http://apprend.org/)
  * [@apprenddetroit](https://twitter.com/apprenddetroit)
  * [meetup.com/apprend](http://www.meetup.com/apprend/)
