Angular Guide, Lifecycle Hooks

https://angular.dev/guide/components/lifecycle#summary

```ts
// ...
import { Subscription } from 'rxjs';

export class BooksPage implements <INSERT HOOKS HERE SEPERATED BY COMMA> {
  private subscription = Subscription.EMPTY;
  
  // ... constructor
  ngOnInit(): void {
    // load data via service here
    // watch out: maybe the service is named differently in you code.
    // this.booksClient is just an example
    this.subscription = this.booksClient. ... .subscribe(<successFn>);
  }
  
  ngOnDestroy(): void {
    this.subscription.unsubscribe();
  }
}
```
