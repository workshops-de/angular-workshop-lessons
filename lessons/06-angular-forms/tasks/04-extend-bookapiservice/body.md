In order to send the book to our Backend we need to extend our BookApiService for another Request.

- Extend the `BookApiService` with a `create` method
- The method `create` should take a book (`Book`) as a parameter and send it with a POST request.
- Inject the service inside of the `BookNewComponent`
- Extract the form data from the `FormGroup` (you can use the  `getRawValue`-Function from the `FormGroup` for this)
- Call the `create` method from the `BookApiService` and give in the extracted form data

