```ts
// book-filter.pipe.ts
// filters an array and checks if the title contains 'Hello'
books.filter((book) => book.title.includes('Hello'))

```

```html
<!-- app.component html -->

<!-- search input -->
<input (input)="updateBookSearchTerm($event)">

<!--  use pipe -->
@for(book of books | bookFilter: bookSearchTerm; track book.title){
<app-book-card ...>
	...
```

```ts
// app.component.ts

// store input value in property
updateBookSearchTerm(input: Event) {
  this.bookSearchTerm = (input.target as HTMLInputElement).value;
  //                                  ^ tells the TypeScript-Compiler to treat the target property as HTMLInputElement
}
```
