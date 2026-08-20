```ts
// app.component.ts
export class AppComponent {
  book = {
    title: 'How to win friends',
    author: 'Dale Carnegie',
    abstract: 'In this book ...'
  };
}
```

```html
<!-- book-card.component.html -->
<h3>{{ content().title }}</h3>
<!-- ... -->
```

