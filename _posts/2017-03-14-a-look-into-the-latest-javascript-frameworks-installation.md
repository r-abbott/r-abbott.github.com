---
layout: post
title: "A Look Into The Latest Javascript Frameworks - Installation"
date: 2017-03-14 18:45:00 UTC
tags: [Angular2,Aurelia,React,Vue,Javascript,Frameworks]
---
{% include JB/setup %}

This is a multi-part post that will take a look into the latest Javascript frameworks:
- [Angular 2](https://angular.io)
- [Aurelia](http://aurelia.io)
- [React](https://facebook.github.io/react)
- [Vue](https://vuejs.org)

This post will cover the process of installing and creating an application with the frameworks.

<h4>Angular 2</h4>
Angular 2 has two recommended installation paths. There is a starter project called [Angular Quickstart Seed](https://angular.io/docs/ts/latest/guide/setup.html) that can be used as a base to start your project, as well as an [Angular CLI Quickstart](https://angular.io/docs/ts/latest/cli-quickstart.html). Creating a new project using the seed is faster than using the CLI (by about a minute), as it has the npm packages already in place, while creating a new project using the CLI has to install all the packages.

<h5>Angular Quickstart Seed</h5>
The Seed requires you to have Node.js 4.x.x or higher and npm 3.x.x or higher.

If you have Git installed and are comfortable using it, you can clone the quickstart using the following:

{% highlight bash %}
git clone https://github.com/angular/quickstart.git quickstart
cd quickstart
npm install
{% endhighlight %}

Alternatively, you can [download a zip file](https://github.com/angular/quickstart/archive/master.zip), and after unzipping, install it with the following:

{% highlight bash %}
cd quickstart
npm install
{% endhighlight %}

After completing the installation, you can run the application and see it in your browser using:
{% highlight bash %}
npm start
{% endhighlight %}

<h5>Angular CLI Quickstart</h5>
Requires you to have Node.js 6.9.x or higher and npm 3.x.x or higher.

Similar to the Quickstart Seed, you can either install using npm or [download a zip file](https://angular.io/resources/zips/cli-quickstart/cli-quickstart.zip).

Using npm, the following will install angular globally:
{% highlight bash %}
npm install -g @angular/cli
{% endhighlight %}

After installing either via the zip or npm, you can create a new application using:
{% highlight bash %}
ng new my-project
{% endhighlight %}

And run the application and see it in your browser using:
{% highlight bash %}
cd my-project
ng serve --open
{% endhighlight %}

<h4>Aurelia</h4>
Aurelia [installation](http://aurelia.io/hub.html#/doc/article/aurelia/framework/latest/contact-manager-tutorial/1).
Aurelia currently requires NodeJs 4.x or higher, npm 3.x and a Git Client.

Installing Aurelia globally can be done with the following command:
{% highlight bash %}
npm install -g aurelia-cli
{% endhighlight %}

Creating an application is done via a wizard, which can be run using:
{% highlight bash %}
au new
{% endhighlight %}

After completing the wizard installation, the application can be run and seen in your browser using:
{% highlight bash %}
au run
{% endhighlight %}

<h4>React</h4>
React [installation](https://facebook.github.io/react/docs/installation.html).

In order to create React applications, Create React needs to be installed using npm:
{% highlight bash %}
npm install -g create-react-app
{% endhighlight %}

Once installation is complete, you can create a new application using (this may take a few minutes):
{% highlight bash %}
create-react-app hello-world
{% endhighlight %}

And run the application and see it in your browser using:
{% highlight bash %}
cd hello-world
npm start
{% endhighlight %}

<h4>Vue</h4>
Vue [installation](https://vuejs.org/v2/guide/installation.html). View can be installed generally or with the CLI.

General installation
{% highlight bash %}
npm install vue
{% endhighlight %}
CLI Installation
{% highlight bash %}
npm install -g vue-cli
{% endhighlight %}

Creating a new application via the CLI is done by running the installation wizard. It will take you through several steps to configure the application:
(Note: this example uses the webpack template, other templates are also available and can be found [here](https://github.com/vuejs-templates))
{% highlight bash %}
vue init webpack my-project
cd my-project
npm install
{% endhighlight %}

Run the application and see it in your browser using:
{% highlight bash %}
npm run dev
{% endhighlight %}

<h4>Conclusion</h4>
All of the global installations and creation of the first application are pretty quick (a few minutes). They are also very comparable when installing using a CLI, with the steps being straightforward and simple, and abstracting all the heavy lifting away from the user. Also, all of the created applications are runnable (which I think is very important to get right, as people become frustrated when things do not work right away), and ready for you to develop your own application.