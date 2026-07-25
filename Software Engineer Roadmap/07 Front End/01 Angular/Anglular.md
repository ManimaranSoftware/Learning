Topics

1. Components
2. Data Binding
3. Directives (ngIf, ngFor, ngClass)
4. Services & Dependency Injection
5. Routing
6. Lifecycle Hooks
7. RxJS & Observables
8. HTTP Client & API Calls
9. Forms

- Template-driven
- Reactive Forms

11. Pipes
12. Parent-Child Communication

- @Input
- @Output
- EventEmitter

12. State Management basics
13. Lazy Loading
14. Guards (CanActivate)
15. Interceptors
16. Change Detection
17. Signals (important in newer Angular versions)
18. Standalone Components
19. Authentication with JWT
20. Angular project structure & best practices

**Angular Interview Questions & Answers**

**1. Components**

**What is a Component in Angular?**

A Component is the basic building block of an Angular application.  
It controls a part of the UI called a view.  
A component contains:

- HTML template
- TypeScript class
- CSS styles

It is decorated using @Component.  
Angular applications are built using multiple reusable components.

Example:

@Component({  
 selector: 'app-home',  
 templateUrl: './home.component.html'  
})

---

**What is the difference between Component and Module?**

A Component controls UI and business logic for a specific screen or section.  
A Module groups related components, directives, pipes, and services together.

Component:

- Handles view
- Reusable UI part

Module:

- Organizes application features
- Declared using @NgModule

Angular app starts from AppModule.

---

**What is a Standalone Component?**

Standalone components are introduced to avoid unnecessary modules.  
They can work independently without declaring them inside NgModule.

Benefits:

- Cleaner structure
- Better performance
- Easier lazy loading

Example:

@Component({  
 standalone: true  
})

---

**2. Data Binding**

**What is Data Binding?**

Data Binding connects the component data with the HTML UI.  
It automatically synchronizes data between TS and HTML.

Types:

1. Interpolation
2. Property Binding
3. Event Binding
4. Two-way Binding

It reduces manual DOM manipulation.

---

**What is Interpolation?**

Interpolation displays component data in HTML using {{ }}.

Example:

<h1>{{title}}</h1>

It is one-way data binding from TS to HTML.  
Used for displaying strings, numbers, and variables.

---

**What is Two-Way Data Binding?**

Two-way binding updates both UI and component simultaneously.

Syntax:

[(ngModel)]

Example:

<input [(ngModel)]="username">

When input changes, variable updates automatically.  
Requires FormsModule.

---

**3. Directives**

**What are Directives?**

Directives are used to change the behavior or appearance of DOM elements.

Types:

1. Component Directives
2. Structural Directives
3. Attribute Directives

Examples:

- *ngIf
- *ngFor
- [ngClass]

---

**What is ngIf?**

ngIf conditionally adds or removes elements from DOM.

Example:

<div *ngIf="isLoggedIn">  
 Welcome  
</div>

If condition is true, element appears.  
If false, element is removed completely.

---

**What is ngFor?**

ngFor is used to iterate over collections like arrays.

Example:

<li *ngFor="let item of items">  
 {{item}}  
</li>

It dynamically creates HTML elements for each item.

---

**What is ngClass?**

ngClass dynamically adds or removes CSS classes.

Example:

<div [ngClass]="{'active': isActive}">

Useful for conditional styling.

---

**4. Services & Dependency Injection**

**What is a Service?**

Service contains reusable business logic or common functionality.

Examples:

- API calls
- Shared data
- Logging

Generated using:

ng generate service service-name

Helps maintain clean architecture.

---

**What is Dependency Injection?**

Dependency Injection (DI) is a design pattern where Angular automatically provides required objects.

Example:

constructor(private empService: EmployeeService){}

Benefits:

- Loose coupling
- Better testing
- Reusability

Angular has built-in DI framework.

---

**What are Service Lifetimes?**

Angular services mainly work as Singleton when provided in root.

providedIn: 'root'

Only one instance is shared across application.

Other scopes:

- Component level
- Module level

---

**5. Routing**

**What is Routing?**

Routing allows navigation between components/pages without reloading browser.

Configured in:

RouterModule.forRoot(routes)

Each route maps URL to component.

Example:

{ path: 'home', component: HomeComponent }

---

**What is Router Outlet?**

<router-outlet> acts as placeholder where routed component loads.

Example:

<router-outlet></router-outlet>

Without it, routing will not display component.

---

**What is Lazy Loading?**

Lazy Loading loads modules only when required.

Benefits:

- Faster initial load
- Better performance

Example:

loadChildren: () =>  
 import('./admin/admin.module')

Used in large applications.

---

**6. Lifecycle Hooks**

**What are Lifecycle Hooks?**

Lifecycle hooks are methods triggered during component lifecycle.

Common hooks:

- ngOnInit
- ngOnChanges
- ngOnDestroy

Used for initialization, cleanup, and data handling.

---

**What is ngOnInit?**

ngOnInit() executes after component initialization.

Used for:

- API calls
- Initial data loading

Example:

ngOnInit(){  
 this.loadData();  
}

Runs once.

---

**What is ngOnDestroy?**

ngOnDestroy() executes before component destruction.

Used to:

- Unsubscribe observables
- Clear timers
- Prevent memory leaks

Example:

ngOnDestroy(){  
 this.subscription.unsubscribe();  
}

---

**7. RxJS & Observables**

