```typescript
// books-client.ts
create(book: Partial<Book>): Observable<Book> {
  return this.http.post<Book>('http://localhost:4730/books', book)
}
```

```typescript
// book-new-page.ts
private readonly booksClient = inject(BooksClient);
...
submit() {
  this.booksClient.create(this.form.getRawValue()).subscribe()
}
```
