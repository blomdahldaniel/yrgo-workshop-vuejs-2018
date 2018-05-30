Previous: [302 Backend](./302-backend.md)

# 303 Frontend with Nuxt.js
The frontend is a nuxt project. Again, the boilerplate was originally made by Alex on codecourse.

## 1. Setup
- `git clone https://github.com/blomdahldaniel/yrgo-nuxt-client`
- `yarn install` / `npm install`

## 2. Dependencies
To make things simple, i use Twitter Bootstrap 3.3 for the frontend.
I use a pre defined styling called [Bootswatch Paper](https://bootswatch.com/3/paper/). You will need to come back to this page to see the different styles/components.

## 2. The nuxt config
Now lets open up the `nuxt.config.js` and take a look.
- Take a look at the `head: {}` object. Pretty similar to how a html `<head>` is structured
- The `css` is pulled in from the `/css` directory. However you can pull in directly from your `node_modules` as well if you would like to. You can also point to cdn css files if you instead of `css` add another object to the `head.link` array.
- Next some middleware, plugins and modules are pulled in to do its magic
- **IMPORTANT**  make sure to add your correct backend domain here, if you run `php artisan serve` on localhost port 8000 then this is correct for you:

```
axios: { baseURL: 'http://127.0.0.1:8000/api/v1'},
```

## 3. Run the client application
Lets run the client application
`npm run dev`

Check it out in the browser [http://localhost:3000](http://localhost:3000)

## 4. Sign up
Create your own account.
Make sure that you have the backend server running, that you have pointed the `nuxt.config.js` axios `baseURL` to the right path.

- Go to sign up and sign up...

### You should now be loged in and ready for some real action!

# Next:
[304 My Books App](./304-books-app.md)
