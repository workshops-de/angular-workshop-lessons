3, 2, 1 Go! Now you will create your first component.

- Open a second terminal.
- Switch to the directory where your Angular project is located.
- Create a new component by executing the following command `ng generate component book-card`.
- Recognize that three files are generated.
- Recognize that your component (_book-card.component.ts_) has the selector `app-book-card`.

- Open _src/app/book-card/book-card.component.html_.
- Set up a simple HTML template visualizing book-information by using **static data**.
  - title
  - author
  - details-link
  - abstract
  
  ```html
  <!-- book-card.component.html -->
  
  <h3>Moby Dick</h3>
  <h4>Herman Melville</h4>  

  <!--
  ... link, abstract ...
  -->
  ```

- Use your component in _app.component.html_. Replace the existing content of _app.component.html_ with `<app-book-card></app-book-card>`.
- Add the missing import for `BookCardComponent` to imports in _app.component.ts_.
- Ensure that your component is displayed in the browser.
- Check [localhost:4200](http://localhost:4200).

## How the component could look like

<iframe src="https://docs.google.com/presentation/d/1QyM9Nwm6CRvQkDvp3q9I-UN32CQmZ-eXs9tdBJXeFYk/embed#slide=id.ga8afa0fa9e_0_24" width="100%" height="720px"></iframe>
