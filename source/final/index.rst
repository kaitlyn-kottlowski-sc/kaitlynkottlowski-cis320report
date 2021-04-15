An Adventure in Angular
=======================

.. figure:: angular_logo.png
    :width: 200px
    :align: center
    :height: 100px
    :alt: alternate text
    :figclass: align-center

    Angular Logo

    * What is Angular?
    * Who created it?
    * What is the purpose of Angular?
    * What languages can it be used with?

The Architecture of an Angular Application
------------------------------------------

Modules, Components, and Templates
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

One of the basic building blocks of the Angular framework architecture is
Angular components. These components are organized into NgModule classes that
provide a way to group sets of related functionality. NgModules can import other
NgModule functionality, as well as allowing their own functionality to be
imported in other NgModules. It is beneficial to use functional modules to
organize code for easier re-usability. A NgModule is defined by ``@NgModule()``
and the properties describe it. To start the Angular app, or to enable
bootstrapping, there must be a root module, usually named AppModule.

The following NgModule is an example of a root NgModule, AppModule:


.. code-block:: typescript
    :linenos:

    import { NgModule } from '@angular/core';
    import { BrowserModule } from '@angular/platform-browser';
    import { AppComponent } from './app.component';

    // @NgModule decorator with its metadata
    @NgModule({
        imports:      [ BrowserModule ],
        providers:    [ Logger ],
        declarations: [ AppComponent ],
        exports:      [ AppComponent ],
        bootstrap:    [ AppComponent ]
    })
    export class AppModule { }


Only the AppComponent component is used in the AppModule example. However, any
other NgModule can include many components. "All components connect a component
hierarchy with the page document object model (DOM). Each component defines a
class that contains application data and login, and is associated with the
HTML template that defines a view to be displayed in a target environment."

An example of a Component is:

.. code-block:: typescript
    :linenos:

    import { Component } from '@angular/core';
    @Component({
        selector: 'example-selector',
        templateUrl: './example-html-template.html',
        styleUrls: ['./example-separate-css-file.css']
    })
    export class ExampleComponent {}


The ExampleComponent stores the css files in the ``styleUrls`` property and the
HTML file in the ``templateUrl`` property. The ``selector`` property stores the name of the CSS selector that creates
and inserts an instance of the ExampleComponent where ever it finds
``<example-selector></example-selector>`` in the template HTML.

A **template** combines HTML with Angular syntax, such as the
ExampleComponent component above. A template's directives provide the program
logic, while the binding syntax connects the app data and the DOM. The
binding syntax could be event binding, where the app responds to user input,
or property binding, which allows developers to inserts the app data into the
HTML file.

Services
^^^^^^^^

