1. Change the `author` FormControl to an `FormArray`
2. Create `addAuthor` and the `deleteAuthor` Function using the FormArray API (`push(new FormControl(...))`)
3. Insert the new FormArray inside the template using `@for` for Iterating over the Controls of the newly created FormArray
4. Add Buttons for removing and adding an Author `FormControl` (The Button for Removing an Author needs to be inside the Html created with `@for`
5. Our Backend cannot handle multiple authors - In order for the `BookApiService` to still work we need to just givin one single Author of this Array 
