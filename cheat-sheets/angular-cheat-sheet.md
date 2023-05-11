# Angular Cheat Sheet
===================

Contents
--------

### Starting a New Project

-   [Starting a New Project](#starting-a-new-project)

### Installing a Library

-   [Installing a Library](#installing-a-library)

### Creating Components

-   [Creating Components](#creating-components)

### Lifecycle Hooks

-   [Lifecycle Hooks](#lifecycle-hooks)

### Services

-   [Services](#services)

### Modules

-   [Modules](#modules)

### Angular Directives

-   [Angular Directives](#angular-directives)
-   [Attribute Directives](#attribute-directives)
-   [Structural Directives](#structural-directives)

### Custom Directives

-   [Custom Directives](#custom-directives)

### Pipes

-   [Pipes](#pipes)

### Decorators

-   [Decorators](#decorators)

### Useful Links

-   [Useful Links](#useful-links)

Starting a New Angular Project 
------------------------------

Before starting a new project, [Node.js](https://nodejs.org/en/) must be
installed on your machine. Next, Angular has an official CLI tool for
managing projects. It can be installed with NPM or Yarn.

``` {.language-bash .line-numbers style="counter-reset: linenumber NaN"}
# NPM
npm install -g @angular/cli

# Yarn
yarn global add @angular/cli
```

Afterward, we can create a new project with the following command:

``` {.language-bash .line-numbers style="counter-reset: linenumber NaN"}
ng new my-app
```

Angular will prompt you to configure the project. For the default
settings, you can press the **Enter** or **Return** keys. During the
installation process, Angular will scaffold a default project with
packages for running Angular.

You can run a project with either command:

``` {.language-bash .line-numbers style="counter-reset: linenumber NaN"}
# Development
ng serve 

# Production
ng build --prod 
```

Installing a Library {#installing-a-library}
--------------------

Without a doubt, you will find yourself installing 3rd party libraries
from other developers. Packages optimized for Angular may be installed
with a special command that will install and configure a package with
your project. If a package is not optimized for Angular, you have the
option of installing it the traditional way.

``` {.language-bash .line-numbers style="counter-reset: linenumber NaN"}
# Installation + Configuration
ng add @angular/material 

# Installation
npm install @angular/material
```

Creating Components {#creating-components}
-------------------

Components are the buildings blocks of an application. You can think of
them as a feature for teaching browsers new HTML tags with custom
behavior. Components can be created with the CLI. Typically, Angular
offers a shorthand command for those who prefer to be efficient.

``` {.language-bash .line-numbers style="counter-reset: linenumber NaN"}
# Common
ng generate component MyComponent

# Shorthand
ng g c MyComponent
```

Angular will generate the component files in a directory of the same
name. You can expect the following.

-   *.component.html** - The template of the component that gets
    displayed when the component is rendered.
-   *.component.css** - The CSS of a component, which is
    encapsulated.
-   *.component.js** - The business logic of a component to dictate
    its behavior.
-   *.component.spec.js** - A test file for validating the behavior
    and output of a component.

Along with creating the files, component classes are decorated with the
`@Component`{.language-text} decorator and registered with the closest
module. Here are some common helpful options:

  Option                                               Example                                             Description
  ---------------------------------------------------- --------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------
  `--dry-run`{.language-text} (`-d`{.language-text})   `ng g c MyComponent -d`{.language-text}             Does not output the result. Useful for keeping your command line clean.
  `--export`{.language-text}                           `ng g c MyComponent --export`{.language-text}       Exports the component in the module `exports`{.language-text} option.
  `--force`{.language-text} (`-f`{.language-text})     `ng g c MyComponent -f`{.language-text}             Forces a component to be created even if it already exists. Useful for overwriting files.
  `--help`{.language-text}                             `ng g c --help`{.language-text}                     Outputs a complete list of options for a given command.
  `--prefix`{.language-text} (`-p`{.language-text})    `ng g c MyComponent -p=base`{.language-text}        Custom prefix for a component HTML selector
  `--skip-tests`{.language-text}                       `ng g c MyComponent --skip-tests`{.language-text}   Skips creating the *.spec.ts** file.
  `--style`{.language-text}                            `ng g c MyComponent --style=scss`{.language-text}   A file extension or preproccessor for the style files. Can be set to `'none'`{.language-text} to skip generating a style file.

Lifecycle Hooks {#lifecycle-hooks}
---------------

Components emit events during and after initialization. Angular allows
us to hook into these events by defining a set of methods in a
component class. You can [dive deeper into hooks
here](https://angular.io/guide/lifecycle-hooks).

Here a quick rundown on the lifecycle hooks available:

-   `ngOnChanges`{.language-text}: Runs after an input/output binding
    has been changed.
-   `ngOnInit`{.language-text}: Runs after a component has been
    initialized. Input bindings are ready.
-   `ngDoCheck`{.language-text}: Allows developers to perform custom
    actions during change detection.
-   `ngAfterContentInit`{.language-text}: Runs after the content of a
    component has been initialized.
-   `ngAfterContentChecked`{.language-text}: Runs after every check of a
    component content.
-   `ngAfterViewInit`{.language-text}: Runs after the view of a
    component has been initialized.
-   `ngAfterViewChecked`{.language-text}: Runs after every check of a
    component view.
-   `ngOnDestroy`{.language-text}: Runs before a component is destroyed.

Services {#services}
--------

Services are objects for outsourcing logic and data that can be injected
into our components. Theye handy for reusing code in multiple
components. For medium-sized apps, they can serve as an alternative to
state management libraries.

We can create services with commands:

``` {.language-bash .line-numbers style="counter-reset: linenumber NaN"}
# Common
ng generate service MyService

# Shorthand
ng g s MyService
```

Services are not standalone. Typically, theye injected into other
areas of our app. Most commonly in components. There are two steps for
injecting a service. First, we must add the
`@Injectable()`{.language-text} decorator.

{.gatsby-highlight data-language="typescript"}
``` {.language-typescript .line-numbers style="counter-reset: linenumber NaN"}
import { Injectable } from '@angular/core';

@Injectable()
export class MyService {
  constructor() { }
}
```

Secondly, we must tell Angular *where* to inject this class. There are
three options at our disposal.

**1. Injectable Decorator**

This option is the most common route. It allows the service to be
injectable anywhere in our app.

{.gatsby-highlight data-language="typescript"}
``` {.language-typescript .line-numbers style="counter-reset: linenumber NaN"}
@Injectable({
  providedIn: 'root'
})
```

**2. Module**

This option allows a service to be injectable in classes that are
imported in the same module.

{.gatsby-highlight data-language="typescript"}
``` {.language-typescript .line-numbers style="counter-reset: linenumber NaN"}
@NgModule({
  declarations: [],
  imports: [],
  providers: [MyService}],
  bootstrap: []
})
```

**3. Component Class**

This option allows a service to be injectable in a single component
class.

{.gatsby-highlight data-language="typescript"}
``` {.language-typescript .line-numbers style="counter-reset: linenumber NaN"}
@Component({
  providers: [MyService]
})
```

Once youe got those two steps settled, a service can be injected into
the `constructor()`{.language-text} function of a class:

{.gatsby-highlight data-language="typescript"}
``` {.language-typescript .line-numbers style="counter-reset: linenumber NaN"}
import { Component } from '@angular/core';

@Component({
  selector: 'app-example',
  template: '<p>Hello World</p>',
  styleUrls: ['./example.component.css']
})
export class ExampleComponent {
  constructor(private myService: MyService) { }
}
```

Modules {#modules}
-------

Angular enhances JavaScript modularity with its own module system.
Classes decorated with the `@NgModule()`{.language-text} decorator can
register components, services, directives, and pipes.

The following options can be added to a module:

-   `declarations`{.language-text} - List of components, directives, and
    pipes that belong to this module.
-   `imports`{.language-text} - List of modules to import into this
    module. Everything from the imported modules is available to
    declarations of this module.
-   `exports`{.language-text} - List of components, directives, and
    pipes visible to modules that import this module.
-   `providers`{.language-text} - List of dependency injection providers
    visible both to the contents of this module and to importers of this
    module.
-   `bootstrap`{.language-text} - List of components to bootstrap when
    this module is bootstrapped.

Here an example of a module called `AppModule`{.language-text}.

{.gatsby-highlight data-language="typescript"}
``` {.language-typescript .line-numbers style="counter-reset: linenumber NaN"}
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';

import { AppRoutingModule } from './app-routing.module';
import { AppComponent } from './app.component';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

Angular Directives {#angular-directives}
------------------

Directives are custom attributes that can be applied to elements and
components to modify their behavior. There are two types of directives:
ttribute directivesand tructural directives

### Attribute Directives

An attribute directive is a directive that changes the appearance or
behavior of an element, component, or another directive. Angular exports
the following attribute directives:**`NgClass`{.language-text}**

Adds and removes a set of CSS classes.

{.gatsby-highlight data-language="html"}
``` {.language-html .line-numbers style="counter-reset: linenumber NaN"}
<!-- toggle the "special" class on/off with a property -->
<div [ngClass]="isSpecial ? 'special' : ''">This div is special</div>
```

**`NgStyle`{.language-text}**

Adds and removes a set of HTML styles.

{.gatsby-highlight data-language="html"}
``` {.language-html .line-numbers style="counter-reset: linenumber NaN"}
<div [ngStyle]="{
  'font-weight': 2 + 2 === 4 ? 'bold'   : 'normal',
}">
  This div is initially bold.
</div>
```

**`NgModel`{.language-text}**

Adds two-way data binding to an HTML form element. Firstly, this
directive requires the `FormsModule`{.language-text} to be added to the
`@NgModule()`{.language-text} directive.

{.gatsby-highlight data-language="typescript"}
``` {.language-typescript .line-numbers style="counter-reset: linenumber NaN"}
import { FormsModule } from '@angular/forms'; // <--- JavaScript import from Angular
/* . . . */
@NgModule({
  /* . . . */
  imports: [
    BrowserModule,
    FormsModule // <--- import into the NgModule
  ],
  /* . . . */
})
export class AppModule { }
```

Secondly, we can bind the `[(ngModel)]`{.language-text} directive on an
HTML `<form>`{.language-text} element and set it equal to the property.

{.gatsby-highlight data-language="html"}
``` {.language-html .line-numbers style="counter-reset: linenumber NaN"}
<label for="example-ngModel">[(ngModel)]:</label>
<input [(ngModel)]="currentItem.name" id="example-ngModel">
```

he gModeldirective has more customizable options that can be
ound
herehttps://angular.io/guide/built-in-directivesisplaying-and-updating-properties-with-ngmodel).

### Structural Directives

Structural directives are directives that change the DOM layout by
adding and removing DOM elements. Here are the most common structural
directives in Angular:

**`NgIf`{.language-text}**

A directive that will conditionally create or remove elements from the
template. If the value of the `NgIf`{.language-text} directive evaluates
to `false`{.language-text}, Angular removes the element.

{.gatsby-highlight data-language="html"}
``` {.language-html .line-numbers style="counter-reset: linenumber NaN"}
<p *ngIf="isActive">Hello World!</p>
```

**`NgFor`{.language-text}**

Loops through an element in a list/array.

{.gatsby-highlight data-language="html"}
``` {.language-html .line-numbers style="counter-reset: linenumber NaN"}
<div *ngFor="let item of items">{{item.name}}</div>
```

**`NgSwitch`{.language-text}**

An alternative directive for conditionally rendering elements. This
directive acts very similarly to the JavaScript `switch`{.language-text}
statement. There are three directives at our disposal:

-   `NgSwitch`{.language-text} --- A structural directive that should be
    assigned the value that should be matched against a series of
    conditions.
-   `NgSwitchCase`{.language-text} --- A structural directive that
    stores a possible value that will be matched against the
    `NgSwitch`{.language-text} directive.
-   `NgSwitchDefault`{.language-text} --- A structural directive that
    executes when the expression doesn match with any defined values.

{.gatsby-highlight data-language="html"}
``` {.language-html .line-numbers style="counter-reset: linenumber NaN"}
<ul [ngSwitch]="food">
  <li *ngSwitchCase="'Burger'">Burger</li>
  <li *ngSwitchCase="'Pizza'">Pizza</li>
  <li *ngSwitchCase="'Spaghetti'">Spaghetti</li>
  <li *ngSwitchDefault>French Fries</li>
</ul>
```

Custom Directives {#custom-directives}
-----------------

Wee not limited to directives defined by Angular. We can create
custom directives with the following command:

``` {.language-bash .line-numbers style="counter-reset: linenumber NaN"}
# Common
ng generate directive MyDirective

# Shorthand
ng g d MyDirective
```

To identify directives, classes are decorated with the
`@Directive()`{.language-text} decorator. Here what a common
directive would look like:

{.gatsby-highlight data-language="typescript"}
``` {.language-typescript .line-numbers style="counter-reset: linenumber NaN"}
import { Directive, ElementRef } from '@angular/core';

@Directive({
  selector: '[appMyDirective]'
})
export class appMyDirective {
  constructor(private elRef: ElementRef) {
    eleRef.nativeElement.style.background = 'red';
  }
}
```

Pipes {#pipes}
-----

Pipes are known for transforming content but not directly affecting
data. Theye mainly utilized in templates like so:

{.gatsby-highlight data-language="html"}
``` {.language-html .line-numbers style="counter-reset: linenumber NaN"}
{{ 'Hello world' | uppercase }}
```

Angular has a few pipes built-in.

**`DatePipe`{.language-text}**

Formats a date value according to locale rules.

{.gatsby-highlight data-language="html"}
``` {.language-html .line-numbers style="counter-reset: linenumber NaN"}
{{ value_expression | date: 'short' }}
```

**`UpperCasePipe`{.language-text}**

Transforms text to all upper case.

{.gatsby-highlight data-language="html"}
``` {.language-html .line-numbers style="counter-reset: linenumber NaN"}
{{ 'Hello world' | uppercase }}
```

**`LowerCasePipe`{.language-text}**

Transforms text to all lower case.

{.gatsby-highlight data-language="html"}
``` {.language-html .line-numbers style="counter-reset: linenumber NaN"}
{{ 'Hello World' | lowercase }}
```

**`CurrencyPipe`{.language-text}**

Transforms a number to a currency string, formatted according to locale
rules.

{.gatsby-highlight data-language="html"}
``` {.language-html .line-numbers style="counter-reset: linenumber NaN"}
{{ 1.3495 | currency:'CAD' }}
```

**`DecimalPipe`{.language-text}**

Transforms a number into a string with a decimal point, formatted
according to locale rules.

{.gatsby-highlight data-language="html"}
``` {.language-html .line-numbers style="counter-reset: linenumber NaN"}
{{ 3.14159265359 | number }}
```

**`PercentPipe`{.language-text}**

Transforms a number to a percentage string, formatted according to
locale rules.-

{.gatsby-highlight data-language="html"}
``` {.language-html .line-numbers style="counter-reset: linenumber NaN"}
{{ 0.259 | percent }}
```

Decorators {#decorators}
----------

Angular exports dozens of decorators that can be applied to classes and
fields. These are some of the most common decorators youl come
across.

  Decorator                              Example                                                                 Description
  -------------------------------------- ----------------------------------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  `@Input()`{.language-text}             `@Input() myProperty`{.language-text}                                   A property can be updated through property binding.
  `@Output()`{.language-text}            `@Output() myEvent = new EventEmitter();`{.language-text}               A property that can fire events and can be subscribed to with event binding on a component.
  `@HostBinding()`{.language-text}       `@HostBinding('class.valid') isValid`{.language-text}                   Binds a host element property (here, the CSS class valid) to a directive/component property (isValid).
  `@HostListener()`{.language-text}      `@HostListener('click', ['$event']) onClick(e) {...}`{.language-text}   A directive for subscribing to an event on a host element, such as a `click`{.language-text} event, and run a method when that event is emitted. You can optionally accept the `$event`{.language-text} object.
  `@ContentChild()`{.language-text}      `@ContentChild(myPredicate) myChildComponent;`{.language-text}          Binds the first result of the component content query (`myPredicate`{.language-text}) to a property (`myChildComponent`{.language-text}) of the class.
  `@ContentChildren()`{.language-text}   `@ContentChildren(myPredicate) myChildComponents;`{.language-text}      Binds the results of the component content query (`myPredicate`{.language-text}) to a property (`myChildComponents`{.language-text}) of the class.
  `@ViewChild()`{.language-text}         `@ViewChild(myPredicate) myChildComponent;`{.language-text}             Binds the first result of the component view query (`myPredicate`{.language-text}) to a property (`myChildComponent`{.language-text}) of the class. Not available for directives.
  `@ViewChildren()`{.language-text}      `@ViewChildren(myPredicate) myChildComponents;`{.language-text}         Binds the results of the component view query (`myPredicate`{.language-text}) to a property (`myChildComponents`{.language-text}) of the class. Not available for directives.

Useful Links {#useful-links}
------------

-   [Angular Documentation](https://angular.io/docs)
-   [Angular Devtools](https://angular.io/guide/devtools)
-   [Angular API Reference](https://angular.io/api)
-   [Angular Blog](https://blog.angular.io/)
-   [Angular Routing](https://angular.io/guide/routing-overview)
-   [Angular Forms](https://angular.io/guide/forms-overview)

#### **[Back To Top](#contents)**