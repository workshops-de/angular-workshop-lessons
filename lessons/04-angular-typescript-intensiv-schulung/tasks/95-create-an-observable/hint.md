## Imports

```typescript
import { Observable, of } from 'rxjs';
```

## getAll()

```typescript
return of(this.books);
```

## Subscribing in BooksPage

```typescript
this.booksClient.getAll().subscribe(booksFromService => this.books.set(booksFromService));
```
