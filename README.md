# Adding a todo
![add todo](https://user-images.githubusercontent.com/15989467/64073025-e9a6c380-cc6e-11e9-8d53-515334ee3f53.png)

# Removing a todo
![removing](https://user-images.githubusercontent.com/15989467/64073043-1a86f880-cc6f-11e9-83bf-15afb4ed81dc.png)

# State
This application state was built with a `writable` component, written in `./src/store.js`.
Contains and return an array created with the writable lib from svelte/store.

```
const tasks = writable([]);

export { tasks };
```

**Remember, it isn't an pure array, its an observable**

So to reference we have to use dollar symbol ($) and to change value we have to use the `.update()` method which will receive a callback function with the new state array.
like this:

```
const store = writable(['var', 'foo']); //on parameters we pass the initial state
console.log($store); // will show ['var', 'foo']

store.update( () => [...$store, 'bar']);
console.log($store); // will show ['var', 'foo', 'bar']

store.update( () => $store.filter(element => element!== 'foo'));
console.log($store); // will show ['var', 'bar']
```


*Psst — looking for a shareable component template? Go here --> [sveltejs/component-template](https://github.com/sveltejs/component-template)*

---

# svelte app

This is a project template for [Svelte](https://svelte.dev) apps. It lives at https://github.com/sveltejs/template.

To create a new project based on this template using [degit](https://github.com/Rich-Harris/degit):

```bash
npx degit sveltejs/template svelte-app
cd svelte-app
```

*Note that you will need to have [Node.js](https://nodejs.org) installed.*


## Get started

Install the dependencies...

```bash
cd svelte-app
npm install
```

...then start [Rollup](https://rollupjs.org):

```bash
npm run dev
```

Navigate to [localhost:5000](http://localhost:5000). You should see your app running. Edit a component file in `src`, save it, and reload the page to see your changes.


## Deploying to the web

### With [now](https://zeit.co/now)

Install `now` if you haven't already:

```bash
npm install -g now
```

Then, from within your project folder:

```bash
cd public
now
```

As an alternative, use the [Now desktop client](https://zeit.co/download) and simply drag the unzipped project folder to the taskbar icon.

### With [surge](https://surge.sh/)

Install `surge` if you haven't already:

```bash
npm install -g surge
```

Then, from within your project folder:

```bash
npm run build
surge public
```
