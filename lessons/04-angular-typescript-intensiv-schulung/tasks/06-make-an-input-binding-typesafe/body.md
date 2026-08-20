We can embrace TypeScripts language features to make developing with Angular more comfortable.

- Create an _Interface_ called `Book`.
- Execute following command to create the interface: `ng generate interface book`.
- Open _src/app/book.ts_.
- Specify the following properties: _title_, _abstract_, _author_ all as `string`.
- Switch to the _AppComponent_.
- Annotate the property book with the interface `Book`.
 - You might need to import `Book` from _'./book'_ if your editor misses to import the type automatically.
- Switch to the _BookCardComponent_.
- Annotate the `input()` signal function with the interface `Book`.
- *Be aware, if you are using the `input()` signal function variant, you have to deal with undefined.*
- Recognize that you now have auto-completion in both TypeScript- & Template-Files.
