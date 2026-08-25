## Storing the search term as a signal

```ts
// books-page.ts
bookSearchTerm = signal('');
```

## Wiring the search input

```html
<!-- books-page.html -->

<!-- search input, sets the signal directly -->
<input (input)="bookSearchTerm.set($event.target.value)" />
```

## Filtering with `computed`

```ts
// books-page.ts
import { computed, signal } from '@angular/core';

// filters the books array and checks if the title contains the search term
booksComputed = computed(() => {
  const searchTerm = this.bookSearchTerm().toLowerCase();

  return this.books.filter(book =>
    book.title.toLowerCase().includes(searchTerm)
  );
});
```

```html
<!-- books-page.html -->

<!-- use the computed signal -->
@for (book of booksComputed(); track book.title) {
<app-book-card ...> ...</app-book-card>
```
