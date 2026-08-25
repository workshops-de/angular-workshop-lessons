Since we add more and more books to our list, a filter is helpful to focus the book you want to know more about.

- **Extract a `BooksPage` component** Create a new component `src/app/books/books-page.ts` (selector `app-book`) that owns the `books` list, `searchTerm` and `goToBookDetails` currently living in _App_. Move the `@for`-loop rendering `<app-book-card>` from _app.html_ into _books-page.html_. Import `BooksPage` in _App_ and replace the content of _app.html_ with `<app-book />`.

---

- **The Book filter control** In _books-page.ts_ add a `signal` property called `searchTerm`. Switch to _books-page.html_ and add an _<input>_-Field acting as search field. Handle its `(input)`-Event by setting the signal directly: `searchTerm.set($event.target.value)`.

---

- **Derive the filtered books with `computed`** Open _books-page.ts_ and add a `computed` property called `booksComputed`. Inside its callback, read `searchTerm()` and the `books` list, and return only the books whose **title** contains the search term.

---

- **Use `booksComputed` in the template** Switch to _books-page.html_ and change the `@for`-expression to iterate over `booksComputed()` instead of `books`.

---

- **Check the result** Open the browser at [localhost:4200](http://localhost:4200) and check if the filter works as expected.
