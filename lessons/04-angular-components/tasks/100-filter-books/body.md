Since we add more and more books to our list, a filter is helpful to focus the book you want to know more about.

- **Extract a `BooksPage` component** Create a new component `src/app/books/books-page.ts` (selector `app-book`) that owns the `books` list, `bookSearchTerm` and `goToBookDetails` currently living in _App_. Move the `@for`-loop rendering `<app-book-card>` from _app.html_ into _books-page.html_. Import `BooksPage` in _App_ and replace the content of _app.html_ with `<app-book />`.

---

- **The Book filter pipe** Create a pipe using the CLI: `ng generate pipe books/book-filter/book-filter`. Open _src/app/books/book-filter/book-filter.ts_ and enhance the `transform` method of the pipe to filter books by **title**.

---

- **The Book filter control** Switch to _books-page.html_ and add an _<input>_-Field acting as search field. Handle its `(input)`-Event by binding it to a method called `updateBookSearchTerm($event.target.value)`. Implement the method `updateBookSearchTerm(searchTerm: string)` in _books-page.ts_ and store the search term in a `signal` property called `bookSearchTerm`.

---

- **Use the bookFilter-Pipe** Open _books-page.ts_ and add `BookFilter` to the `imports` array. Open _books-page.html_ and enhance the `@for`-expression by using the `bookFilter`-Pipe. Pass the current value of `bookSearchTerm` to the pipe.

---

- **Check the result** Open the browser at [localhost:4200](http://localhost:4200) and check if the filter works as expected.
