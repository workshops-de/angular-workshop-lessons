```typescript
// books-page.ts
books$ = this.booksClient.getAll();
```

```html
<!-- books-page.html -->
  @for (book of books$ | async | bookFilter: bookSearchTerm(); track book.isbn) {
```
