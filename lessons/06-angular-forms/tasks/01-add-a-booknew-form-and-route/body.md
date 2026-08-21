- **Generate `BookNewPage`** Create a new Component `BookNewPage` for the Book-Feature with `ng generate component books/book-new/book-new-page`.
- **Add the route** Configure a new Route inside the `book.routes.ts` File, displaying the `BookNewPage` (path: new).
- **Link to it** Add a link from `BooksPage` with `routerLink` to the `new` route.

---

- **Set up the form group** Add `ReactiveFormsModule` to the imports-Array of `BookNewPage`. Inside the `book-new-page.ts`-File:
	- inject the `NonNullableFormBuilder` from `@angular/forms`
	- Create a `FormGroup` by calling the `group`-Function on the injected `NonNullableFormBuilder`
	- The formGroup should have Controls for  `isbn`,`author`,`title`,`subtitle`, and `abstract`

---

- **Build the template** Inside the `book-new-page.html`-File:
	- Add a `<form>`-Tag and bind the created `form` Property to the `[formGroup]`-Directive
	- For each created Control inside the FormGroup create one `<input>`-Tag and bind the FormControl-Keys to the `formControlName`-Directive
	- Also add a Submit-Button with `type=submit`
	- In order to get notified if the user clicks on this button register to the `(ngSubmit)`-Event inside the `<form>`-Tag and bind it to a `submit()`-function
	- Implement this function as well inside the `book-new-page.ts`-File. Inside this function you can just log the `form` on the `console`

Run the application inside the Browser: You should see your form. After you filled it out and clicked on the Submit-Button you should see the whole `FormGroup`-Object inside your Browser Developer Console.
