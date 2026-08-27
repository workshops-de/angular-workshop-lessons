```ts
// book-card.spec.ts
import { ComponentFixture, TestBed } from '@angular/core/testing';
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

  let component: BookCard;
  let fixture: ComponentFixture<BookCard>;

  beforeEach(() => {
    TestBed.configureTestingModule({});

    fixture = TestBed.createComponent(BookCard);
    component = fixture.componentInstance;
    fixture.componentRef.setInput('content', book);
    fixture.detectChanges();
  });

  it('should display the book title', () => {
    const title = fixture.nativeElement.querySelector('h3');
    expect(title.textContent).toContain('Moby Dick');
  });

  it('should emit detailClick when the details link is clicked', () => {
    let emitted: Book | undefined;
    component.detailClick.subscribe(value => (emitted = value));

    const link: HTMLAnchorElement = fixture.nativeElement.querySelector('a');
    link.click();

    expect(emitted).toEqual(book);
  });
});
```
