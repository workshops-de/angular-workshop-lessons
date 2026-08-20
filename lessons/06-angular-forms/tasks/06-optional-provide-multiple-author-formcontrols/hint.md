```typescript
export class BookNewComponent {
...
  form: FormGroup<BookForm> = this.formBuilder.group({
   ...
    authors: this.formBuilder.array(['', [Validators.required, validAuthorName()]]),
   ...
  });

  addAuthor() {
    this.form.controls.authors.controls.push(this.formBuilder.control('', [Validators.required, validAuthorName()]));
  }
  
  deleteAuthor(index: number) {
    this.form.controls.authors.removeAt(index);
  }
}
```

```html
  <ng-container formArrayName="authors">
  @for(author of authors.controls; track author){
      <label class="form-field">
        <span>Author</span>
        <input [formControlName]="$index" />
        <!-- <small> .... </small>-->
      </label>
      <button (click)="deleteAuthor($index)">
        Remove Author
      </button>
  }
  </ng-container>
```
