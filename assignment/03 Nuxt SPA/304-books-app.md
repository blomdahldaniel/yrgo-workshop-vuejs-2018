Previous: [303 Frontend](./303-frontend.md)

# 304 My Books App

The app will contain these different views:
- **My Books**
    + index
    + show
    + add
    + edit

Setup the entry endpoint:
- `pages/books/index.vue`

Add the link to the navbar and make sure to add a  `<nuxt-link>` that works.
Add it to the section that is rendered only if the user is authenticated.

### Redirect to `/books`
From the `signin.vue` and the `signup.vue` make sure that the user is sent to the `/books` route when loged in the first time.
`this.$route.query.redirect || 'books'`
`this.$router.push('books')`


## 1. Fetch all my books
Fetch all books from the backend through nuxt `asyncData()` method.

> asyncData creates a request to get the data from the URL before the HTML is shipped to the browser. This allows search engines to see the content on the page. Since this is a loged in mode, it does not make much sens but thats ok, its just an example. If you would not do it this way, how would you do it..?

```JavaScript
// .....
asyncData ({app}) {
  return app.$axios.get('/books')
    .then(res => {
      return { books: res.data }
    })
},
```

> Note that we get the `app` variable from the asyncData() function. This allows us to reach for the $axios plugin.

## 2. Display list with some styling

Loop over the list and follow the instructions in the markup to add the vue extra flavor to make things come alive!

**HTML**
```html
<!-- /pages/books/index,vue -->
<div>
  <h1 class="pull-left no-margin-top">Books</h1>
  <div class="books-wrapper">
    <!--
        Loopa över .book-item och visa alla böcker
        Glöm inte lägga till :key="book.id" för att varje
        loop ska vara unik.
    -->
    <div class="book-item" v-for="book in books" :to="'/books/' + book.id" :key="book.id" tag="div">
        <div class="book-image-wrapper">
            <!--
                Visa denna banner om boken är påbörjad men inte färdigläst
                book.started_at && book.finished_at == null
             -->
          <div class="banner is-started">started</div>
          <!--
              Visa denna banner om boken är färdigläst
              book.started_at && book.finished_at
           -->
          <div class="banner is-finished">finished</div>

          <!--
              Bind src till book.image_path
           -->
          <img class="book-image" src="">
        </div>

        <!--
            Skriv ut book.title och book.author
         -->
        <div class="book-title"></div>
        <div class="book-author"></div>

        <!--
            Visa denna if om book.rating är > 0 och != null
         -->
        <div class="rating-wrapper center">

        <!--
            Man måste inte loopa över en array utan man kan också loopa
            övern en siffra. Stanna upp och se hur det funkar.
            Lägg till en :key men tänk på att en key måste vara unik.
         -->
          <span class="glyphicon glyphicon-star"></span>
          <span class="glyphicon glyphicon-star-empty text-gray-light"></span>
        </div>
    </div>
  </div>
</div>
```


## 3. Make it to a component

Create a component called `<book-item>` and extract the above book item into this component and loop it through (display them all) in the `books/index.vue` file.


# Next:
[305 View book](./305-view-book.md)
