- Create a new Component `BookNewComponent` for the Book-Feature with `ng generate component book/book-new`
- Configure a new Route inside the `book.routes.ts` File, displaying the `BookNewComponent` (path: new)
- Add a link from `BookComponent` with `routerLink` to the `new` route.
- Add `ReactiveFormsModule` to the imports-Array of the `BookNewComponent` 
- Inside the `book-new.component.ts`-File:
	- inject the `FormBuilder` from `@angular/forms`
	- Create a `FormGroup` by calling the `group`-Function on the injected `FormBuilder` 
	- The formGroup should have Controls for  `isbn`,`author`,`title`,`subtitle`, and`abstract`
- Inside the `book-new.component.html`-File:	
	- Add a `<form>`-Tag and bind the created `form` Property to the `[formGroup]`-Directive
	- For each created Control inside the FormGroup create one `<input>`-Tag and bind the FormControl-Keys to the `formControlName`-Directive
	- Also add a Submit-Button with `type=submit`
	- In order to get notified if the user clicks on this button need to register to the `(ngSubmit)`-Event inside the `<form>`-Tag and bind it to a `submit()`-function 
	- you need to implement this function as well inside the `book-new.component.ts`-File. Inside this function you can just log the `form` on the `console` 

Run the application inside the Browser: You should see your form. After you filled it out and clicked on the Submit-Button you should see the whole `FormGroup`-Object inside your Browser Developer Console.
