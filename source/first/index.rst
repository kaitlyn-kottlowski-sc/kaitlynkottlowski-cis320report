First Page
==========

* AngularJS versus Angular2+

    * History of the transition from AngularJS to Angular2+
    * Differences in architecture, language, syntax, etc.
    * Similarities
    * Advantages of Angular2+

In 2012, Google first released their JavaScript front-end framework called
AngularJS. [#f11]_ Originally this framework was meant for web-designers,
however, it
is more used by developers today. It is open-sourced and used for web
application. After a couple years, the structure of web development changed
as JavaScript became more advanced. Thus came the rewrite of Angular 2 and
beyond. Angular 2 was released in 2016 as an open-source, TypeScript-based
front-end web application platform. [#f11]_ While AngularJS's architecture is based
on the model-view-controller (MVC) design, Angular 2+ uses
model-view-viewmodel (MVVM). [#f11]_ However, both designs can be implemented in both
AngularJS and Angular2+.

Something that cannot be easily implemented in AngularJS is a search
engine within a Single Page Application (SPA), although Angular2+ has
an easier time creating it. [#f12]_ Also, Angular2+ is considered to be more
well-defined, some things can be done in multiple ways. Similarly, the syntax
of Angular2+ is said to be simpler than AngularJS. [#f12]_ When it comes to the
binding syntax, Angular uses ng directives, which are extended HTML
attributes, and "{{ }}" to bind the data to the view, while Angular 2+ uses "
( )" and "[ ]" for event and property binds. [#f11]_ For example:

The app.component.ts will be used for both examples. [#f13]_
app.component.ts::

    import { Component } from '@angular/core';
    @Component({
        selector: 'test-app',
        templateUrl: './app/databinding.html'
    })

    export class AppCopoment {
        name = 'Kaitlyn Kottlowski';
    }

Angular JS Example-
databinding.html::

    <h4> Data binding in AngularJS Application</h4>
    <div>
        <h5>Binding example</h5>
        Hello {{name}} !
    </div>

Angular2+ Example-
databinding.html::

    <h4> Data binding in Angular 2+ Application</h4>
    <div>
        <h5>Binding example</h5>
        Hello <span [innerText]="name"></span>! <br/>
        OR <br/>
        <input type='text' [value]="name" />
    </div>


Unlike AngularJS, Angular 2+ was built so that it could be used for large and
cross-platform applications and it is also mobile-oriented. [#f11]_ However,
AngularJS does have a few advantages over Angular 2+ such as the framework
being unit testing ready, not needing to be downloaded with any extra
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