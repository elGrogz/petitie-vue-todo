# petitie-vue-todo

Playing about with the Petite Vue Stack. I watched [this](https://www.youtube.com/watch?v=Sxxw3qtb3_g) video which inspired me to give the [Petite Vue Framework](https://github.com/vuejs/petite-vue) a try by building a Todo app, something that I haven't got round to yet.

# Spec

I want the app to:

- Allow me to add a todo list with a title
  - This will be saved in a database
- Add seperate items in that todo list in a bulleted list
  - These will also be saved in a database
- Show lists altogether in a grid
- When I click on a list, I see a full(er) screen view of that list
- Delete items and entire lists
- Update items and entire lists
- Add authentication so users can log back in and see their todo lists

# First steps

First I created a repo for my app [here](https://github.com/elGrogz/petitie-vue-todo).

Then I added a basic HTML page which will serve as my main apps page. Despite being the simplest step in the whole process I actually forgot the basic HTML layout so I had to research that. But never fear:

No matter how small, commit early and often :)

The final 'first' step is to add Petite Vue to the webpage. Now my page looks something like this:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Petite Vue Todo</title>
    <script src="https://unpkg.com/petite-vue" defer init></script>
  </head>
  <body>
    <p>Let's make a todo!</p>
    <div v-scope="{ count: 0 }">
      {{ count }}
      <button @click="count++">++</button>
    </div>
  </body>
</html>
```

Now the page has a nice wee count button demonstarting some basic Vue javascript. Here we have:

- the `script` tag, which loads petite vue.
- The `v-scope` attribute, which tells the webpage what areas are controlled by Vue.

Let's add another special Petite Vue attribute: `v-effect`

```
  <div v-scope="{ count: 0 }">
    <div v-effect="$el.textContent = count"></div>
    <button @click="count++">++</button>
  </div>
```

`v-effect` will rerun whenever the `count` variable is changed.

Ok let's continue. Vue seems to work by adding Vue attributes to HTML elements, and binding javascript to them.
