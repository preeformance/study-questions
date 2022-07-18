# Technical Questions

## HTML

1. What does a doctype do?
2. How do you serve a page with content in multiple languages?
3. What kind of things must you be wary of when design or developing for multilingual sites?
4. What are data- attributes good for?
5. Consider HTML5 as an open web platform. What are the building blocks of HTML5?
6. Describe the difference between a cookie, sessionStorage and localStorage.
7. Describe the difference between `<script>`, `<script async>` and `<script defer>`.
8. Why is it generally a good idea to position CSS `<link>s` between `<head></head>` and JS `<script>s` just before `</body>`? Do you know any exceptions?
9. What is progressive rendering?
10. Why you would use a srcset attribute in an image tag? Explain the process the browser uses when evaluating the content of this attribute.
11. Have you used different HTML templating languages before?

## CSS

1. What is CSS selector specificity and how does it work?
2. What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
3. Describe floats and how they work.
4. Describe z-index and how stacking context is formed.
5. Describe BFC (Block Formatting Context) and how it works.
6. What are the various clearing techniques and which is appropriate for what context?
7. Explain CSS sprites, and how you would implement them on a page or site.
8. How would you approach fixing browser-specific styling issues?
9. How do you serve your pages for feature-constrained browsers? What techniques/processes do you use?
10. What are the different ways to visually hide content (and make it available only for screen readers)?
11. Have you ever used a grid system, and if so, what do you prefer?
12. Have you used or implemented media queries or mobile specific layouts/CSS?
13. Are you familiar with styling SVG?
14. Can you give an example of an @media property other than screen?
15. What are some of the "gotchas" for writing efficient CSS?
16. What are the advantages/disadvantages of using CSS preprocessors?
17. Describe what you like and dislike about the CSS preprocessors you have used.
18. How would you implement a web design comp that uses non-standard fonts?
19. Explain how a browser determines what elements match a CSS selector.
20. Describe pseudo-elements and discuss what they are used for.
21. Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
22. What does \* { box-sizing: border-box; } do? What are its advantages?
23. What is the CSS display property and can you give a few examples of its use?
24. What's the difference between inline and inline-block?
25. What's the difference between a relative, fixed, absolute and statically positioned element?
26. What existing CSS frameworks have you used locally, or in production? How would you change/improve them?
27. Have you played around with the new CSS Flexbox or Grid specs?
28. Can you explain the difference between coding a web site to be responsive versus using a mobile-first strategy?
29. How is responsive design different from adaptive design?
30. Have you ever worked with retina graphics? If so, when and what techniques did you use?
31. Is there any reason you'd want to use translate() instead of absolute positioning, or vice-versa? And why?

## Javascript

