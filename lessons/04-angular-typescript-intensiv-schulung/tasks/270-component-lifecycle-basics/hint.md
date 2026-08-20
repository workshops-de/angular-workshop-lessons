Angular Guide, Lifecycle Hooks

https://angular.dev/guide/components/lifecycle#summary

```ts
// ...
import { Subscription } from 'rxjs';

export class BookComponent implements <INSERT HOOKS HERE SEPERATED BY COMMA> {
  private subscription = Subscription.EMPTY;
  
  // ... constructor
  ngOnInit(): void {
    // load data via service here
    // watch out: maybe the service is named differently in you code.
    // this.bookDataService is just an example
    this.subscription = this.bookDataService. ... .subscribe(<successFn>);
  }
  
  ngOnDestroy(): void {
    this.subscription.unsubscribe();
  }
}
```
