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

### Hide/Show

### Repetition
