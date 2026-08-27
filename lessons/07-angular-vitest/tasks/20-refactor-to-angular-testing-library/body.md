Testing through `TestBed` directly involves a lot of repetitive boilerplate: manual change detection, DOM querying by tag or CSS-selector, and coupling your test to markup details that have nothing to do with what you're actually testing. **Angular Testing Library** (ATL) wraps `TestBed` and nudges you towards accessible, user-centric tests instead — "the more your tests resemble the way your software is used, the more confidence they can give you."

`@testing-library/angular`, `@testing-library/user-event` and `@testing-library/jest-dom` are already installed in this project.

- **Rewrite `book-card.spec.ts`** to use ATL instead of raw `TestBed`:
  - Replace `TestBed.configureTestingModule` + `createComponent` + `setInput` + `detectChanges` with a single `await render(BookCard, { componentInputs: { content: book } })` call from `@testing-library/angular`.
  - Replace `fixture.nativeElement.querySelector('h3')` with `screen.getByText(book.title)` and assert it `.toBeInTheDocument()`.
  - For the emission test, pass a `vi.fn()` as `componentOutputs: { detailClick }`.
  - Replace the manual `.click()` with `@testing-library/user-event`: create `const user = userEvent.setup();`, then `await user.click(screen.getByRole('link', { name: /details/i }));`.
  - Assert the emission with `expect(detailClick).toHaveBeenCalledWith(book);`.

Run `npm test` again. Compare the two versions side by side — which one reads closer to "what does a user actually see and do"?