**What is Observable?**

Observable is used for asynchronous programming.

Commonly used in:

- HTTP calls
- Events
- Real-time updates

Example:

this.http.get().subscribe()

Observable emits multiple values over time.

---

**What is Subscribe?**

subscribe() is used to receive data from observable.

Example:

this.service.getData().subscribe(data=>{  
 console.log(data);  
});

Without subscribe, observable will not execute.

---

**Difference between Observable and Promise?**

Observable:

- Multiple values
- Lazy execution
- Can cancel subscription

Promise:

- Single value
- Executes immediately
- Cannot cancel

Angular prefers Observables.

---

**8. HTTP Client & API Calls**

**What is HttpClient?**

HttpClient is used for API communication.

Imported from:

HttpClientModule

Supports:

- GET
- POST
- PUT
- DELETE

Returns observables.

---

**How to make GET API call?**

Example:

constructor(private http: HttpClient){}  
  
this.http.get('api/url')  
.subscribe(res=>{  
 console.log(res);  
});

GET is used to retrieve data.

---

**How to handle API errors?**

Using catchError.

Example:

.pipe(  
 catchError(error=>{  
   return throwError(error);  
 })  
)

Helps avoid application crashes.

---

**9. Forms**

**Difference between Template-driven and Reactive Forms?**

Template-driven:

- Simple forms
- HTML-based
- Uses ngModel

Reactive Forms:

- Complex forms
- TS-based
- Better validation
- More scalable

Reactive forms preferred in enterprise apps.

---

**What is FormGroup?**

FormGroup groups multiple form controls.

Example:

this.form = new FormGroup({  
 name: new FormControl('')  
});

Used in reactive forms.

---

**What are Validators?**

Validators are used for form validation.

Examples:

- required
- minlength
- pattern

Example:

Validators.required

Helps ensure valid user input.

---

**10. Pipes**

**What are Pipes?**

Pipes transform displayed data in templates.

Examples:

- date
- uppercase
- currency

Example:

{{amount | currency}}

Does not modify original data.

---

**What is Custom Pipe?**

Custom pipes are user-defined transformations.

Created using:

ng generate pipe pipe-name

Example:

transform(value:string){  
 return value.toUpperCase();  
}

---

**11. Parent-Child Communication**

**What is @Input?**

@Input sends data from parent to child.

Example:

@Input() name:string;

Parent:

<app-child [name]="username"></app-child>

---

**What is @Output?**

@Output sends data from child to parent.

Uses EventEmitter.

Example:

@Output() notify = new EventEmitter();

---

**12. State Management**

**What is State Management?**

State management handles shared application data.

Used in:

- Large applications
- Multiple component communication

Popular libraries:

- NgRx
- Signals

Improves predictability.

---

**13. Guards**

**What are Route Guards?**

Guards protect routes from unauthorized access.

Types:

- CanActivate
- CanDeactivate
- Resolve

Example:

canActivate(): boolean{  
 return this.authService.isLoggedIn();  
}

---

**14. Interceptors**

**What is Interceptor?**

Interceptor intercepts all HTTP requests and responses.

Uses:

- Add JWT token
- Logging
- Error handling

Example:

intercept(req,next)

Very commonly asked.

---

**15. Change Detection**

**What is Change Detection?**

Angular automatically updates UI when data changes.

Default strategy checks entire component tree.

Optimized using:

ChangeDetectionStrategy.OnPush

Improves performance.

---

**16. Signals**

**What are Signals?**

Signals are Angular's new reactive state management feature.

Example:

count = signal(0);

Benefits:

- Better performance
- Simpler reactivity
- Fine-grained updates

Important in latest Angular versions.

---

**17. JWT Authentication**

**What is JWT Token?**

JWT (JSON Web Token) is used for authentication.

Flow:

1. User logs in
2. Server sends token
3. Client stores token
4. Token sent in headers

Used for secure APIs.

---

**Where do you store JWT token?**

Usually stored in:

- LocalStorage
- SessionStorage

Sent using interceptor:

Authorization: Bearer token

---

**18. Angular Project Structure**

**Explain Angular Project Structure**

Important folders:

- src/app → components/services
- assets → static files
- environments → configs

Important files:

- angular.json
- package.json
- main.ts

Structure helps maintain scalability.

---

**19. Frequently Asked Difference Questions**

**Difference between Constructor and ngOnInit**

Constructor:

- Dependency Injection
- Executes first

ngOnInit:

- Component initialization
- API calls

Avoid heavy logic in constructor.

---

**Difference between Subject and BehaviorSubject**

Subject:

- No initial value
- New subscribers get future values only

BehaviorSubject:

- Requires initial value
- New subscribers receive latest value immediately

---

**Difference between ngIf and hidden**

ngIf:

- Removes element from DOM

hidden:

- Hides element using CSS
- Element still exists in DOM

ngIf is better for performance.

---

**20. Scenario-Based Questions**

**How will you share data between unrelated components?**

Using:

- Shared service
- BehaviorSubject

Service stores data and components subscribe to updates.

Most common enterprise approach.

---

**How do you improve Angular performance?**

Methods:

- Lazy loading
- OnPush change detection
- TrackBy in ngFor
- Avoid unnecessary API calls
- Unsubscribe observables

---

**How do you prevent memory leaks?**

By unsubscribing observables in:

ngOnDestroy()

Or using:

- async pipe
- takeUntil

Very important interview question.