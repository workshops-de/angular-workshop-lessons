```typescript
private formBuilder = inject(FormBuilder)
this.form = this.formBuilder.group({
    author: ['', [Validators.required]],
    title: ['', [Validators.required]],
    subtitle: [''],
    abstract: [''],
});
```

```html
<form [formGroup]="form" (ngSubmit)="create()">
  <label>
    <span>Title</span>
    <input formControlName="title" />
@if(form.get('title')?.dirty && form.get('title')?.hasError('required')){
      <small>Please insert a title. </small>
}
  </label>
  <label>
    <span>Author</span>
    <input formControlName="author" />
@if(form.get('author')?.dirty && form.get('author')?.hasError('required')){
      <small>Please insert a title.</small>
}
  </label>
  ....
  <button type="submit" [disabled]="form.invalid">Save</button>
</form>	
```
