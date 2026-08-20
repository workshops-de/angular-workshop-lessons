```ts
// src/app/book-card/book-card.component.ts

// Output-Binding
detailClick = output<Book>();

// Emit an event
this.detailClick.emit(this.content());
```

```ts
// src/app/app.component.ts

// handling detailClick-Event
goToBookDetails(book: Book) {
  console.log('Navigate to book details, soon...');
  console.table(book);
}
```
