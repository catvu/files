## AngularJS -> VueJS
Recently I see many posts talking about ReactJS vs AngularJS vs VueJS. 
My team just migrated the code from AngularJS 1.x to VueJS.
Here is my some experiences about the moving process:

### 1. Before Moving
We used AngularJS 1.x from 2014 with following features:
* View model binding (controller, view + template engine)
* Dependency Injection (services, factories, directives)
* Angular 3rd party components (uib-modal, ui-select, ...)
* Other pure in-house JS components

### 2. Problems with Angular 1
* Two-way data flow makes handling logic very difficult. The more variables we have, the more unexpected cases can happen. 
And as a consequence, writing controllers and components turned to be painful when the project scales up.
* Dependency injection is no longer needed. ES6 import/export can take that business and make everything explicit.
* Rendering performance is getting worse because of `$watch` and some other Angular functions.
* Angular documentation is very bad.

### 3. Why I choose VueJS not other frameworks (Angular2, ReactJS, EmberJS)
  
#### Angular 2
Angular 2 is even more confusing than Angular 1. There are many changes since this version: 
TypeScript, Template syntax, ... It's like the difference between Python 2.7 and Python 3.0. 
The migration path from version 1 to version 2 is not clearly too.
  
#### ReactJS
ReactJS is completely different from Angular 1. So, it will take a big effort to study and convert the code. 
Moreover, it's difficult to make the 'baby steps' for gradually migration. 

AngularJS is based on templating system (HTML-based) while ReactJS is based on JSX (JS-based). 
These two guys are hard to live together in the same project. 

Another reason is that, in my opinion, JSX is pretty lengthy.
  
#### EmberJS
EmberJS is the framework for SPA. It's not JS library.
    
#### VueJS
HTML template engine of VueJS is nearly the same to Angular 1. So, converting code is very easy (e.g. ng-repeat to v-for).

VueJS and Angular 1 can live together. So, it's possible for applying the changes steadily. 
This will reduce the risk of mistake making as well as the pressure from code migration.

Like ReactJS, VueJS uses 1-way data binding. This fixes problem of 2-ways data binding in Angular 1.

Vue documentation is extremely good (important point).

### 4. Migration Process & Results:
Overall, before migration, there were two main problems with our application:
1. Messy control flow logic
2. Angular 1 (stated above).

In the migration process, Vue's structure and convention (1-way data flow, component-based)
have forced me to refactor the code again. That help me solve first problem as well. When every logic flow is straightforward, moving to another 
framework in the future (such as ReactJS) is not a big deal.

Now we have moved 90% (phew). Clients didn't realize the changes because of gradually migration.

Benefits after migration:
* Clean code, modular (component-based)
* Vuex, Vue Store increase programming productivity
* Component tests are good & fast running
* Enhance UI performance

I think the key point of VueJS (or React) is that: It's not about the rich of libraries and components. It's about the framework structure which forces us to refactor our code to follow its mechanism.
That secures 3 properties for the code: Reusability, testability and maintainability.

**P/s**: We're still finding more engineers: full-stack / frontend / backend for ... refactoring and building product. 
Both junior and senior are welcome. Anyone interested, contact us via: [r.holistics.io/join](http://r.holistics.io/join)