# Technical Questions

## HTML

1.  What does a doctype do?
2.  How do you serve a page with content in multiple languages?
3.  What kind of things must you be wary of when design or developing for multilingual sites?
4.  What are data- attributes good for?
5.  Consider HTML5 as an open web platform. What are the building blocks of HTML5?
6.  Describe the difference between a cookie, sessionStorage and localStorage.

    **_sessionStorage:_** _similar to localStorage. Data persistent through reloads but not tab/browser closings. Same origin policy._

    **_localStorage:_** _same origin policy. Data persistent through browser/tab closings._

    **_cookie:_** _smaller size available. Data sent back to server every time, so more traffic between client and server. More older browsers support._

7.  Describe the difference between `<script>`, `<script async>` and `<script defer>`.
8.  Why is it generally a good idea to position CSS `<link>s` between `<head></head>` and JS `<script>s` just before `</body>`? Do you know any exceptions?

    _CSS at the beginning because you want your page to be readable._

    _Script at the end because you don’t want JS loading to slow down the rendering of the fundamentals of the site._

9.  What is progressive rendering?

    _Makes a site usable on shittier connections._

    _Lazy loading: (may only load items when they are visible in the viewport)_

    _Prioritizing visible content: only using the CSS necessary for what is visible, then using deferred JS to run the rest later._

    _Bridges best of both worlds of client and server-side rendering. Rendered on the server, which is collocated with API calls, but you don’t have to wait for everything to load critical things. (Although event handlers won’t be rendered until the end, so interactivity will still take a moment to work). Next.js is one way to do this, but progressive rendering really depends on how the site is set up, and there is no one-size-fits-all solution._

10. Why you would use a srcset attribute in an image tag? Explain the process the browser uses when evaluating the content of this attribute.
11. Have you used different HTML templating languages before?

## CSS

1. What is CSS selector specificity and how does it work?

   _Determines precedence. element =1, class =10, id=100, !important =1000_

2. What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?

   _Normalize makes all browser the same, reset removes all borders. I personally prefer normalize but I can work with either._

3. Describe floats and how they work.

   _Makes an element go as far up and to the left as it can. Might need to apply clearfix to objects below it._

4. Describe z-index and how stacking context is formed.

   _Higher number puts an object higher in the stack.Stacking context created by parent elements._

5. Describe BFC (Block Formatting Context) and how it works.
6. What are the various clearing techniques and which is appropriate for what context?
7. Explain CSS sprites, and how you would implement them on a page or site.

   _All images put in a single file so that you have fewer images to serve. There are sites that automatically generate sprites._

