First Page
==========

AngularJS versus Angular2+
--------------------------

    * History of the transition from AngularJS to Angular2+
    * Differences in architecture, language, syntax, etc.
    * Similarities
    * Advantages of Angular2+

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
binds. [#f11]_ For example: [#f13]_

Angular JS Two-Binding Example

``angular-js-example.html`` [#f17]_ ::

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

Angular2+ Example
-----------------

``app.component.ts`` ::

    import { Component } from '@angular/core';
    @Component({
        selector: 'test-app',
        templateUrl: './app/databinding.html'
    })

    export class AppCopoment {
        name = 'Kaitlyn Kottlowski';
    }

``databinding.html`` ::

    <h4> Data binding in Angular 2+ Application</h4>
    <div>
        <h5>Binding example</h5>
        Hello <span [innerText]="name"></span>! <br/>
        OR <br/>
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

.. [#f11] Kumar, Pankaj. (January 19, 2021). "`AngularJS Vs. Angular 2 Vs.
    Angular 4: Understanding the Differences <https://www.simplilearn
    .com/angularjs-vs-angular-2-vs-angular-4-differences-article>`_".
    Simplilearn. Retrieved March 1, 2021.

.. [#f12] Pedamkar, Priya. "`AngularJS vs Angular 2 <https://www.educba
    .com/angular-js-vs-angular-2/>`_". Educba. Retrieved March 8, 2021.

.. [#f13] Trivedi, Jignesh. (September 16, 2016). "`Data Binding in Angular 2
    <https://www.c-sharpcorner.com/article/data-binding-in-angular-2/>`_".
    C# Corner.  Retrieved March 8, 2021.

.. [#f17] "`Angularjs Data Binding <https://www.w3schools
    .com/angular/angular_databinding.asp>`_". (n.d.). Retrieved March 25, 2021.