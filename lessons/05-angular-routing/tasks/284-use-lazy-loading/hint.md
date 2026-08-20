```ts
// app.routes.ts
export const routes: Routes = [
  {
    path: '',
    pathMatch: 'full',
    redirectTo: '/about'
  },
  {
    path: 'books',
    loadChildren: () => import('./book/book.routes').then(module => module.bookRoutes)
  },
  {
    path: 'about',
    component: AboutComponent
  }
];
```

```ts
// book.routes.ts
export const bookRoutes: Routes = [
  {
    path: '',
    component: BookComponent
  },
  {
    path: 'detail/:isbn',
    component: BookDetailComponent
  }
];
```

### Lazy load a single component

```ts
{
    path: 'detail/:isbn',
    loadComponent: () =>
      import('./book-detail/book-detail.component').then(c => c.BookDetailComponent)
 }
```
