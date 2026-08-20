* The type of the Signal needs to be: `books: Signal<Book[] | undefined>;`
* Usage of toSignal(): `this.books = toSignal(this.bookApi.getAll());` and move this line into the constructor!
* If you get an error in the browsser `toSignal() can only be used inside of an injection context` see hint above (move line into the constructor)
* Usage of signal in template: `@for(book of books() | bookFilter: bookSearchTerm;...`
* Since books() can be undefined, it might be necessary to refactor bookFilter pipe in order to accept `undefined`:
 `transform(books: Book[] | null | undefined, searchTerm: string | null): Book[] {`
