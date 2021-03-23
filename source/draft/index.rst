Draft Paper
===========

* Angular adv and disadv [#f2]_ [#f6]_ [#f7]_

    * What does Angular do well?
    * What does Angular not do well?
    * What frameworks are comparable or better than Angular?
    * The People's opinion [#f1]_

Angular's compiler, TypeScript, and its combination with ES6 or ES7
JavaScript supports classes and module loaders. Classes are blueprints that
are using for creating objects that are assigned functions and properties
. [#f15]_ An example of a simple Person class in TypeScript would look like::

class Person { (1)
    firstName = ""; (2)
    lastName = "";
    constructor(firstName, lastName) {  (3)
        this.firstName = firstName;
        this.lastName = lastName;
    }

    name() { (4)
        return `${this.firstName} ${this.lastName}`;
    }

    whoAreYou() {
        return `Hi i'm ${this.name()}`; (5)
    }
}

A module is another name for a reusable file, thus module loaders simply
interprets the module code and loads the module depending on the module
format. [#f14]_ For example, in HTML UI you may want to load in a javascript
file or a .css file like ::

<script src="Example/example.js"></script>
<link rel="stylesheet" href="example.css">

Angular also has advanced form validation that include the form being a
container that can be validated itself when submitted. Controllers can have
its own validation, which can include validating errors and providing users
with descriptive feedback on their UI. Also, because Angular is backed by
Google it has one of the largest communities and Google's core team
collaborates with the community in design updates. While Angular2+ may have more simpler binding than AngularJS, compared to all
the other front-end frameworks, both AngularJS and Angular2+ are consider
easy to use in two-way binding. Two-way binding allows an update in the
browser to automatically update the data in storage, and if there the data in
the storage is updated, then the browser is immediately updated too. [#f6]_

Out of all the other frameworks, Angular is compared to React the
most. [#f2]_ While Angular is built with data-binding and is a complete
framework, React is even easier to learn and understand. Both frameworks use
TypeScript and have large communities. However, based on their GitHub
repositories, React has more popularity among users. [#f16]_ These findings
correlate with Angular's ranking on State of JavaScript.  The satisfaction
and interest of Angular has been below React since 2016. While Angular is
still below React in usage and awareness, Angular's usage has increased
heavily since 2016 (Chart 1). [#f1]_

(Chart 1 here - show usage)

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