# The `main.js` file

All plugins must have a `main.js` file, which serves as the entry point for execution of your JavaScript code. This file is where all the fun happens!

Below, we'll cover some points to help you get oriented with `main.js`.


## Wiring your code to the manifest

Your `main.js` file exports a map linking each `commandId` from the manifest to a _handler function_ in your code:

```js
function sayHello(selection, documentRoot) {
    console.log("Hello, world!");
}

module.exports.commands = {
    helloCommand: sayHello
};
```

In this example:

1.  `helloCommand` matches the value of `commandId` in your manifest
1. `sayHello` is the name of your main handler function, so it is mapped to `helloCommand` in your command exports.


## Contextual arguments

The handler function (in the above example, `sayHello`) receives two contextual arguments from XD:

* The current [selection](../selection.md) state
* The root node of the entire document (see [scenegraph > RootNode](../scenegraph.md#rootnode))

The argument names `selection` and `documentRoot` are arbitrary, but are considered convention. We use those names throughout our documentation.


## Accessing app APIs

See [Available APIs](../core/apis.md) to learn about how to access the APIs that XD provides you with. Most APIs are loaded using `require()`, but a few can be accessed directly as globals.


## Loading libraries and other JavaScript files

You can learn about including further JavaScript files in our [JavaScript concepts section on using `require`](/reference/javascript/javascript-support.html#can-i-use-require).