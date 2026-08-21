## Generate the component

```sh
ng generate component books/book-new/book-new-page
```

## The template

```html
<form [formGroup]="form" (ngSubmit)="submit()">

  <input type="text" formControlName="isbn">
  <input type="text" formControlName="author">
  <input type="text" formControlName="title">
  <input type="text" formControlName="subtitle">
  <input type="text" formControlName="abstract">
	....
  <button type="submit">Save</button>
</form>
```

## The component class

```typescript
@Component({..})
export class BookNewPage {
  private readonly formBuilder = inject(NonNullableFormBuilder);

  form: FormGroup = this.formBuilder.group({
     isbn: [''],
     author: [''],
     title: [''],
     subtitle: [''],
     abstract: [''],
  });
}
```
