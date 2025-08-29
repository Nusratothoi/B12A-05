1. What is the difference between getElementById, getElementsByClassName, and querySelector / querySelectorAll?
# document.getElementById("id")
Selects one element only by its unique id. Returns the element directly (not a collection).Fastest among them since IDs are unique.

const heading = document.getElementById("mainTitle");
console.log(heading.innerText);

# document.getElementsByClassName("className")
Selects all elements with a given class. Returns an HTMLCollection (array-like, live updating).
You need to loop through it to access each element.

const items = document.getElementsByClassName("list-item");
for (let i = 0; i < items.length; i++) {
  console.log(items[i].innerText);
}

# document.querySelector("selector")
Selects the first matching element based on a CSS selector. More flexible (supports IDs, classes, attributes, etc.).

const firstItem = document.querySelector(".list-item"); // first element with class
console.log(firstItem.innerText);

const firstItem = document.querySelector(".list-item"); // first element with class
console.log(firstItem.innerText);

2. How do you create and insert a new element into the DOM?
steps:
i) Use document.createElement(tagName) to create.
ii) Optionally add content, attributes, or classes.
iii) Insert it using appendChild(), append(), prepend(), or insertBefore().

3. What is Event Bubbling and how does it work?
 Event bubbling means that when an event happens on an element, it first runs the handler on that element, then propagates upward (parent → ancestor → root).

4. What is Event Delegation in JavaScript? Why is it useful?
   Event Delegation is a pattern where instead of attaching event listeners to multiple child elements, you attach a single event listener to a parent, and handle events as they bubble up.
   useful because: Less memory usage (one listener instead of many). Works even for dynamically added elements.Cleaner, scalable code.
5. What is the difference between preventDefault() and stopPropagation() methods?
# preventDefault()
Prevents the default behavior of an event.
Example: prevent form submission, prevent a link from opening

document.querySelector("form").addEventListener("submit", e => {
  e.preventDefault(); // stops form from reloading the page
  console.log("Form submission prevented");
});


# stopPropagation()
Prevents the event from bubbling up to parent elements.
Example: a button inside a div → stop parent handler from firing.

document.getElementById("child").addEventListener("click", e => {
  e.stopPropagation();  // parent won't get the event
  console.log("Child clicked only");
});

