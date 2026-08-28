So far you tested **components** through the DOM. The piece that actually talks to the backend — `BooksClient` (`src/app/books/books-client.ts`) — deserves its own focused test: no component, no template, just the service and a **fake HTTP backend**. Angular's `provideHttpClientTesting()` swaps the real HTTP handler for one that never hits the network — every request is captured and answered by _you_, via **`HttpTestingController`**.

- **Create the spec file** `src/app/books/books-client.spec.ts`.

---

- **Write a `describe('BooksClient', ...)`-block** with two module-level `Book` fixtures (`mobyDick`, `friends` — reuse the shape from the previous tasks).

---

- Inside a `beforeEach()`:
  - `TestBed.configureTestingModule({ providers: [provideHttpClient(), provideHttpClientTesting()] })` (import `provideHttpClient` from `@angular/common/http`, `provideHttpClientTesting` from `@angular/common/http/testing`).
  - `httpMock = TestBed.inject(HttpTestingController);`
  - `booksClient = TestBed.inject(BooksClient);` — it's `providedIn: 'root'`, so no need to list it as a provider.
- Add an `afterEach(() => httpMock.verify());` — this fails the test if a request was fired that you never `expectOne`'d or `flush`'ed.
- **`it('requests all books via GET', ...)`**:
  - `let actual: Book[] | undefined;` then `booksClient.getAll().subscribe(books => (actual = books));`
  - `const req = httpMock.expectOne('http://localhost:4730/books');`
  - `expect(req.request.method).toBe('GET');`
  - `req.flush([mobyDick, friends]);` — this resolves the Observable synchronously.
  - `expect(actual).toEqual([mobyDick, friends]);`

---

- **`it('requests a single book by ISBN', ...)`**: same pattern for `booksClient.getByIsbn(mobyDick.isbn)`, expecting `http://localhost:4730/books/${mobyDick.isbn}`, method `GET`, `flush(mobyDick)`.

---

- **`it('sends a new book via POST', ...)`**:
  - `const draft: Partial<Book> = { title: 'Clean Code', author: 'Robert C. Martin', isbn: '978-0-13-235088-4', abstract: '', cover: '' };`
  - `booksClient.create(draft).subscribe();`
  - `const req = httpMock.expectOne('http://localhost:4730/books');`
  - `expect(req.request.method).toBe('POST');`
  - `expect(req.request.body).toEqual(draft);`
  - `req.flush({ ...draft });`

Run `npm test`.

> The `subscribe` + captured-variable style works because `flush()` delivers the response synchronously. If you prefer `async/await`, `const actual = await lastValueFrom(booksClient.getAll());` right after the `flush()` reads just as well.
