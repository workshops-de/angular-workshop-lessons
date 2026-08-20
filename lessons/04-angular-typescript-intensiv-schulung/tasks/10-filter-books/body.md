Since we add more and more books to our list, a filter is helpful to focus the book you want to know more about.

**The Book filter pipe**
- Create a pipe using the CLI: `ng generate pipe book-filter/book-filter`.
- Open _src/app/book-filter/book-filter.pipe.ts_.
- Enhance the `transform` method of the pipe to filter books by **title**.

**The Book filter control**
- Switch to _src/app/app.component.html_
- Add an _<input>_-Field acting as search field.
- Handle its `(input)`-Event by binding it to a method called `updateBookSearchTerm($event)`.
- Implement the method `updateBookSearchTerm` in _app.component.ts_.
- Extract the value of the input field from the `Event` and store the search term in a property called `bookSearchTerm`.

**Use the bookFilter-Pipe**
- Open _app.component.ts_.
- Add `BookFilterPipe` to `imports` array.
- Open _app.component.html_.
- Enhance the `@for`-expression by using the `bookFilter`-Pipe.
- Pass the value of the _<input>_-Field to the pipe by adding the parameter `bookSearchTerm`

**Check the result**
- Open the browser at [localhost:4200](http://localhost:4200)
- Check if the filter works as exepected


