```ts
// book-card.spec.ts
import { render, screen } from '@testing-library/angular';
import userEvent from '@testing-library/user-event';
import { BookCard } from './book-card';
import { Book } from '../book';

describe('BookCard', () => {
  const book: Book = {
    isbn: '978-3-16-148410-0',
    cover: '',
    title: 'Moby Dick',
    author: 'Herman Melville',
    abstract: 'A whale of a tale.'
  };

  it('should display the book title', async () => {
    await render(BookCard, { componentInputs: { content: book } });

    expect(screen.getByText(book.title)).toBeInTheDocument();
  });

  it('should emit detailClick when the details link is clicked', async () => {
    const detailClick = vi.fn();
    await render(BookCard, {
      componentInputs: { content: book },
      componentOutputs: { detailClick }
    });

    const user = userEvent.setup();
    await user.click(screen.getByRole('link', { name: /details/i }));

    expect(detailClick).toHaveBeenCalledWith(book);
  });
});
```
