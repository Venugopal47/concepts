# DOM

## What is DOM

It is a representation of HTML that can be accessed using Javascript.When a web page is loaded, the browser creates the DOM for that specific page.

## Structure Of DOM

The structure of the DOM uses something called a tree, where the top node is the document object.

![image](https://github.com/user-attachments/assets/fce76633-4591-4f4c-8c88-de4271b57ed7)


## Things we can do with DOM

- **Finding Elements**
- **Creating new elements***
- **Updating elements**
- **Changing properties of an elements**
- **Listening to events like click, hover, etc**

## 1. Element Selection in DOM

To access the DOM, we make use of the document object.

This object has properties and functions that we use to access our HTML elements which we can manipulate with JavaScript by using some methods.

### Methods

- **getElementById:**

It accepts a string which is the name of an id in the DOM and returns the first element that matches the id passed to the function.

```document.getElementById("div1");```

This function returns a special object called an HTMLElement.

- **getElementsByTagName:**

It accepts a string which is the HTML tags (like div, p, a, li, ul etc) in the DOM and returns a list of all of the elements that match the string passed to the function.

```document.getElementByTagName("p");```

This function returns an HTMLCollection to us!.It looks a lot like an array, and you can access it at a specific index or use a for loop.

However, you can not use common methods like push, pop, indexOf or includes.

- **getElementsByClassName:**

It accepts a string which is the class name of an element in the DOM and returns a list of all of the elements that have a class attribute, which matches the string passed to the function.

```document.getElementsByClassName("p2");```

Just like getElementsByTagName, this function returns a special HTMLElement object to us.

- **querySelector:**

It accepts a string that is a valid CSS selector and returns the first element that matches the CSS selector passed to the function.

```document.querySelector("#div1");```

Just like getElementById, this function returns a special HTMLElement object to us.

- **querySelectorAll:**

It accepts a string that is a valid CSS selector and returns all the elements that matches the CSS selector passed to the function.

```document.querySelectorAll("#div1");```

This function returns a NodeList.It looks a lot like an array, and you can access it at a specific index or use a for loop

However, you can not use common methods like push, pop, indexOf or includes

It’s almost identical to an HTMLCollection except it can include special kinds of nodes.

**Difference b/w NodeList and HTML Collection:**

<https://dev.to/jharteaga/difference-between-htmlcollection-and-nodelist-25bp>

## 2. DOM Manipulation

**Modifying Elements in the DOM:**

- **Accessing Text**

The easiest way to access the text of an element is to use innerText.

```<section id="greeting">
  <article>Hello World!</article>
</section>
```

```const greeting = document.getElementById("greeting")

console.log(greeting.innerText) // "Hello World!" 

```

- **Modifying Text**

```const greeting = document.getElementById("greeting")

greeting.innerText = "It's changed !!!"
```

Using textContent also we can access and modify text.

**So what’s the difference?**

textContent gets the content of all elements, including script and style elements. In contrast, innerText only shows “human-readable” elements.

- **Accessing HTML**

If you need to access the HTML of an element, you can use innerHTML. This will include all the elements inside of the one you select.

```<section id="greeting">
  <article>Hello World!</article>
</section>
```

```const greeting = document.getElementById("greeting")

console.log(greeting.innerHTML) // "<article>Hello World!</article>"
```

- **Modifying HTML**

If you need to change any HTML, you can assign a new value to the innerHTML, just like you did with innerText:

```const greeting = document.getElementById("greeting")

greeting.innerHTML = "<article>It's Changed!!!</article>"
```

- **Modifying Styling**

You can access any inline CSS properties on an element using the style property.

```<h1 style="color: black; background-color: red;">
  Welcome to MountBlue!!!
</h1>
```

```const mainHeading = document.querySelector("h1")

mainHeading.style.color // "black"
```

To change the style, simply reassign the value of the CSS property

```const mainHeading = document.querySelector("h1")

mainHeading.style.color = "red
```

**How about background color?**

```const mainHeading = document.querySelector("h1")

console.log(mainHeading.style.background-color) //Error!
```

It was working fine for color property, but throwing error for background-color property, why????

It's because of Hyphen("-") sign, and it will apply to all the properties having a hyphen in their names, so, instead, remove the hyphen and join the word in camelCase format, i.e.,
background-color will become backgroundColor

- **Modifying Attributes**

To do that, we can get attributes using getAttribute and modify attributes using setAttribute.

***getAttribute***

In order to access an attribute on an element, you can use the getAttribute method

```const firstInput = document.querySelector("input")

firstInput.getAttribute("type") // "text"
```

***setAttribute***

To set an attribute on an element, you can use the setAttribute method.

```const firstInput = document.querySelector("input")

firstInput.setAttribute("type", "email") // "email"
```

***Direct attribute access***

There are a few attributes that you can directly access and modify as well instead of having to use getAttribute or setAttribute.

- **id**

```<input type="text" id="first-name">```

```const firstInput = document.querySelector("input")

firstInput.id // "first-name"

firstInput.id = "full-name" // changes the attribute
```

- **value**

```<input type="text" >```

```const firstInput = document.querySelector("input")

firstInput.value // ""

firstInput.value = "full-name" // changes the attribute
```

### Manipulating classes

We have quite a few ways to manipulate the ***class*** attribute in JavaScript:

- ***setAttribute(“class”)*** - this will override the class
- ***className*** - this will give you a string representation of the class
- ***classList*** - this will give you an array-like object to add, remove or toggle classes

#### setAttribute(“class”)

If you want to access the class attribute you can use ***getAttribute(“class”)*** or the ***className*** property.

```const mainHeading = document.querySelector("h1")

mainHeading.setAttribute("class", "section-heading");
```

this works but will overwrite the previous class

#### className

You can also add a class by reassigning the className property

```const mainHeading = document.querySelector("h1")

mainHeading.className += " top-heading" // works, but is prone to bugs
```

#### classList

An easier way to interact with classes on an element is to use the ***.classList*** method

```const mainHeading = document.querySelector("h1")

mainHeading.classList // []

mainHeading.classList.add("top-heading") // ["top-heading"]

mainHeading.classList.remove("top-heading") // []

mainHeading.classList.toggle("top-heading") // true

mainHeading.classList.contains("top-heading") // true
```

### Changing Multiple Elements

Now that you’ve seen how to modify styles, attributes, and text. How can we modify multiple elements at once?

```const listItems = document.querySelectorAll("li");

// let's change them all to green!

listItems.style.color = "green"
//  TypeError: Cannot set property 'color' of undefined
```

**How it's done ???**

To do this we need to loop over multiple elements!

```const listItems = document.querySelectorAll("li");

for(let listItem of listItems){
  listItem.style.color = "red";
}
```

### Working with the Dom

#### Creating Elements

To create an HTML element, we can use the ***createElement*** function and pass in the name of the element

This just makes an empty element, so if we want to add any text, attributes or styling we will have to do that on another line

```const newDiv = document.createElement("div");

newDiv.innerText = "a brand new div!"

newDiv.style.color = "red"
```

#### Appending Elements

After you create an element, you need to place it in the DOM to see it. You can do this using the ***append*** method.

***append*** is a method that a parent element calls and you pass in the child element that you would like to place inside of the parent element.

```const ul = document.querySelector("ul");

const newLi = document.createElement("li");

newLi.innerText = "Hello!";

ul.append(newLi);
```

**Note:** append will place the element as the last child in the parent. If you would like the element to be the first child, you can use the ***prepend*** method.

#### Removing Elements

If we want to remove elements in the DOM, we can use the handy ***remove*** method.

In order to remove an element, we first need to find it.

```const ul = document.querySelector("ul");

ul.remove();
```

This function can only be called on a single element, so if you need to remove multiple elements you’ll need to call ***remove*** multiple times.

### Finding elements near another element

As you start adding and removing elements in the DOM, there are times where you might want to know not only information about an element, but it’s parents or children.

You might want to:

- find an element and remove some or all of its children
- find an element and add an element to one of its children

```<!DOCTYPE html>
<html>
<body>
  <section>
    <h1>Here is a main heading!</h1>
    <div>
      <p>
        Here is a paragraph inside a div!
      </p>
      <ul>
        <li>First list item in a div</li>
        <li>Second list item in a div</li>
      </ul>
    </div>
    <div>Here is the second div!</div>
  </section>
  <script src="script.js"></script>
</body>
</html>
```

#### Accessing a parent element

If you want to access the parent element of another element, you can use the ***parentElement*** method.

```const foundDiv = document.querySelector("div")

foundDiv.parentElement // <section></section>
```

#### Accessing the children of an element

If you want to access the child elements of another element, you can use the ****children**** method.

```foundDiv.children //HTMLCollection(2) [p, ul]
foundDiv.firstElementChild //<p>Here is a paragraph inside a div!</p>
foundDiv.lastElementChild // <ul></ul>
```

#### Accessing the siblings of an element

If you want to access the previous sibling or next sibling element of another element, you can use the ***previousElementSibling*** or ***nextElementSibling*** method.

```foundDiv.previousElementSibling // <h1>Here is a main heading!</h1>
foundDiv.nextElementSibling // <div>Here is the second div!</div>
```

#### Text Nodes

You may come across other methods for finding things in the DOM, we have shown you the most common ones, but as you learn more you may come across something called a ***text node***

More about [Text Node](https://stackoverflow.com/questions/17195868/what-is-a-text-node-its-uses-document-createtextnode)

### Nodes VS Elements

- With some of these finder methods, you will see that you don’t always get back an HTML element, you sometimes get back what is called a text node
- Everything in the DOM is a **node**, some nodes are not actually HTML elements, but text or even comments!

## 3. Javascript Events

### What is an event?

DOM events are “actions” that occur as a result of something the user or the browser does.

We can use JavaScript to execute code when these kinds of “events” happen.

#### What Kinds Of Events Do We Have???

- clicking on something
- hovering over something with the mouse
- pressing certain keys
- when the DOM has loaded
- when a form is submitted


We write code that listens for events - and react accordingly!

#### How do we do it?

We have three options:

- Attach the name of the function to the element in HTML
- Attach the name of the function to an element in JavaScript
- Use the addEventListener method

**Attaching The Name Of The Function:**

```html
<h1 onclick="runClickHandler()"> Hello World </h1>
```

```js
function runClickHandler(){
  console.log("You just clicked the h1 element!");
}
```

**Adding in Javascript**

```js
const h1 = document.querySelector("h1");

h1.onclick = function(){
  console.log("You just clicked the h1 element!");
}
```

**Using addEventListener**

```js
const h1 = document.querySelector("h1");

h1.addEventListener("click", function(){
  console.log("You just clicked the h1 element!");
})
```

#### Which One Should We Use?

We’re going to go with addEventListener - here’s why:

- It gives us the most flexibility around our event listeners
- It avoids writing any inline code in our HTML and keeps our HTML and JS separate

#### Accessing The Event Object

Inside of the callback to addEventListener, we get access to a special object as a parameter - the event object

```js
const h1 = document.querySelector("h1");

h1.addEventListener("click", function(event){
  console.log(event)
})
```

#### What Is Inside Of The Event Object?

- target - what element is the target of the event
- pageX / pageY - where on the page did this event occur?
- key - what key was pressed that triggered this event?
- [preventDefault()](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault) - a function used to prevent the default behavior of the event.
  - This is **very useful** for stopping form submissions from refreshing the page which is their default behavior


```html
<form>
  Name: <input id="firstName" type="text">
  <button>Add your name!</button>
</form>
```

```js
const formElement = document.querySelector("form");

formElement.addEventListener("submit", function(event){
  console.log("you just submitted the form!")
})
```

Unfortunately, this will not work! The default behavior of a form is to trigger a refreshing of the page.

**Solution:**

If we want to stop the default behavior of an event, we need to use the special ***event.preventDefault()*** method.

```js
const formElement = document.querySelector("form");

formElement.addEventListener("submit", function(event){
  event.preventDefault();
  console.log("you just submitted the form!");
})
```
