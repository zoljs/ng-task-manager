# ng-task-manager

A task management application built with Angular 18 while following Maximilian Schwarzmuller's [The Complete Guide to Angular](https://www.udemy.com/course/the-complete-guide-to-angular-2/) on Udemy.

## What I learned building this

### Angular module system

The project uses NgModule-based architecture. I learned how to split an app into feature modules (`TasksModule`) and shared modules (`SharedModule`), and why `BrowserModule` belongs only in `AppModule` while feature modules use `CommonModule`. Scoping `FormsModule` to only the modules that need it was a non-obvious but important detail.

### Component communication with @Input and @Output

`@Input` passes data down the tree; `@Output` with `EventEmitter` bubbles events back up. The `required: true` option on `@Input` gives a compile-time error if a parent forgets to pass a value.

### Service injection and singletons

`TasksService` uses `@Injectable({ providedIn: 'root' })`, making it a singleton. I also learned both injection styles Angular supports: constructor injection and the `inject()` function.

### Template-driven forms and localStorage

`[(ngModel)]` two-way binding handles form state, with `(ngSubmit)` wiring up submission. The service persists tasks to `localStorage` on every mutation and rehydrates from it in the constructor, so data survives a page refresh without a backend.

### New control flow syntax

Angular 17's `@if` and `@for` replace `*ngIf` and `*ngFor`. The `track` expression in `@for` is mandatory.

## Stack

- Angular 18 (NgModule, not standalone - though the entire project started out as standalone modules)
- TypeScript
- Angular Forms
- localStorage for persistence
- Bun
