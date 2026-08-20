- Create new component `AboutComponent` with `ng generate component about`
- Add a new file `app.routes.ts` beside of `app.config.ts`
- Add an exported constant `routes` as array with type `Routes`.
- Configure the start route, redirecting to `/about`.
- Configure a book route, displaying the `BookComponent` (path: _books_).
- Configure an about route, displaying the `AboutComponent` (path: _about_).
- Add Angular's `provideRouter` with the exported *routes* constant of `app.routes.ts` as argument to the `providers`-Array in `app.config.ts`.
- Open the template of `AppCompoent` ( _app.component.html_).
  - Replace its content with `router-outlet`. To activate the `router-outlet` you have to import the `RouterOutlet`-Directive in `imports` of the component declaration.
- You can test the navigation already by typing the different URLs in the browser.
- Add a simple `NavigationComponent` (`ng generate component navigation`), containing 2 links
  - Books
  - About
- Add the `NavigationComponent` at your desired place.
- Use the directive `routerLink` for the 2 links to navigate between the views (also do not forget the import of the `RouterLink`-Directive).

> Don't forget to remove <app-book> from your AppComponent's template, otherwise you will see it twice.
