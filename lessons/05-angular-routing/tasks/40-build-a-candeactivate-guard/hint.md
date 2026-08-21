
## Guard function

- Import CanDeactivateFn interface from `@angular/router`
- Add interface to your function as return value and implement the fat arrow function

```ts
export const confirmLeaveGuardFn: CanDeactivateFn<MyComponent> = (component, route, state) => {
  // ...
};
```

```ts
return confirm('Do you really want to leave?');
```


Add guard to route:

```ts
{
  path: ...,
  component: ...,
  canDeactivate: [...]
}
```

