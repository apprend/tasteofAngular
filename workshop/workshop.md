# A Taste of Angular.js

The Superheroic JavaScript Framework

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

> so what is is this magical [ng-mode](https://docs.angularjs.org/api/ng/directive/ngModel)l??

# Directives

![Picard](http://www.cinemablend.com/images/news_img/69362/patrick_stewart_69362.jpg)

---

Directives give angular it's expressive power - they give you a way to author new HTML elements and enhance others.

## Built in Directives

Angular has a large library of built-in directives to handle most of your single page application needs right out of the box

### Example

Open [2-angular-directives.html](http://apprend.github.io/tasteofAngular/workshop/2-angular-directives.html) in your code editor *and* web browser

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

`ng-show` evaluates an angular expression, and adds the class `ng-hide` to the element it is attached to if it's expression is falsey (false, undefined, null, NaN etc.). This means the element is still on the page, but has it's css to set to `display: none`. 

This particular code will only be visible when `name` is equal to `Ringo`, the last element in our `ng-init` array.

```html
<!-- the ng-show directive hides/shows an element based on truthiness of an expression -->
<span ng-show="name=='Ringo'" class="glyphicon glyphicon-star"></span>
```

### Hide/Show

### Repetition
