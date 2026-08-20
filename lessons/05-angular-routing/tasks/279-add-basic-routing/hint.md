** NavigationComponent **
```html
<ul>
  <li><a routerLink="/books">Books</a></li>
  <li><a routerLink="/about">About</a></li>
</ul>
```

**Book Routes:**
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
    component: BookComponent
  },
  {
    path: 'about',
    component: AboutComponent
  }
];
```

```ts
// app.config.ts
// ...
import { provideRouter } from '@angular/router';
// ...

export const appConfig: ApplicationConfig = {
  providers: [provideHttpClient(), provideRouter(routes)]
};
```

**Router outlet and router link:**

```ts
// app.component.ts
@Component({
  selector: 'app-root',
  // ...
  imports: [RouterOutlet],
  // ...
})
export class AppComponent {}
```

```html
<router-outlet></router-outlet>
```
