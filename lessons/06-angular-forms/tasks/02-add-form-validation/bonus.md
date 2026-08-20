## Make your FormGroup Typesafe

- Create an Interface for your FromGroup: `interface BookForm = { ... }`
- Make your `form` typesafe by adding your created Type: `form: FormGroup<BookForm> = ...`
