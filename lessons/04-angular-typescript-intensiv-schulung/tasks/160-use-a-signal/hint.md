* The type of the Signal needs to be: `books: Signal<Book[] | undefined>;`
* Usage of toSignal(): `books = toSignal(this.booksClient.getAll());` — this works fine as a class field initializer, since it still runs inside the component's injection context.
* If you get an error in the browser `toSignal() can only be used inside of an injection context`, make sure the call is not wrapped in a callback or moved into a lifecycle hook.
* Usage of signal in template: `@for(book of books() | bookFilter: bookSearchTerm(); ...`
* Since `books()` can be undefined, it might be necessary to refactor the `BookFilter` pipe in order to accept `undefined`:
 `transform(books: Book[] | null | undefined, searchTerm: string | null): Book[] {`
