# destructionanigans

This is a slightly modified copy of the Sapper template:

1. A writable store has been added and initialized with a falsy value.
2. `index.svelte` assigns the store to an object.
3. `about.svelte` waits for the store to be truthy and then appears via transition.

Navigating between the index page and about pages will never call `onDestroy` for the about page and ping-ponging between the two will add a new copy of the about page to the document every time.

If the store's assignment is moved to another page, ping-ponging between that page and the about page will stack about pages in the same way.

**Note:** Everything works fine if the store is a primitive value. This only seems to be relevant for object stores.