8. How would you approach fixing browser-specific styling issues?

   _[Here](https://www.youtube.com/watch?v=9tEixRJ3GeI) is a good video about this topic (a bit outdated now that IE is finally dead, but still 99% solid info)_

   _Some items we may want to test:_

   1. CSS validation
   2. HTML or XHTML validation ([form validation!](https://caniuse.com/form-validation))
   3. Page validations with and without JavaScript enabled.
   4. Ajax and JQeury functionality
   5. Font size validation (browsers might apply different font weights with the `<strong>` tag)
   6. Page layout in different resolutions
   7. All images and alignment
   8. Header and footer sections
   9. Page content alignment to the center, LHS or RHS.
   10. Page styles
   11. Date formats
   12. Special characters with HTML character encoding.
   13. Page zoom-in and zoom-out functionality.

    <br>

   _Using normaize.css is a very popular way to make a larger share of your CSS behave the same across browsers. There is also reset.css._

   _However, reset.css is a bit heavy-handed and doesn't actually touch on "all" the user-agent styles. This is part of why normalize is popular._

   _There are also variations of normalize, e.g. Bootstrap has their own normalize. Normalize actually touches on more things than reset, and applies a consistent styling to all browsers rather than no styling._

   _However, once you've applied normalize, you might not know if the ***features*** you want to implement are available accross all browsers._

   _This is where https://caniuse.com/ is your friend. You enter the name of the CSS feature you want to use, and it pulls up a graphic showing which browsers/versions support it. It will also show you the percentage of people using each browser, and what percentage of total users would have access to your feature, so you can determine what you can get away with. You can use Google Analytics to test compatibility with your specific user base, if you have one._

   _If you search the feature in the MDN, there will usually be a browser-compatability chart at the bottom of the page. MDN overall has more information. So caniuseis good for a quick check, MDN is better for more in-depth._

   _Consider your userbase: if you are making a website for devs, a higher-than-average percent might use Firefox. If you're making the website for a bingo hall, a higher percentage likely use IE. Or a school or corporation might be locked down to older versions of browsers._

   _(fallbacks, progressive enhancement)._

   _We can also use feature queries._

   ```css
   /* CSS */
   @supports (property: value) {
   CSS rules to apply
   }

   /* e.g. */

   .box {
       border: 4px solid blue;
       color: blue;
   }
   @supports (row-gap: 10px) {
       .box {
           border: 4px solid red;
           color: red;
       }
   }
   ```

   ```html
   <!-- HTML -->
   <div class="box">
     If your browser supports row-gap, the text and border will be red.
   </div>
   ```

   _If a browser does not support a feature you really want to include, you can see if there is a polyfill for i (a polyfill is custom JS someone has written to make a feature work in an unsupported browser)._

   _You can also use https://postcss.org to add vendor-prefixes to css. PostCSS converts CSS into something most browsers can read, determining which polyfills will be needed._

9. How do you serve your pages for feature-constrained browsers? What techniques/processes do you use?

   _Graceful delegation: (making sure site runs on newer and older browsers)._

   _Progressive enhancement: build it for shitty browsers so it is passible, then add features on top of that for nicer browsers._

10. What are the different ways to visually hide content (and make it available only for screen readers)?

    _`display: none` and `visibility: hidden` take elements out of the flow of the document and also make them invisible to screen readers_

    _`text-indent: -10000px` can put an element off the screen but readers can still read it._

    _The truly proper way:_

    ```css
    .sr-only {
      position: absolute;
      left: -10000px;
      top: auto;
      width: 1px;
      height: 1px;
      overflow: hidden;
    }
    ```

11. Have you ever used a grid system, and if so, what do you prefer?
12. Have you used or implemented media queries or mobile specific layouts/CSS?
13. Are you familiar with styling SVG?
14. Can you give an example of an @media property other than screen?

    _`@media (pointer: coarse)` vs `@media (pointer: fine)`_

    _(you might make the buttons bigger if the user is using a touch screen-***course***-vs a mouse or stylus-***fine***. This is not always going to be able to 100% predict a user’s input device, though.)_

15. What are some of the "gotchas" for writing efficient CSS?
16. What are the advantages/disadvantages of using CSS preprocessors?
17. Describe what you like and dislike about the CSS preprocessors you have used.
18. How would you implement a web design comp that uses non-standard fonts?
19. Explain how a browser determines what elements match a CSS selector.
20. Describe pseudo-elements and discuss what they are used for.
21. Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
22. What does `box-sizing: border-box;` do? What are its advantages?

    _It makes margin and padding be built into size calculations. Easier to calculate with this setting._

23. What is the CSS display property and can you give a few examples of its use?

    _Determines how an element displays within the document flow (e.g. block or inline, or inline-block), and how children will be displayed_

    ```css
    .block {
      display: block;
    }

    .flex {
      display: flex;
    }
    ```

24. What's the difference between inline and inline-block?

    _Inline-block lets you set height and width of item, and it respects margins and paddings unlike inline_

25. What's the difference between a relative, fixed, absolute and statically positioned element?
26. What existing CSS frameworks have you used locally, or in production? How would you change/improve them?
27. Have you played around with the new CSS Flexbox or Grid specs?
28. Can you explain the difference between coding a web site to be responsive versus using a mobile-first strategy?

    _Mobile first is kind of “inside-to-outside”. In the end they are both mobile-friendly. However, in this day and age, mobile-first is a good strategy because a whole lot of people will be viewing your site on mobile._

29. How is responsive design different from adaptive design?

    _Responsive is more fluid and constantly changes. Adaptive moves things around at certain fixed points._

30. Have you ever worked with retina graphics? If so, when and what techniques did you use?
31. Is there any reason you'd want to use translate() instead of absolute positioning, or vice-versa? And why?

## Javascript

1. Explain event delegation
2. Explain how `this` works in JavaScript
3. Explain how prototypal inheritance works

   _Chains. When looking for a method or property, Javascript starts at the child, then the parent, and up the chain until reaching the root. All children inherent the properties and methods of their parents._

4. What do you think of AMD vs CommonJS?
5. Explain why the following doesn't work as an IIFE: function foo(){ }();. What needs to be changed to properly make it an IIFE?
6. What's the difference between a variable that is: null, undefined or undeclared? How would you go about checking for any of these states?
7. What is a closure, and how/why would you use one?
8. Can you describe the main difference between a `forEach` loop and a `map` loop and why you would pick one versus the other?

   _forEach is allowed to mutate the original and doesn’t actually return anything. Might use if you’re not trying to change data but to do something with it (like console log?)_

   _Map performs a function on every element and returns a new array_

9. What's a typical use case for anonymous functions?

   _In a higher-order function (e.g. within a .map we might just use a simple arrow function, unless we are doing a more complex map. If you’re only gonna use something once, no need to pollute the global namespace with it. (If you’re gonna use it more than once, you should give it a name, though)._

10. How do you organize your code? (module pattern, classical inheritance?)
11. What's the difference between host objects and native objects?

    _Native objects: Object (constructor), Date, Math, parseInt, eval, string methods like indexOf and replace, array methods, ... Host objects (assuming browser environment): window, document, location, history, XMLHttpRequest, setTimeout, getElementsByTagName, querySelectorAll,..._

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

    _`===` ensures that they are also the same type (otherwise JS might use coercive type conversion, e.g. string to Number)_

27. Explain the same-origin policy with regards to JavaScript.
28. Make this work: `duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]`

```js
function duplicate(arr) {
  return arr.concat(arr)
}
```

29. Why is it called a Ternary expression, what does the word "Ternary" indicate?

    _Because it takes 3 operands: The condition, expression to execute if condition is truthy, expression to execute if expression is falsey_

30. What is "use strict";? what are the advantages and disadvantages to using it?
31. Create a for loop that iterates up to 100 while outputting "fizz" at multiples of 3, "buzz" at multiples of 5 and "fizzbuzz" at multiples of 3 and 5

    ```js
    function fizzBuzz() {
      for (let i = 0; i <= 100; i++) {
        if (i % 3 === 0 && i % 5 === 0) {
          console.log('fizzbuzz')
        } else if (i % 3 === 0) {
          console.log('fizz')
        } else if (i % 5 === 0) {
          console.log('buzz')
        } else {
          console.log(i)
        }
      }
    }
    fizzBuzz()
    ```

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
    _A function that accepts functions as parameters or returns a function_
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

### Updates

2022-07-21

#### HTML: 6, 8, 9

#### CSS: 1, 2, 3, 4, 7, 8, 9, 10, 14, 22, 23, 24, 28, 29

#### JS: 3, 8, 9, 11, 26, 28, 29, 31, 48
