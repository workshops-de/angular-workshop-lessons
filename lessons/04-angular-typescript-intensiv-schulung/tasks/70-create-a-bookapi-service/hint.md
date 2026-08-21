## Generate with Angular CLI

```bash
ng generate service books/books-client
```

## Injecting the service

```typescript
// books-page.ts
private readonly booksClient = inject(BooksClient);
```