In addition, Angular components define views and use services that provide
specific functionality. [#f8]_ Service classes can be created to share data
and/or logic over multiple views and can depend on other services.

The example below shows ``HeroService`` depends on the ``Logger`` service and
the ``BackendService``. [#f8]_

.. code-block:: typescript
    :linenos:

    import { Injectable } from '@angular/core';

    @Injectable({
      providedIn: 'root',
    })
    export class HeroService {
      private heroes: Hero[] = [];

      constructor(
        private backend: BackendService,
        private logger: Logger) { }

      getHeroes() {
        this.backend.getAll(Hero).then( (heroes: Hero[]) => {
          this.logger.log(`Fetched ${heroes.length} heroes.`);
          this.heroes.push(...heroes); // fill cache
        });
        return this.heroes;
      }
    }

These services can be injected dependencies allowing code to be modular,
reusable, and efficient. Dependencies are not always services; they can be
objects, functions, values, etc. An dependency injection is used to request
dependencies from external sources instead of creating them. Before you
think about using a service, you must register one of its providers, which
is an object that explains how to object the dependency. The providers
property accepts services that then registers the services with the class
injector. The injector maintains created service instances and returns a new
one if the service instance does not exist. An example of a service being
registered in a component is below.

.. code-block:: typescript
    :linenos:

    @Component({
      selector:    'app-hero-list',
      templateUrl: './hero-list.component.html',
      providers:  [ HeroService ]
    })

Pipes
^^^^^

While services can share data, pipes can transform data. Pipes are an Angular
concept that filter data before displaying it on the view. The pipe (|)
operator can be used like ``{{title | uppercase }}``, where the ``uppercase``
is a built-in pipe that transforms the title text into all uppercase lettering.
Like most Angular concepts, you can use built-in pipes and create your own
pipes too.

Below is a custom pipe that takes in a number array and transforms
it into an increasing array of positive numbers. [#f3]_

.. code-block:: typescript
    :linenos:

    import { Pipe, PipeTransform } from '@angular/core';

    @Pipe({ name: 'positiveNumber' })
    export class PositivePipe implements PipeTransform {
            transform(value: number[]): number[] {
                return value.filter(v => v > 0);
        }
    }

The pipe ``positiveNumber`` can be referenced in the template html file,
where the number array ``number`` is declared in the ``Component`` class. The
syntax may look like ``{{ numbers | positiveNumbers }}``. [#f3]_


AngularJS versus Angular2+
--------------------------

In 2012, Google first released their JavaScript front-end framework called
AngularJS. [#f11]_ Originally this framework was meant for web-designers,
however, it largest share of usage has been among front-end developers. It is
open-sourced library used for web application development. After a couple
years, the structure of web development changed as JavaScript became more
advanced. Thus came the rewrite of Angular2+.

Angular 2 was released in 2016 as an open-source, TypeScript-based front-end web
application platform. [#f11]_ TypeScript is a static, object-oriented language
that also contains a set of tools that is converted into JavaScript. While
AngularJS's architecture is based on the model-view-controller (MVC) design,
Angular 2+ uses model-view-viewmodel (MVVM). [#f11]_ However, both designs
can be implemented in both AngularJS and Angular2+.

There are many advantages in using Angular2+ over AngularJS. A Single Page
Application (SPA) is more easily implemented in Angular2+, than AngularJS.
SPA is a website that dynamically rewrites the current web page based on user
interactions and new data from the server. [#f12]_ Unlike AngularJS, Angular 2+ was built so that it could be used for large and
cross-platform applications and it is also mobile-oriented. [#f11]_ Also,
Angular2+ is considered to be more well-defined, some things can be done in
multiple ways. Similarly, the syntax of Angular2+ is said to be simpler than
AngularJS. [#f12]_ When it comes to the binding syntax, which allows data to
bind to pages and update automatically, AngularJS uses ng directives, which are
extended HTML attributes using the prefix ``ng-``. Examples include the
``ng-app`` directive that initializes the app and the ``ng-init`` directive
that initializes the app data. AngularJS uses ``{{ }}`` to bind the data to
the view, while Angular2+ uses ``( )`` and ``[ ]`` for event and property
binds. [#f11]_

Angular JS Example [#f17]_
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: HTML
    :linenos:

    <div ng-app="myApp" ng-controller="myCtrl">
      Name: <input ng-model="name">
      <h1>{{name}}</h1>
    </div>

    <script>
    var app = angular.module('myApp', []);
    app.controller('myCtrl', function($scope) {
      $scope.name = "Kaitlyn Kottlowski";
    });
    </script>

Angular2+ Example [#f13]_
^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: typescript
    :linenos:

    import { Component } from '@angular/core';
    @Component({
        selector: 'test-app',
        templateUrl: './app/databinding.html'
    })

    export class AppCopoment {
        name = 'Kaitlyn Kottlowski';
    }


.. code-block:: HTML
    :linenos:

    <h4> Data binding in Angular 2+ Application</h4>
    <div>
        <h5>Binding example</h5>
        Hello <span [innerText]="name"></span>!
        <br/>
        <br/>
        <input type='text' [value]="name" />
    </div>


However, AngularJS does have a few advantages over Angular 2+ such as the
framework being unit testing ready, not needing to be downloaded with any extra
frameworks or plugins, and it is less complicated to set up. [#f11]_ Overall, the only
similarities are between AngularJS and Angular2+ is that they are both
open-source front-end frameworks that are considered easy to learn.
While AngularJS is still supported by Google, the releases have ceased.
Angular2+ is continuously updated and is currently on a Version 12, which was
released in November 2020.

Advantages and Disadvantages of Angular
---------------------------------------

Using Angular comes with many advantages. Angular's compiler, TypeScript, and
its combination with ES6 or ES7 JavaScript supports classes and module
loaders. Classes are blueprints that are using for creating objects that are
assigned functions and properties. [#f15]_

An example of a simple Person class in TypeScript would look like:

.. code-block:: typescript
    :linenos:

    class Person {
        firstName = "";
        lastName = "";
        constructor(firstName, lastName) {
            this.firstName = firstName;
            this.lastName = lastName;
        }

        name() {
            return `${this.firstName} ${this.lastName}`;
        }

        whoAreYou() {
            return `Hi i'm ${this.name()}`;
        }
    }

A module is another name for a reusable file, thus module loaders simply
interprets the module code and loads the module depending on the module
format. [#f14]_

For example, in HTML you may want to load in a javascript file or a .css
file like:


.. code-block:: HTML
    :linenos:

    <script src="Example/example.js"></script>
    <link rel="stylesheet" href="example.css">

Angular also has advanced form validation that includes the form being a
container that can be validated itself when submitted. Controllers can have
its own validation, which can include validating errors and providing users
with descriptive feedback on their views. Also, because Angular is backed by
Google it has one of the largest communities and Google's core team
collaborates with the community in design updates. While Angular2+ may have more simpler binding than AngularJS, compared to all
the other front-end frameworks, both AngularJS and Angular2+ are consider
easy to use in two-way binding. Two-way binding allows an update in the
browser to automatically update the data in storage, and if there the data in
the storage is updated, then the browser is immediately updated too. [#f6]_

Out of all the other frameworks, Angular is compared to React the most.
[#f2]_ While Angular is built with data-binding and is a complete framework,
React is even easier to learn and understand. Both frameworks use TypeScript
and have large communities. However, based on their GitHub repositories,
React has more popularity among users. [#f16]_ These findings correlate with
Angular's ranking on State of JavaScript.  The satisfaction and interest of
Angular has been below React since 2016. While Angular is still below React
in usage and awareness, Angular's usage has increased heavily since 2016
(Chart 1). [#f1]_

(Chart 1 here - show usage)

Applications Built By Angular
-----------------------------

Enterprise Web Apps
^^^^^^^^^^^^^^^^^^^

People use Angular to build all sorts of applications. The first type of
application is an Enterprise Web App. Most big organizations use this
web-based application to handle internal and external needs and operations.
Since Angular is scalable, which means it can handle growth and an increase
in users and load, it has started to become the go-to framework for big teams
. Organizations appreciated the re-usability of the components, the unified
architecture, and its high security standards. [#f9]_

Mobile Apps
^^^^^^^^^^^

Another type of application that can be built by Angular is Mobile. You can
use Angular with NativeScript to build an iOS or Android app. NativeScript is
another open-source framework used to develop mobile apps using JavaScript.
To build hybrid apps, you can use Angular with Ionic. Hybrid apps allow a
developer to create both iOS, Android, and Window apps from the same codebase.
Ionic is also another open-source framework using JavaScript. [#f9]_

Progressive Web Apps
^^^^^^^^^^^^^^^^^^^^

Thirdly, progressive web applications (PWA) can also be built using the Angular
framework. [#f9]_ PWAs are a type of application software built for the web
using JavaScript, HTML, and CSS. They are to work on any device and any browser.
PWAs are installable, should work offline as well as online, have minimal
page refreshes, and more. [#f18]_ Use the command ``ng add @angular/pwa`` to
build a PWA with Angular on the Command Line in the project directory.

Single-Page Apps
^^^^^^^^^^^^^^^^

Finally, the most popular application built by Angular is Single-Page
Applications (SPA). The purpose of a SPA is to allow the user to interact
with an application on a single page. The information displayed will appear
dynamically. SPAs are considered better at providing greater user experiences
in comparison to multi-page applications. [#f18]_

SPA Tutorial
------------
Can't do this part yet because the eBook I am referencing is unavailable due
to Simpson's Network issues.


References
----------

.. [#f1] Greif, S., Benitte, R., & Rambeau, M. (2020). "`The State of
    JavaScript 2020: Front-end frameworks <https://2020.stateofjs.com/en-US/technologies/front-end-frameworks/>`_". Retrieved
    19:52, February 6, 2021.

.. [#f2] Holas, T. (2017, June 27).
    "`Angular vs. React: Which is better for web development? <https://www.toptal.com/front-end/angular-vs-react-for-web-development>`_".
    Retrieved 20:05, February 06, 2021.

.. [#f3] Padmanabhan, P. (2018).
    "`Java ee 8 and angular : a practical guide to building modern single-page applications with angular and java ee
    <https://simpsoncollege.on.worldcat.org/search?queryString=kw%3A%28java+ee+8+and+angular%29&databaseList=638&origPageViewName=pages%2Fadvanced-search-page&clusterResults=true&expandSearch=true&translateSearch=false&queryTranslationLanguage=&scope=#/oclc/1021887714>`_".
    Packt Publishing.

.. [#f4] Оглукян, А. К. (2020).
    "`OVERVIEW OF THE ANGULAR FRAMEWORK: PROS AND CONS <https://os-russia.com/SBORNIKI/KON-299.pdf#page=33>`_".
    Omega Science International Center of Innovation Research, 33-37.

.. [#f5] Noccioli, R. (2019, May 2).
    "`Blast Off with Angular Material | Rachel Noccioli
    <https://www.youtube.com/watch?v=PPhkGNOgaNM&list=PLOETEcp3DkCpimylVKTDe968yNmNIajlR&index=42>`_ [Video file].
    NG Conf. Retrieved 20:34, February 6, 2021.

.. [#f6] Sultan, Mohamed. (2017, November 29-30).
    "`Angular and the Trending Frameworks of Mobile and Web-Based Platform
    Technologies: A Comparative Analysis <https://saiconference
    .com/Downloads/FTC2017/Proceedings/128_Paper_264
    -Angular_and_the_Trending_Frameworks_of_Mobile.pdf>`_". Future
    Technologies Conference (FTC). Retrieved February 21, 2021.

.. [#f7] Thorén, Emma, and Filip Brännlund Stål. March 17, 2017.
    "`Usage of Angular from Developers Perspective <http://www.diva-portal.org/smash/get/diva2:1112464/FULLTEXT01.pdf>`_". Blekinge Institute of Technology. Retrieved
    February 21, 2021.

.. [#f8] Google. "`Introduction to Angular Concepts <https://angular
    .io/guide/architecture>`_". Angular. Retrieved February 21, 2021.

.. [#f9] Gluszek, Lukasz. "`What Apps Can I Build With Angular? A Short Guid for
    Entrepreneurs and Managers <https://www.netguru
    .com/blog/what-apps-can-i-build-with-angular#:~:text=Angular%20is%20an
    %20excellent%20tool,allows%20building%20iOS%20and%20Android>`_". NetGuru.
    Retrieved February 21, 2021.

.. [#f10] Sirchend Softwares. "`Mobile App Development: Why choose Angular
    Development for Mobile Apps? <https://www.sirchend
    .com/web-development/mobile-app-development-why-choose-angular-development
    -for-mobile-apps/>`_". Sirchend Softwares Group. Retrieved February 21,
    2021.

.. [#f11] Kumar, Pankaj. (January 19, 2021). "`AngularJS Vs. Angular 2 Vs.
    Angular 4: Understanding the Differences <https://www.simplilearn
    .com/angularjs-vs-angular-2-vs-angular-4-differences-article>`_".
    Simplilearn. Retrieved March 1, 2021.

.. [#f12] Pedamkar, Priya. "`AngularJS vs Angular 2 <https://www.educba
    .com/angular-js-vs-angular-2/>`_". Educba. Retrieved March 8, 2021.

.. [#f13] Trivedi, Jignesh. (September 16, 2016). "`Data Binding in Angular 2
    <https://www.c-sharpcorner.com/article/data-binding-in-angular-2/>`_".
    C# Corner.  Retrieved March 8, 2021.

.. [#f14] Van de Moere, Jurgen. (February 21, 2017). "`A 10 minute primer to
    JavaScript modules, module formats, module loaders and module bundler
    <https://www.jvandemo.com/a-10-minute-primer-to-javascript-modules-module
    -formats-module-loaders-and-module-bundlers/>`_". JVanDemo. Retrieved March
    22, 2021.

.. [#f15] Asim. (December 26, 2018). "`Class and Inteface <https://codecraft
    .tv/courses/angular/es6-typescript/classinterface/>`_". CodeCraft. Retrieved
    March 22, 2021.

.. [#f16] Daityari, Shaumik. (March 15, 2021). "`Angular vs React vs Vue:
    Which Framework to Choose in 2021 <https://www.codeinwp
    .com/blog/angular-vs-vue-vs-react/>`_". codeinwp. Retrieved March 22, 2021.

.. [#f17] "`Angularjs Data Binding <https://www.w3schools
    .com/angular/angular_databinding.asp>`_". (n.d.). Retrieved March 25, 2021.

.. [#f18] Farrugia, Kevin. (August 11, 2015). "`A Beginner's Guid to
    Progressive Web Apps <http://kaitlynkottlowskicis320-env.eba-bfvuhtc5
    .us-east-2.elasticbeanstalk.com/name_list.html>`_". SmashingMagazine.
    Retrieved April 3, 2021.