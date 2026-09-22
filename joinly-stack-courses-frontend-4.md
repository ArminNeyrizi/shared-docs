Chapter 4

# Getting Started with React

To use React in your newly created project, load two React scripts from an external website called [unpkg.com](https://unpkg.com/):

- **react** is the core React library.
- **react-dom** provides DOM-specific methods that enable you to use React with the DOM.

index.html

```
<html>  <body>    <div id="app"></div>    <script src="https://unpkg.com/react@18/umd/react.development.js"></script>    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>    <script type="text/javascript">      const app = document.getElementById('app');      const header = document.createElement('h1');      const text = 'Develop. Preview. Ship.';      const headerContent = document.createTextNode(text);      header.appendChild(headerContent);      app.appendChild(header);    </script>  </body></html>
```

Instead of directly manipulating the DOM with plain JavaScript, remove the DOM methods that you had added previously, and add the [`ReactDOM.createRoot()`](https://react.dev/reference/react-dom/client/createRoot) method to target a specific DOM element and create a root to display your React Components in. Then, add the [`root.render()`](https://react.dev/reference/react-dom/client/hydrateRoot#root-render) method to render your React code to the DOM.

This will tell React to render our `<h1>` title inside our `#app` element.

index.html

```
<html>  <body>    <div id="app"></div>    <script src="https://unpkg.com/react@18/umd/react.development.js"></script>    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>    <script>      const app = document.getElementById('app');      const root = ReactDOM.createRoot(app);      root.render(<h1>Develop. Preview. Ship.</h1>);    </script>  </body></html>
```

If you try to run this code in the browser, you will get a syntax error:

Terminal

```
Uncaught SyntaxError: expected expression, got '<'
```

This is because `<h1>...</h1>` is not valid Javascript. This piece of code is **JSX**.
## Adding Babel to your project[](https://nextjs.org/learn/react-foundations/getting-started-with-react#adding-babel-to-your-project)

To add Babel to your project, copy and paste the following script in your `index.html` file:

index.html

```
<script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
```

In addition, you will need to inform Babel what code to transform by changing the script type to `type=text/jsx`.

index.html

```
<html>  <body>    <div id="app"></div>    <script src="https://unpkg.com/react@18/umd/react.development.js"></script>    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>    <!-- Babel Script -->    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>    <script type="text/jsx">      const domNode = document.getElementById('app');      const root = ReactDOM.createRoot(domNode);      root.render(<h1>Develop. Preview. Ship.</h1>);    </script>  </body></html>
```

To confirm it's working correctly, open your HTML file in the browser.

Comparing the **declarative** React code you just wrote:

index.html

```
<script type="text/jsx">  const domNode = document.getElementById('app');  const root = ReactDOM.createRoot(domNode);  root.render(<h1>Develop. Preview. Ship.</h1>);</script>
```

to the **imperative** JavaScript code you wrote in the previous section:

index.html

```
<script type="text/javascript">  const app = document.getElementById('app');  const header = document.createElement('h1');  const text = 'Develop. Preview. Ship.';  const headerContent = document.createTextNode(text);  header.appendChild(headerContent);  app.appendChild(header);</script>
```

You can start to see how using React enables you to cut down a lot of repetitive code.

And this is exactly what React does, it's a library that contains reusable snippets of code that perform tasks on your behalf - in this case, updating the UI.

**Additional Resources:**

You don't need to know exactly how React updates the UI to start using it, but if you'd like to learn more, here are some additional resources:

- [UI trees](https://react.dev/learn/understanding-your-ui-as-a-tree)
- [Writing markup with JSX](https://react.dev/learn/writing-markup-with-jsx)
- [react-dom/server](https://react.dev/reference/react-dom/server) sections in the React Documentation.

## Essential JavaScript for React[](https://nextjs.org/learn/react-foundations/getting-started-with-react#essential-javascript-for-react)

While you can learn JavaScript and React at the same time, being familiar with JavaScript can make the process of learning React easier.

In the next sections, you will be introduced to some core concepts of React from a JavaScript perspective. Here's a summary of the JavaScript topics that will be mentioned:

- [Functions](https://developer.mozilla.org/docs/Web/JavaScript/Guide/Functions) and [Arrow Functions](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
- [Objects](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)
- [Arrays and array methods](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array)
- [Destructuring](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)
- [Template literals](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Template_literals)
- [Ternary Operators](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)
- [ES Modules and Import / Export Syntax](https://developer.mozilla.org/docs/Web/JavaScript/Guide/Modules)

While this course does not dive into JavaScript, it's good practice to stay up to date with the latest versions of JavaScript. But if you don't feel proficient in JavaScript yet, don't let this hinder you from starting to build with React!

### It’s time to take a quiz!

Why do you need to compile your React code?

A

React uses a new version of HTML that’s too advanced for current browsers.

B

React uses JSX which needs to be compiled into JavaScript.

C

React doesn’t know how to update the DOM so it needs a compiler to do it.