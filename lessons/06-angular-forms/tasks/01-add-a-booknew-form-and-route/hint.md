```sh
ng generate component book/book-new
```

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


```typescript
@Component({..})
export class BookNewComponent {
  private formBuilder = inject(FormBuilder);
	
  form: FormGroup = this.formBuilder.group({
     isbn: [''],
     author: [''],
     title: [''],
     subtitle: [''],
     abstract: [''],
  });
}
```
