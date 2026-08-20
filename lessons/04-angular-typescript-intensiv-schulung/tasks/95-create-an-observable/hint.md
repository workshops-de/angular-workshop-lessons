**imports**
```typescript
import { Observable, of } from 'rxjs';
```

**getAll()**
```typescript
return of(this.books);
```

**Component**
```typescript
...getAll().subscribe({ next: booksFromApi => /* assign to books */})
```
