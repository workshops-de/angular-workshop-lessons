```typescript
// book.component.ts
this.books$ = this.bookApiService.getAll();
```

```html
<!-- book.component.html -->
  @for (book of books$ | async | bookFilter: searchTerm; track book.isbn) {
```
