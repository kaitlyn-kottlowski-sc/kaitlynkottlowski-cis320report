First Page
==========

 [#f4]_ [#f11]_

In 2012, Google first released their JavaScript front-end framework called
AngularJS. Originally this framework was meant for web-designers, however, it
is more used by developers today. It is open-sourced and used for web
application. After a couple years, the structure of web development changed
as JavaScript became more advanced. Thus came the rewrite of Angular 2 and
beyond. Angular 2 was released in 2016 as an open-source, TypeScript-based
front-end web application platform. While AngularJS's architecture is based
on the model-view-controller (MVC) design, Angular 2+ uses
model-view-viewmodel (MVVM). However, both designs can be implemented in both
AngularJS and Angular2+.

Something that cannot be easily implemented in AngularJS is a search
engine withing a Single Page Application (SPA). Although Angular2+ has
an easier time creating it. Also, Angular2+ is considered to be more
well-defined, some things can be done in multiple ways. Similarly, the syntax
of Angular2+ is said to be simpler than AngularJS. When it comes to the
binding syntax, Angular uses ng directives, which are extended HTML
attributes, and "{{ }}" to bind the data to the view, while Angular 2+ uses "
( )" and "[ ]" for event and property binds. For example:

The app.component.ts will be used for both examples.
app.component.ts
    import { Component } from '@angular/core';
    @Component({
        selector: 'test-app',
        templateUrl: './app/databinding.html'
    })
    export class AppCopoment {
        name = 'Kaitlyn Kottlowski';
    }

Angular JS Example-
databinding.html
    <h4> Data binding in AngularJS Application</h4>
    <div>
        <h5>Binding example</h5>
        Hello {{name}} !
    </div>

Angular2+ Example-
databinding.html
    <h4> Data binding in Angular 2+ Application</h4>
    <div>
        <h5>Binding example</h5>
        Hello <span [innerText]="name"></span>! <br/>
        OR <br/>
        <input type='text' [value]="name" />
    </div>


Unlike AngularJS, Angular 2+ was built so that it could be used for large and
cross-platform applications and it is also mobile-oriented. However,
AngularJS does have a few advantages over Angular 2+ such as the framework
being unit testing ready, not needing to be downloaded with any extra
frameworks or plugins, and it is less complicated to set up. Overall, the only
similarities are between AngularJS and Angular2+ is that they are both
open-source front-end frameworks that are considered easy to learn. While
AngularJS is still supported by Google, the releases have ceased. Angular2+
is continuously updated and is currently on a Version 12, which was released
in November 2020.
