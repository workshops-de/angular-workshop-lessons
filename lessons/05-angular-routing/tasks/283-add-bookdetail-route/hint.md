**Implement the Component**
 
```ts
// book-detail.component.ts

import { ActivatedRoute } from '@angular/router';

private readonly route  = inject(ActivatedRoute);
private readonly bookApi  = inject(BookApiService);
```

```ts
ngOnInit () {
  this.route.params.subscribe((params) => { ... });
}
```

**Extend BookComponent**

```ts
// book.component.ts

private readonly router  = inject(Router);
private readonly bookApi  = inject(BookApiService);

goToBookDetails(book: Book) {
  this.router.navigate(['books', 'detail', book.isbn]);
}
```


**Extend your routes definitions**

```ts
// app.routes.ts

{ path: 'books/detail/:isbn', component: BookDetailComponent }
```

**Extend and use the Service with a getBookByIsbn(isbn: string)**
```
HTTP GET http://localhost:4730/books/:isbn
```
