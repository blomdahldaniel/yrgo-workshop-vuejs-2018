Previous: [303 Frontend](./303-frontend.md)

# 304 View Book

Now we will create a page for when we are viewing the active book.
But we want to access the view book page from the route `books/1337` where `1337` is an id for a book.

Create a new `.vue` page: `pages/books/_id.vue`

The new file `_id.vue` will be a way for nuxt to know that we are looking for a dynamic route.

Setup the `pages/books/_id.vue` file and add the asyncData

```JavaScript
// ......
asyncData ({app, params}) {
  return app.$axios.get('/books/' + params.id)
    .then(res => {
      return { book: res.data }
    })
},
```


Add them to the navbar and make sure to add a  `<nuxt-link>` that works.

## 1. Display the book info
Follow the instructions in the markup to add the vue extra flavor to make things come alive!

**HTML**

```html
<div>
  <h6> <span class="glyphicon glyphicon-menu-left"></span></h6>
  <div class="book-show-wrapper">
    <div class="left-content">
      <div class="book-image-wrapper">
        <img class="book-image" :rc="">
      </div>

      <strong>Your rating:</strong>
      <div class="rating-wrapper">
          <!--
            Loopa antal för books.rating och sedan 5 - boks.rating för att visa rätt stjärna.
         -->
        <span class="glyphicon glyphicon-star"></span>
        <span class="glyphicon glyphicon-star-empty text-gray-light"></span>
      </div>
      <br>
      <!--
          Visa bara om book.rating_read_again != null
       -->
      <template>
        <strong>Would read again:</strong>
        <div class="rating_read_again-wrapper">
         <!--
           Loopa antal för books.rating_read_again och sedan 5 - boks.rating_read_again att visa rätt stjärna.
           Glöm inte upgie "key".
        -->
          <span class="glyphicon glyphicon-thumbs-up"></span>
          <span class="glyphicon glyphicon-thumbs-up text-gray-light"></span>
        </div>
      <br>
      </template>
      <!--
        Visa om book.started_at
       -->
      <p>
        <strong>Started reading:</strong>
        <br>
        <!-- skriv ut book.started_at -->
      </p>
      <!--
        Visa om book.finished_at
       -->
      <p>
        <strong>Finished reading:</strong>
        <br>
        <!-- skriv ut book.finished_at -->
      </p>
    </div>
    <div class="content">
      <h2 class="no-margin-top">{{ book.title }}</h2>
      <p class="no-margin-top">{{ book.author }}</p>
      <h6>DESCRIPTION</h6>
      <blockquote>{{ book.description }}</blockquote>

      <!-- skriv ut book.body om det finns någon body -->
      <h6>NOTES</h6>
      <div v-html="book.body"></div>
    </div>
  </div>
</div>
```

## 3. Link back

Add a link that goes back to the `/books` index page
It should include:
```html
<span class="glyphicon glyphicon-menu-left"></span> BACK TO MY BOOKS
```


# Next:
[305 Add book](./305-add-book.md)
