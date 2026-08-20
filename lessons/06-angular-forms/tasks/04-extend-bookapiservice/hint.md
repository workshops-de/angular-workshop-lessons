```typescript
// book-api.service.ts
create(book: Book): Observable<Book> {
  return this.http.post<Book>('http://localhost:4730/books', book)
}
```

```typescript
// book-new.component.ts
private bookApiService = inject(BookApiService)
...
submit() {
  this.bookApiService.create(this.form.getRawValue() as Book).subscribe()
}
```
