## Lazy load the book route

- Create a new file `book.routes.ts` inside the book folder to configure child routes.
- Transfer the routes _books/detail_ & _books_ from  _app.routes.ts_ to `book.routes.ts`.
  - Pay attention to the hints: The paths will slightly change.
- Add a lazy loaded route for the path `books` loading the `book.routes.ts` in _app.routes.ts_.
- Make sure that the compiler in your terminal shows _lazy chunk files_ in the output.
- Open your app in the browser
- Open the Developer Tools -> Open the Network Tab and check the chunk bundles in the list of network requests in the brower dev tools.

## Lazy load the book details route

- We can be even more lazy
- The `BookDetailsComponent` might not me loaded up front
- use `loadComponent` to load it lazily
- Verify that a several chunk is generated and loaded for `BookDetailsComponent`
