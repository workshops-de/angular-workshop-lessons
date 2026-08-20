## API starten
If not already installed
```bash
# run bookmonkey-api directly
npx bookmonkey-api
```

```typescript
import { provideHttpClient } from '@angular/common/http';

providers: [provideHttpClient()]
```

```typescript
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';
```

```typescript
return this.http.get<Book[]>('http://localhost:4730/books')
```

```typescript
// ... using the service in the component (should already be done :-))
this.bookApiService.getBooks().subscribe(...
```

