## Filtering inside the pipe

```ts
// book-filter.ts
// filters an array and checks if the title contains 'Hello'
books.filter((book) => book.title.includes('Hello'))
```

## Wiring the search input

```html
<!-- books-page.html -->

<!-- search input -->
<input (input)="updateBookSearchTerm($event.target.value)">

<!--  use pipe -->
@for(book of books | bookFilter: bookSearchTerm(); track book.title){
<app-book-card ...>
	...
```

## Storing the search term as a signal

```ts
// books-page.ts
bookSearchTerm = signal('');

// store input value in the signal
updateBookSearchTerm(searchTerm: string) {
  this.bookSearchTerm.set(searchTerm);
}
```
