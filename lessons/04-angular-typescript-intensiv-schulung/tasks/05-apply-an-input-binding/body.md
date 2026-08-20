Now, it is time to feed our component with data using an `input()`-Binding.

- Open `src/app/book-card/book-card.component.ts`.
- Add a property `content`  and use the `input()` signal function with type `any` (do not forget to add the import from `@angular/core`).
- Switch to the template of _BookCardComponent_ component.
- Bind the values coming with `content` using binding expression (e.g.`{{ content().title }}`).
- Switch to the `src/app/app.component.ts`.
- Initialize a property `book` as object with the properties _title_, _author_, _abstract_.
- Switch to the template of _AppComponent_.
- Bind the property `book` to the component `app-book-card` using its `input()`-binding **[content]**.

<iframe src="https://docs.google.com/presentation/d/1KJMDvEUIWDHluMPLffiBnadVSO2IElTAs7jPsMadehw/embed#slide=id.ga8afa0fa9e_0_24" height="800px" width="100%"></iframe>
