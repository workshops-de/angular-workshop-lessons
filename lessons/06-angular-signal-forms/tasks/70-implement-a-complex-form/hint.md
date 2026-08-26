```typescript
// books-client.ts
update(isbn: string, book: Partial<Book>): Observable<Book> {
  return this.http.put<Book>(`${this.baseUrl}/books/${isbn}`, book);
}
```

```typescript
// book-edit-page.ts
import { Component, effect, inject, input, signal } from '@angular/core';
import { toObservable, toSignal } from '@angular/core/rxjs-interop';
import { form, FormField, FormRoot, readonly, required } from '@angular/forms/signals';
import { firstValueFrom, switchMap } from 'rxjs';
import { BooksClient } from '../books-client';
import { validAuthorName } from '../validators/author';

const emptyBookForm = { isbn: '', title: '', subtitle: '', author: '', abstract: '' };

@Component({
  selector: 'app-book-edit',
  imports: [FormField, FormRoot],
  templateUrl: './book-edit-page.html'
})
export class BookEditPage {
  private readonly booksClient = inject(BooksClient);
  protected readonly isbn = input.required<string>();

  private readonly book = toSignal(
    toObservable(this.isbn).pipe(switchMap(isbn => this.booksClient.getByIsbn(isbn)))
  );

  protected readonly model = signal(emptyBookForm);

  constructor() {
    effect(() => {
      const loadedBook = this.book();
      if (loadedBook) {
        this.model.set({ ...emptyBookForm, ...loadedBook });
      }
    });
  }

  protected readonly form = form(
    this.model,
    schemaPath => {
      readonly(schemaPath.isbn);
      required(schemaPath.title, { message: 'Please insert a title.' });
      required(schemaPath.author, { message: 'Please insert an Author.' });
      validAuthorName(schemaPath.author);
    },
    {
      submission: {
        action: async () => {
          await firstValueFrom(this.booksClient.update(this.isbn(), this.model()));
          return null;
        }
      }
    }
  );
}
```

```html
<!-- book-detail-page.html -->
<a [routerLink]="['/books/edit', book.isbn]">Edit</a>
```
