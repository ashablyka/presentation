### Slide1
In this presentation I'll try to cover everything you need to know to get started with JSDoc. I'll also share with you some other cool stuff I learned about it that you might find useful.
### Slide2. Why code documentation?
Suppose you wrote a couple of functions for making an HTML table with JavaScript. You could use those function right now, or pass them to another developer.

Everything is clear in your mind the moment you write the code, yet a month later you don't remember how to use functionA or functionB anymore. And so your colleagues. How functionA is supposed to be called? What parameters it takes? And what shape should the parameters have?

Code documentation dissolves those doubts, helping you and other developers to understand how to use the software you wrote.
### Slide3. Forms of code documentation
There are many ways for documenting a piece of code. For example you can write:

-   howtos guides for using your code
-   a nice README for the repo
-   code documentation in the source

Tutorials are nice because you can teach things to thousands of people, but they get outdated soon for many reasons: lack of time, breaking changes to the code.

A README on the Git repo hopefully is more in sync with the project because when you make changes to the code you're "forced" to update the README too (otherwise users will complain).

But on top of howtos and READMEs, code documentation in the source holds most of the value. It sits right there with the code and helps avoiding mistakes as you write JavaScript (or any other language) in the editor.

Speaking of JavaScript, we can use a documentation layer called, JSDoc. It's a command line tool and a "documentation language" at the same time. Let's see how it can helps.
### Slide4. function generateTableHead(table, data)
Consider the following function.

This function kind of speaks by itself, "generateTableHead" after all is a descriptive sentence. But how about the "data" parameter? What "data" should be really? If I look at the function's body becomes evident that "data" must be an array (by the way, what a bad naming for "data". How about "arrayOfNames"?).

"table" is less bad on the other hand, yet it's not clear if it could simply be a string or an actual HTML element.
Turns out, code documentation with JSDoc annotations can help our functions to better describe their intentions

### Slide5
JSDoc is simple as adding a comment before the function:

In this case we already know the function's purpose by looking at its name. But let's make things interesting with JSDoc annotations for function parameters...

### Slide6. @param

Here's the syntax:

For each parameter you can describe:
-   its  **type**, i.e. string, number, HTMLTableElement and so on
-   its  **name**
-   a  **description**

Having laid the foundations let's move on to documenting our function...

### Slide7

"generateTableHead" should take an HTMLTableElement and an array as parameters. We can add annotations for both like so:

### Slide8. VSCode

Adding JSDoc documentation has a side effect. Auto completion will improve in your IDE and you'll get real-time hints.

This is example in VS Code.

### Slide9. @autor

JSDoc has a lot more tags. The "author" annotation for example is useful when you need to blame someone's else code. Here's an example:

### Slide10. @return

Another useful tag is "return" (or "returns") for describing the return value of a function. Our function returns nothing:

### Slide11

And here's a function which returns a number:

### Slide12. Tags

Some of the more popular annotation tags used in modern JSDoc are here:

### Slide13

JSDoc has a binary which can be installed in your JavaScript project. To make a bit of practice create a project in a new folder and Initialize with:
```bash
npm init -y
```
And install JSDoc:

```bash
npm i jsdoc --save-dev
```
Finally run the JSDoc binary against the file:

```bash
node_modules/jsdoc/jsdoc.js app.js
```

### Slide14

If everything goes well you'll see a new folder named  **out**  in your project folder. Inside this folder open up index.html, click on "generateTableHead" and check out the page. You should see your documentation for generateTableHead formatted in HTML.
