```ts
// app.component.ts
books: Book[] = [
  {
    title: 'How to win friends',
    author: 'Dale Carnegie',
    abstract: "How to Win Friends and Influence ..."
  },
  {
    title: 'The Willpower Instinct: How Self-Control Works ...',
    author: 'Kelly McGonigal',
    abstract: 'Based on Stanford University ...'
  },
  {
    author: 'Simon Sinek',
    title: 'Start with WHY',
    abstract: "START WITH WHY shows that the leaders who've ..."
  }
];
```

```html
<!-- app.component.html -->
@for(book of books; track book.title){
  <app-book-card ... >
}
```
