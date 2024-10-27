## goit-neo-js-hw-07

## Homework Topic 11/12: DOM Model/ Events


## Task 1

HTML contains a list of categories ul#categories.

<ul id="categories">
  <li class="item">
    <h2>Animals</h2>
    <ul>
      <li>Cat</li>
      <li>Hamster</li>
      <li>Horse</li>
      <li>Parrot</li>
    </ul>
  </li>
  <li class="item">
    <h2>Products</h2>
    <ul>
      <li>Bread</li>
      <li>Parsley</li>
      <li>Cheese</li>
    </ul>
  </li>
  <li class="item">
    <h2>Technologies</h2>
    <ul>
      <li>HTML</li>
      <li>CSS</li>
      <li>JavaScript</li>
      <li>React</li>
      <li>Node.js</li>
    </ul>
  </li>
</ul>


Using DOM element properties and methods, write a script that:

Counts and logs the number of categories in ul#categories, i.e., li.item elements.
For each li.item element in the ul#categories list, find and log the text of the element's heading (the <h2> tag) and the number of items in that category (all <li> nested within it).



## Task 2

Write a script to create an image gallery based on an array of data. HTML contains an ul.gallery list.

<ul class="gallery"></ul>

Use the images array of objects to create <img> elements nested within <li>.

You can create and add HTML elements using document.createElement() and elem.append() or template strings and elem.insertAdjacentHTML().

All gallery elements should be added to the DOM in a single insertion operation.
Apply minimal styling to the gallery using Flexbox via CSS classes.

const images = [
  {
    url: "https://images.pexels.com/photos/140134/pexels-photo-140134.jpeg?dpr=2&h=750&w=1260",
    alt: "White and Black Long Fur Cat",
  },
  {
    url: "https://images.pexels.com/photos/213399/pexels-photo-213399.jpeg?dpr=2&h=750&w=1260",
    alt: "Orange and White Koi Fish Near Yellow Koi Fish",
  },
  {
    url: "https://images.pexels.com/photos/219943/pexels-photo-219943.jpeg?dpr=2&h=750&w=1260",
    alt: "Group of Horses Running",
  },
];



## Task 3

Write a script that, while typing in the input#name-input (on input event), inserts its current value into span#name-output as the name for greeting. Ensure to trim leading and trailing spaces from the input value. If the input is empty or contains only spaces, replace the name in the span with "Anonymous".

<input type="text" id="name-input" placeholder="Please enter your name" />
<h1>Hello, <span id="name-output">Anonymous</span>!</h1>



## Task 4

Write a script to manage a login form.

<form class="login-form">
  <label>
    Email
    <input type="email" name="email" />
  </label>
  <label>
    Password
    <input type="password" name="password" />
  </label>
  <button type="submit">Log in</button>
</form>

The form submission for form.login-form should be triggered by the submit event.
The page should not reload when the form is submitted.
If there are empty fields upon submission, display an alert with the message: 'All form fields must be filled in.' Do not add the required attribute to the inputs; validation should be performed using JavaScript.
If the user fills in all fields and submits the form, collect the field values into an object with two properties. The keys are the input names, and the values are the corresponding input values, trimmed of leading and trailing spaces. Use the elements property to access form elements.
Upon form submission, log the object containing the entered data to the console and reset the form fields using the reset method.



## Task 5

Write a script that changes the background colour of the <body> element through inline style when clicking on a button.change-color and sets this colour value as the text content for span.color.

<div class="widget">
  <p>Background color: <span class="color">-</span></p>
  <button type="button" class="change-color">Change color</button>
</div>

Use the getRandomHexColor()function to generate a random colour.

function getRandomHexColor() {
  return `#${Math.floor(Math.random() * 16777215)
    .toString(16)
    .padStart(6, 0)}`;
}



Note that the getRandomHexColor() function returns a colour in hex format, whereas the background colour on <body> will be in RGB format. This is fine and does not require any changes.



## Task 6

Write a script for creating and clearing a collection of elements with the following functionality.

There is an input where the user enters the desired number of elements. After clicking the Create button, a collection with the corresponding elements should be rendered (added to the DOM), and the input value should be cleared. When clicking the Create button again, a new collection should be rendered on top of the old one. After clicking the Destroy button, the collection of elements should be cleared.

<div id="controls">
  <input type="number" min="1" max="100" step="1" />
  <button type="button" data-create>Create</button>
  <button type="button" data-destroy>Destroy</button>
</div>

<div id="boxes"></div>

After the user clicks the Create button, validate the value in the input to ensure it falls within the inclusive range of 1 to 100. Only if the value meets this condition should new <div> elements be added to the DOM.

To render the elements on the page, create a function createBoxes(amount) that takes one parameter — a number representing the number of elements to render.

The function should generate the specified number of <div> elements and add them as children of div#boxes to the DOM.

The dimensions of the first <div> element should be 30px by 30px.
Each subsequent <div> should be 10px wider and taller than the previous one.
All elements should have a random background colour. Use the provided getRandomHexColor() function to generate a random colour.

function getRandomHexColor() {
  return `#${Math.floor(Math.random() * 16777215)
    .toString(16)
    .padStart(6, 0)}`;
}

To clear the collection after clicking the Destroy button, create a destroyBoxes() function that empties the contents of div#boxes, thereby removing all created elements.



## Requirements
- Code must be formatted with Prettier.
- There must be no errors or warnings in the console after running the tasks.
- Execution of tasks 1, 2 and 3.

## Formatting the code with Prettier:

* You must have Node.js installed, then install Prettier in your project. This can be done with the command in the terminal:

```bash
npm install --save-dev prettier
```

* Then you can run Prettier on your code with:

```bash
npx prettier --write .
```

This command will format all files in the project.