It is time to allow our component to communicate with other components.

- Open _src/app/book-card/book-card.component.ts_
- Initialize a property `detailClick` with an `output()` signal.
- Type the `output()` signal to accept a `Book` as event payload.
	- Make sure `output` are imported from `@angular/core`.
- Emit the `detailClick`-Event within `handleDetailClick` method.
- Switch to _src/app/app.component.html_
- Bind to the `detailClick`-Event of _<app-book-card>_ to a method `goToBookDetails($event)`
- Implement `goToBookDetails($event)` and log the book passed by _<app-book-card>_

<iframe src="https://docs.google.com/presentation/d/1KJMDvEUIWDHluMPLffiBnadVSO2IElTAs7jPsMadehw/embed#slide=id.gab308489f3_0_122" height="700px" width="100%"></iframe>
