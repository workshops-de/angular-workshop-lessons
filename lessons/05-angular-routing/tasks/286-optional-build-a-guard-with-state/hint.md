```ts
@Injectable({
  providedIn: 'root'
})
export class UserStateService {
  //...
}
```

```ts
const service = inject(UserStateService);
```

```ts
{
  path: 'books',
  //...
  canMatch: [
  //...
  ]
}
```
