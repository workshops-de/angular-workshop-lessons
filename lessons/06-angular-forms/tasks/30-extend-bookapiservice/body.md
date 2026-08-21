In order to send the book to our Backend we need to extend our `BooksClient` for another Request.

- Extend `BooksClient` with a `create` method.
- The method `create` should take a book (`Partial<Book>`) as a parameter and send it with a POST request.
- Inject the service inside of `BookNewPage`.
- Extract the form data from the `FormGroup` (you can use the `getRawValue`-Function from the `FormGroup` for this).
- Call the `create` method from `BooksClient` and give in the extracted form data.
