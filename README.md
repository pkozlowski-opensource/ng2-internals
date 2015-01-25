# ng-internals 2.0

by Pawel Kozlowski

![Creative Commons License](http://i.creativecommons.org/l/by-nc-nd/3.0/88x31.png)


A set of in-depth, code-level design documents for [Angular 2.0](https://github.com/angular/angular) describing the main interfaces and their interactions.
The ultimate goal is to make it easier for people to contribute fixes and new features and 3rd party modules to Angular2 ecosystem. Hopefully this text will also come handy for more advanced framework users and 3rd party library authors who look for more advanced info on inner workings of Angular2.

# TOC

* [Prerequisites](prerequisites.md))
* Key concepts
* Inner working
    * The big picture
    * Bits and pieces
        * [Expressions](details/expressions.md): parsing and evaluating
        * Change detection
            * Detecting changes in a given expression
            * Zones: triggering expressions - re-evaluation
        * Dependency Injection
        * Compiler pipeline
        * ATScript and reflection
    * Putting it all together
* Contributting to Angular2
    * Development environment
    * Building and testing
    * Performance monitoring

## Copyright and License

  Copyright 2015 Pawel Kozlowski

  This work is licensed under a [Creative Commons Attribution-NonCommercial-NoDerivs 3.0 Unported License](http://creativecommons.org/licenses/by-nc-nd/3.0/).