# Beginner Angular Interview Questions

### Table of Contents

| No. | Questions |
|---- | --------- |
| 1 | [What is Angular Framework?](#what-is-angular-framework) |
| 2 | [What is the difference between AngularJS and Angular?](#what-is-the-difference-between-angularjs-and-angular) |
| 3 | [What is TypeScript?](#what-is-typescript) |
| 4 | [Write a pictorial diagram of Angular architecture?](#write-a-pictorial-diagram-of-angular-architecture) |
| 5 | [What are the key components of Angular?](#what-are-the-key-components-of-angular) |
| 6 | [What are directives?](#what-are-directives) |
| 7 | [What are components?](#what-are-components) |
| 8 | [What are the differences between Component and Directive?](#what-are-the-differences-between-component-and-directive) |
| 9 | [What is a template?](#what-is-a-template) |
| 10 | [What is a module?](#what-is-a-module) |
| 11 | [What are lifecycle hooks available?](#what-are-lifecycle-hooks-available) |
| 12 | [What is a data binding?](#what-is-a-data-binding) |
| 13 | [What is metadata?](#what-is-metadata) |
| 14 | [What is Angular CLI?](#what-is-angular-cli) |
| 15 | [What is the difference between constructor and ngOnInit?](#what-is-the-difference-between-constructor-and-ngoninit) |
| 16 | [What is the purpose of *ngFor directive?](#what-is-the-purpose-of-ngfor-directive) |
| 17 | [What is the purpose of *ngIf directive?](#what-is-the-purpose-of-ngif-directive) |
| 18 | [What is interpolation?](#what-is-interpolation) |
| 19 | [How do you categorize data binding types?](#how-do-you-categorize-data-binding-types) |
| 20 | [What are pipes?](#what-are-pipes) |
| 21 | [What is a bootstrapping module?](#what-is-a-bootstrapping-module) |
| 22 | [What are the various kinds of directives?](#what-are-the-various-kinds-of-directives) |
| 23 | [How do you create directives using CLI?](#how-do-you-create-directives-using-cli) |
| 24 | [Give an example for attribute directives?](#give-an-example-for-attribute-directives) |
| 25 | [What are the case types in Angular?](#what-are-the-case-types-in-angular) |
| 26 | [What are the class decorators in Angular?](#what-are-the-class-decorators-in-angular) |
| 27 | [How do you test Angular application using CLI?](#how-do-you-test-angular-application-using-cli) |
| 28 | [How do you find angular CLI version?](#how-do-you-find-angular-cli-version) |

---

1. ### What is Angular Framework?
    Angular is a **TypeScript-based open-source** front-end platform that makes it easy to build web, mobile and desktop applications. The major features of this framework include declarative templates, dependency injection, end to end tooling which ease application development.

    **[⬆ Back to Top](#table-of-contents)**

2. ### What is the difference between AngularJS and Angular?
    AngularJS (version 1.x) is a JavaScript framework, whereas Angular (version 2+) is a complete rewrite of AngularJS using TypeScript, providing better performance, mobile support, modularity, and a more modern architecture.

    Here are some of the major differences in tabular format:

    | AngularJS | Angular |
    |---- | --------- |
    | It is based on MVC architecture | This is based on Service/Controller |
    | It uses JavaScript to build the application | Uses TypeScript to build the application |
    | Based on controllers concept | This is a component based UI approach |
    | No support for mobile platforms | Fully supports mobile platforms |
    | Difficult to build SEO friendly application | Ease to build SEO friendly applications |

    **[⬆ Back to Top](#table-of-contents)**

3. ### What is TypeScript?
    TypeScript is a strongly typed superset of JavaScript created by Microsoft that adds optional types, classes, async/await and many other features, and compiles to plain JavaScript. Angular is written entirely in TypeScript as a primary language.
    You can install TypeScript globally as:
    ```cmd
    npm install -g typescript
    ```
    Example of TypeScript usage:
    ```typescript
    function greeter(person: string) {
        return "Hello, " + person;
    }

    let user = "Sudheer";
    document.body.innerHTML = greeter(user);
    ```

    **[⬆ Back to Top](#table-of-contents)**

4. ### Write a pictorial diagram of Angular architecture?
    The main building blocks of an Angular application are shown in the diagram below:
    ![Architecture](images/architecture.png)

    **[⬆ Back to Top](#table-of-contents)**

5. ### What are the key components of Angular?
    Angular has the following key components:
    1. **Component:** Basic building blocks of an Angular application to control HTML views.
    2. **Modules:** A set of basic building blocks like components, directives, services etc.
    3. **Templates:** Represent the views of an Angular application.
    4. **Services:** Used to create components which can be shared across the entire application.
    5. **Metadata:** Used to add more data to an Angular class.

    **[⬆ Back to Top](#table-of-contents)**

6. ### What are directives?
    Directives add behaviour to an existing DOM element or an existing component instance.
    ```typescript
    @Directive({ selector: '[myHighlight]' })
    export class HighlightDirective {
        constructor(el: ElementRef) {
           el.nativeElement.style.backgroundColor = 'yellow';
        }
    }
    ```
    ```html
    <p myHighlight>Highlight me!</p>
    ```

    **[⬆ Back to Top](#table-of-contents)**

7. ### What are components?
    Components are the most basic UI building block of an Angular app, which form a tree of Angular components. These components are a subset of directives. Unlike directives, components always have a template, and only one component can be instantiated per element in a template.

    **[⬆ Back to Top](#table-of-contents)**

8. ### What are the differences between Component and Directive?
    A component (@Component) is a directive-with-a-template.

    | Component | Directive |
    |---- | --------- |
    | Registered with @Component | Registered with @Directive |
    | Used to create UI widgets | Used to add behavior to existing DOM elements |
    | Breaks down app into smaller pieces | Designed for re-usable behavior |
    | One component per DOM element | Multiple directives per DOM element |
    | Template is mandatory | No template |

    **[⬆ Back to Top](#table-of-contents)**

9. ### What is a template?
    A template is a HTML view where you can display data by binding controls to properties of an Angular component. It can be defined inline using the `template` property or in a separate file using `templateUrl`.

    **[⬆ Back to Top](#table-of-contents)**

10. ### What is a module?
    Modules are logical boundaries in your application used to separate functionality. Every Angular app has at least one root module, usually named `AppModule`.

    **[⬆ Back to Top](#table-of-contents)**

11. ### What are lifecycle hooks available?
    Angular applications go through a set of processes from initiation to destruction.
    1. **ngOnChanges:** Called when a data-bound property changes.
    2. **ngOnInit:** Called after the first display of data-bound properties.
    3. **ngDoCheck:** For custom change detection.
    4. **ngAfterContentInit:** Called after content projection.
    5. **ngAfterContentChecked:** Called after checking projected content.
    6. **ngAfterViewInit:** Called after initializing component and child views.
    7. **ngAfterViewChecked:** Called after checking component and child views.
    8. **ngOnDestroy:** Cleanup phase before destruction.

    **[⬆ Back to Top](#table-of-contents)**

12. ### What is a data binding?
    Data binding defines communication between a component and the DOM.
    1. **Component to DOM:** Interpolation `{{ value }}` and Property binding `[property]="value"`.
    2. **DOM to Component:** Event binding `(event)="function"`.
    3. **Two-way binding:** `[(ngModel)]="value"`.

    **[⬆ Back to Top](#table-of-contents)**

13. ### What is metadata?
    Metadata decorates a class to configure its behavior.
    1. **Class decorators:** `@Component`, `@NgModule`.
    2. **Property decorators:** `@Input`, `@Output`.
    3. **Method decorators:** `@HostListener`.
    4. **Parameter decorators:** `@Inject`, `@Optional`.

    **[⬆ Back to Top](#table-of-contents)**

14. ### What is Angular CLI?
    Angular CLI is a command-line interface to scaffold and build Angular apps.
    - `ng new <project-name>`: Create new project.
    - `ng generate <type> <name>`: Generate components, services, etc.
    - `ng serve`: Run the project.

    **[⬆ Back to Top](#table-of-contents)**

15. ### What is the difference between constructor and ngOnInit?
    The **Constructor** is a default method of the class executed when the class is instantiated, mainly used for Dependency Injection.
    **ngOnInit** is a lifecycle hook called by Angular after it's done creating the component and resolving its bindings.

    **[⬆ Back to Top](#table-of-contents)**

16. ### What is the purpose of *ngFor directive?
    We use the `*ngFor` directive in the template to display each item in a list.
    ```html
    <li *ngFor="let user of users">
      {{ user }}
    </li>
    ```

    **[⬆ Back to Top](#table-of-contents)**

17. ### What is the purpose of *ngIf directive?
    The `*ngIf` directive inserts or removes an element based on a truthy/falsy condition.
    ```html
    <p *ngIf="user.age > 18">Eligible</p>
    ```

    **[⬆ Back to Top](#table-of-contents)**

18. ### What is interpolation?
    Interpolation is a special syntax that Angular converts into property binding, represented by double curly braces `{{}}`.

    **[⬆ Back to Top](#table-of-contents)**

19. ### How do you categorize data binding types?
    1. **Source-to-view:** Interpolation, Property, Attribute, Class, Style.
    2. **View-to-source:** Event binding.
    3. **Two-way:** `[(ngModel)]`.

    **[⬆ Back to Top](#table-of-contents)**

20. ### What are pipes?
    Pipes are simple functions that accept data as input and transform it into a desired output for the template.
    ```html
    <p>Birthday is {{ birthday | date }}</p>
    ```

    **[⬆ Back to Top](#table-of-contents)**

21. ### What is a bootstrapping module?
    The root module that you bootstrap to launch the application, commonly known as `AppModule`.

    **[⬆ Back to Top](#table-of-contents)**

22. ### What are the various kinds of directives?
    1. **Components:** Directives with a template.
    2. **Structural directives:** Change DOM layout (e.g., `*ngIf`, `*ngFor`).
    3. **Attribute directives:** Change appearance or behavior (e.g., `ngStyle`, `ngClass`).

    **[⬆ Back to Top](#table-of-contents)**

23. ### How do you create directives using CLI?
    Use the command:
    ```bash
    ng generate directive <name>
    ```

    **[⬆ Back to Top](#table-of-contents)**

24. ### Give an example for attribute directives?
    ```typescript
    @Directive({ selector: '[appHighlight]' })
    export class HighlightDirective {
        constructor(el: ElementRef) {
           el.nativeElement.style.backgroundColor = 'red';
        }
    }
    ```
    ```html
    <p appHighlight>Highlight me!</p>
    ```

    **[⬆ Back to Top](#table-of-contents)**

25. ### What are the case types in Angular?
    1. **camelCase:** properties, methods, pipe names.
    2. **UpperCamelCase:** class names (PascalCase).
    3. **dash-case:** file names, selectors (kebab-case).
    4. **UPPER_UNDERSCORE_CASE:** constants.

    **[⬆ Back to Top](#table-of-contents)**

26. ### What are the class decorators in Angular?
    - `@Component()`
    - `@Directive()`
    - `@Pipe()`
    - `@Injectable()`
    - `@NgModule()`

    **[⬆ Back to Top](#table-of-contents)**

27. ### How do you test Angular application using CLI?
    Run `ng test` to execute unit tests using Jasmine and Karma.

    **[⬆ Back to Top](#table-of-contents)**

28. ### How do you find angular CLI version?
    Use the command:
    ```bash
    ng version
    ```

    **[⬆ Back to Top](#table-of-contents)**
