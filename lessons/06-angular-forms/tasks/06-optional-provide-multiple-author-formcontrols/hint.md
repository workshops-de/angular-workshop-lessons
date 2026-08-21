```typescript
export class BookNewPage {
...
  form: FormGroup<BookForm> = this.formBuilder.group({
   ...
    authors: this.formBuilder.array([
      ['', [Validators.required, validAuthorName()]]
    ]),
   ...
  });

  get authors(): FormArray {
    return this.form.controls.authors;
  }

  addAuthor() {
    this.authors.push(this.formBuilder.control('', [Validators.required, validAuthorName()]));
  }

  deleteAuthor(index: number) {
    this.authors.removeAt(index);
  }
}
```

```html
  <ng-container formArrayName="authors">
  @for (author of authors.controls; track author; let index = $index) {
      <label class="form-field">
        <span>Author</span>
        <input [formControlName]="index" />
        <!-- <small> .... </small>-->
      </label>
      <button (click)="deleteAuthor(index)">
        Remove Author
      </button>
  }
  </ng-container>
```
