Previous: [305 View Book](./305-view-book.md)

# 305 Add Book
Now it is time to set up a form and work out how we can post some data to our server. Create a new file `pages/books/add.vue`

Add the following script section to the page.

```html
<script>
  export default {
    middleware: 'auth',
    data () {
      return {
        form: {
          title: '',
          author: '',
          // ....
        }
      }
    },
  }
</script>
```

And now lets add the template. Follow the instructions in the markup to make the page come alive.

Note that the instructions is only present for the first input. Make sure to get all of the inputs to work properly.

```html
<template>
  <div class="row">
      <nuxt-link to="/books"><span class="glyphicon glyphicon-menu-left"></span> BACK TO MY BOOKS </nuxt-link>
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 card box-shadow-2">
        <h3 class="no-margin-top">Add Book</h3>

        <!-- 
          Listen for the submit event on the form and then prevent the
          default action. But when the form is submited, a method called
          submitForm should be called.
         -->
        <form class="form-horizontal">
          <fieldset>
            <!-- add class .has-error if erros.title exists -->
            <div class="form-group">
              <label for="inputTitle" class="col-lg-3 control-label">Title*</label>
              <div class="col-lg-9">
                <!-- Bind the form.title variable to the input -->
                <input type="text" class="form-control" id="inputTitle" placeholder="Title">
                <span class="help-block" v-if="errors.title">
                  <!-- print the first error message errors.title[0] -->
                </span>
              </div>
            </div>
            <div class="form-group">
              <label for="inputAuthor" class="col-lg-3 control-label">Author*</label>
              <div class="col-lg-9">
                <input type="text" class="form-control" id="inputAuthor" placeholder="Author">
                <span class="help-block">
                  errors.author[0]
                </span>
              </div>
            </div>
            <div class="form-group">
              <label for="inputImageLink" class="col-lg-3 control-label">Image link</label>
              <div class="col-lg-9">
                <input type="text" class="form-control" id="inputImageLink" placeholder="Image link">
              </div>
            </div>
            <div class="form-group">
              <label for="inputStartedAt" class="col-lg-3 control-label">Started reading at</label>
              <div class="col-lg-9">
                <input type="text" class="form-control" id="inputStartedAt" placeholder="Started reading at">
              </div>
            </div>
            <div class="form-group">
              <label for="textArea" class="col-lg-3 control-label">Description</label>
              <div class="col-lg-9">
                <textarea class="form-control" rows="2" id="textArea"></textarea>
                <span class="help-block">
                  Add a short description for the book.
                </span>
              </div>
            </div>
            <div class="form-group">
              <label for="textArea" class="col-lg-3 control-label">Notes</label>
              <div class="col-lg-9">
                <textarea class="form-control" rows="3" id="textArea"></textarea>
                <span class="help-block">
                  Here you can write your notes in markdown
                </span>
              </div>
            </div>
          </fieldset>
          <button type="submit" class="btn btn-primary pull-right">Add new book</button>
        </form>

      </div>
    </div>
</template>
```

## 1. Try out the form
Make the form work! When `sendForm()` is called, all the `form` values should be visible in the console. When you are ready, feel free to start posting to the server.

**If validation fails (required fields):**
If the validation fails and throws back an `HTPP: 422`, the validation plugin
for axios will help us out. All errors will be captured and the error messages will be kept inside a global (vuex) variable called `errors`.


```JavaScript
methods: {
  sendForm() {
    console.log(this.form)
    // this.$axios.post('/books', this.form)
    //  .then(res => {
    //    this.$router.push('/books/' + res.data.id)
    //  })
  }
}
```

Notera att `this.$router.push('/books/' + res.data.id)` skickar oss direkt till vy-sidan för den nya boken `pages/books/_id.vue`.

## 2. Add a way to enter stars (rating and rating_read_again)
You may choose your own path here, text input, dropdown select or what ever. 
But add a way to enter the `form.rating` which is the rating for the book.
Try to make it intuitive if you like!


# Next:
[307 Next Level](./307-next-level.md)
