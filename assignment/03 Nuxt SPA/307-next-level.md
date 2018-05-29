Previous: [307 Add Book](./307-add-book.md)

# Extras
Here are suggestions for how you can improve the twitter app.

🌶 = Refreshing

🌶🌶 = MmMm.. Spicyy...

🌶🌶🌶 = Daaaiiim that's hot!

🌶🌶🌶🌶 = I CAN'T FEEL MY LEGS! 

## 1. Update book
Create a new page where you can update the information for a book.
For simplicity, create a new page called `books/_id/edit.vue`. 
Copy and paste the template from your `add.vue` file.

#### Axios
First, fetch the book on load:

```JavaScript
// ...
asyncData ({app, params}) {
  return app.$axios.get('/books/' + params.id)
    .then(res => {
      return { book: res.data }
    })
},
```

Then setup the form to push to the correct backend path
```
this.$axios.put('/books/' + book.id, this.form).then(res => {
    // send the user to the view page after update
})
```

#### 🌶🌶 Create a `<book-form>` component
But hey, now we are reusing a lot of code.
If your cool, you would first create a component called `book-form`

## 2. Archive book
We want to add the option to archive a book.

1. Create a new view called `archived` that will list all archived books.

```
this.$axios.get('/books/archived')
```

2. Add a link from the `/pages/books/index.vue` page to point to the new archived page. 
3. Add two buttons for each archived book that links to restore and delete archived
 
Restore url: `this.$axios.put('/books/archived/{id}')`
Delete archived url: `this.$axios.delete('/books/archived/{id}')`

Redirect the user if needed.


## 3. 🌶🌶 Date picker 
Add a real date picker for the date field in the book form.
So install it (npm) in [vuejs-datepicker](https://github.com/charliekassel/vuejs-datepicker) and make it work with the form value.

Make sure to add a date picker for both `book.started_at` and `book.finished_at`


## 3. 🌶🌶 toggle done
From the `view` page. Add a toggle functionality to `started_at` and `finished_at`.

```
this.$axios.put('/books/' + book.id, this.form).then(res => {
    // send the user to the view page after update
})
```


# Next:
[308 Extras](./308-extras.md)
