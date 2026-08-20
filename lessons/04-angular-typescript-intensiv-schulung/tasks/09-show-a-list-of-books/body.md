We already have a component being capable of rendering a book.
Let's instrument the component to render a whole list.

- Open _src/app/app.component.ts_.
- Rename the property _book_ to _books_.
- Change the type of `books` from `Book` to `Book[]` .
- Wrap your book with an array ([ ] / square-brackets).
- Add at least one additional book to your list.
- Switch to the template of _AppComponent_.
- Use Control Flow `@for` to render all books of your list.
- Have a look at the browser to check the result.
