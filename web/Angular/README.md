Introduction
------------

Structuring Angular projects can be intimidating for new comers. I will
give two examples: one for a small to medium sized application and
another one for larger applications.

 Small to medium sized applications
-----------------------------------

Let's say you want to create a small todo application using Angular. I
would use the following structure:

    .
    +-- views
    |   +-- view-one.html
    |   +-- view-two.html
    +-- app
    |   +-- controllers
    |   |  +-- controller.one.js
    |   |  +-- controller.two.js
    |   +-- services
    |   |  +-- service.one.js
    |   |  +-- service.two.js
    |   +-- directives
    |   |  +-- directive.one.js
    |   |  +-- directive.two.js
    |   +-- app.js
    +-- style
    |   +-- view-one.css
    |   +-- view-two.css
    |
    +-- test
    |   +-- directive.one.test.js
    |   +-- directive.two.test.js
    |   ...
    +-- index.html

As you have noticed, the high level orgnization of this structure is
based on Angular core functionnalites: seperation of html views and
JavaScript code into two folders, then seperation of JavaScript code
into different functionnalites (controllers, services, directives...).

The app.js file is the entry point for the whole application: where you
declare modules, specify the .config and .run of your application and
specify your routing strategy.

The index.html contains a placeholder for the first view and decalartion
of used internal and external JavaScript modules.

 Larger applications
--------------------

Now imagine you need to build a larger application with intrecate
buisness logic and many reusable components, nested views and
communication services.

You should then consider switching to the more involved following
structure:

    .
    +-- app
    |   +-- home
    |   |  +-- home.controller.js
    |   |  +-- home.service.js
    |   |  +-- home.html
    |   |  +-- home.css
    |   |  +-- home.test.js
    |   |  +-- home.js
    |   +-- search
    |   |  +-- search.controller.js
    |   |  +-- search.service.js
    |   |  +-- search.html
    |   |  +-- search.css
    |   |  +-- search.test.js
    |   |  +-- search.js
    |   +-- app.js
    +-- components
    |   +-- side-bar
    |   |  +-- side-bar.controller.js
    |   |  +-- side-bar.service.js
    |   |  +-- side-bar.html
    |   |  +-- side-bar.css
    |   |  +-- side-bar.test.js
    |   |  +-- side-bar.js
    |   +-- services
    |   |  +-- shop.service.js
    |   |  +-- shop.test.js
    |   |  +-- cache.service.js
    |   |  +-- cache.test.js
    |   ...
    +-- index.html

As you have noticed, the high level orgnization of this structure is
based on your application (rather than Angular) core functionnalites:
seperation of your application into the reusable bits (under the
components folder) and the main ones, which in turn are strutured as: a
controller, an html view, a css styling file, a test script and a module
and routing definition entry point.

Again, the app.js file is the entry point for the whole application.
However, you won't define different routes in this file. Instead, you
will do this in each different module in the app folder.

Finally, the index.html contains a placeholder for the first view and
decalartion of used internal and external JavaScript modules.

Remarks
-------

-   In both structres, I have omitted the inclusion of many files and
    folders that aren't specific to Angular such as:

        - .gitignore
        - bower.json
        - Gruntfile.js (or gulpfile.js)
        - package.json
        - assets (where you place images, icons...)

-   The simple and more complex structures could be combined and adapted
    for your own needes.

Resources
---------

-   A very good read to start structuring you applications:
    https://scotch.io/tutorials/angularjs-best-practices-directory-structures
