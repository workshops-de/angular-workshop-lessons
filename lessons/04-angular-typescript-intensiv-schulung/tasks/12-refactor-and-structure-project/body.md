Now we want to structure our app into features. Therefore we create a new folder for our book feature.

- Create a component that will take all the code of _AppComponent_: `ng generate component book/book`.
- Move all book related code to the `book/`-folder.
  - _book.ts_
  - _book-card/_
  - _book-filter/_
- Open _app.component.ts_.
  - Move all book related code to the newly created _book.component.ts_.
  - Move  _BookCardComponent_ & _BookFilterPipe_ from `imports` array in _app.component.ts_ to `imports` array in _book.component.ts_
  - Add  _BookComponent_ to the `imports` array of _app.component.ts_.
  - Transfer all properties and methods of _AppComponent_ to _BookComponent_.
- Transfer the content of _app.component.html_ to _book.component.html_.
- Transfer the content of _app.component.scss_ to _book.component.scss_.
- Open app.component.html
- Add `<app-book></app-book>` to the template.
- Check if all `imports`-statements are correct.

> *Often the import-Statements are updated automatically by your editor, but sometimes the end result is not perfect. If you experience that your app does not compile, check & correct the import-Statements.*
- *If it still not works, reboot the Angular CLI.*
- *If it still not works, consult your trainer.*