1. Explain event delegation
2. Explain how `this` works in JavaScript
3. Explain how prototypal inheritance works
4. What do you think of AMD vs CommonJS?
5. Explain why the following doesn't work as an IIFE: function foo(){ }();. What needs to be changed to properly make it an IIFE?
6. What's the difference between a variable that is: null, undefined or undeclared? How would you go about checking for any of these states?
7. What is a closure, and how/why would you use one?
8. Can you describe the main difference between a .forEach loop and a .map() loop and why you would pick one versus the other?
9. What's a typical use case for anonymous functions?
10. How do you organize your code? (module pattern, classical inheritance?)
11. What's the difference between host objects and native objects?
12. Difference between: function Person(){}, var person = Person(), and var person = new Person()?
13. What's the difference between .call and .apply?
14. Explain Function.prototype.bind.
15. When would you use document.write()?
16. What's the difference between feature detection, feature inference, and using the UA string?
17. Explain Ajax in as much detail as possible.
18. What are the advantages and disadvantages of using Ajax?
19. Explain how JSONP works (and how it's not really Ajax).
20. Have you ever used JavaScript templating? If so, what libraries have you used?
21. Explain "hoisting".
22. Describe event bubbling.
23. What's the difference between an "attribute" and a "property"?
24. Why is extending built-in JavaScript objects not a good idea?
25. Difference between document load event and document DOMContentLoaded event?
26. What is the difference between == and ===?
27. Explain the same-origin policy with regards to JavaScript.
28. Make this work: `duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]`
29. Why is it called a Ternary expression, what does the word "Ternary" indicate?
30. What is "use strict";? what are the advantages and disadvantages to using it?
31. Create a for loop that iterates up to 100 while outputting "fizz" at multiples of 3, "buzz" at multiples of 5 and "fizzbuzz" at multiples of 3 and 5
32. Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
33. Why would you use something like the load event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?
34. Explain what a single page app is and how to make one SEO-friendly.
35. What is the extent of your experience with Promises and/or their polyfills?
36. What are the pros and cons of using Promises instead of callbacks?
37. What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
38. What tools and techniques do you use debugging JavaScript code?
39. What language constructions do you use for iterating over object properties and array items?
40. Explain the difference between mutable and immutable objects.
41. Explain the difference between synchronous and asynchronous functions.
42. What is event loop? What is the difference between call stack and task queue?
43. Explain the differences on the usage of foo between function foo() {} and var foo = function() {}
44. What are the differences between variables created using let, var or const?
45. What are the differences between ES6 class and ES5 function constructors?
46. Can you offer a use case for the new arrow => function syntax? How does this new syntax differ from other functions?
47. What advantage is there for using the arrow syntax for a method in a constructor?
48. What is the definition of a higher-order function?
49. Can you give an example for destructuring an object or an array?
50. ES6 Template Literals offer a lot of flexibility in generating strings, can you give an example?
51. Can you give an example of a curry function and why this syntax offers an advantage?
52. What are the benefits of using spread syntax and how is it different from rest syntax?
53. How can you share code between files?
54. Why you might want to create static class members?

## Javascript General

1. Can you name two programming paradigms important for JavaScript app developers?
2. What is functional programming?
3. What is the difference between classical inheritance and prototypal inheritance?
4. What are the pros and cons of functional programming vs object-oriented programming?
5. What are two-way data binding and one-way data flow, and how are they different?
6. What is asynchronous programming, and why is it important in JavaScript?

## Node

1. What is Node.js? Where can you use it?
2. Why use Node.js?
3. What are the features of Node.js?
4. How do you update NPM to a new version in Node.js?
5. Why is Node.js Single-threaded?
6. Explain callback in Node.js.
7. What is callback hell in Node.js?
8. How do you prevent/fix callback hell?
9. Explain the role of REPL in Node.js.
10. Name the types of API functions in Node.js.
11. What are the functionalities of NPM in Node.js?
12. What is the difference between Node.js and Ajax?
13. What are “streams” in Node.js? Explain the different types of streams present in Node.js.
14. Explain chaining in Node.js.
15. What are Globals in Node.js?
16. What is Event-driven programming?
17. What is Event loop in Node.js work? And How does it work?
18. What is the purpose of module.exports in Node.js?
19. What is the difference between Asynchronous and Non-blocking?
20. What is Tracing in Node.js?
21. How will you debug an application in Node.js?
22. Difference between setImmediate() vs setTimeout()?
23. What is process.nextTick()
24. What is package.json? What is it used for?
25. What is libuv?
26. What are some of the most popular modules of Node.js?
27. What is EventEmitter in Node.js?

## Computer Science

1. What is recursion and give an example using javascript?
2. What are types?
3. What are data structures?
4. What is an algorithm?
5. What is scope / lexical scope in javascript?
6. What is polymorphism?
7. What is encapsulation?
8. What is a Linked List
9. What is a Doubly Linked List
10. What is a Queue
11. What is a Stack
12. What is a Hash Table
13. What is a Heap
14. What is a Trie
15. What is a Tree
16. What is a Binary Search Tree
17. What is a Disjoint Set
18. What is a Bloom Filter
19. Demonstrate Bubble Sort and explain when you might use it?
20. Demonstrate Insertion Sort and explain when you might use it?
21. Demonstrate Merge Sort and explain when you might use it?
22. Demonstrate Quicksort and explain when you might use it?
