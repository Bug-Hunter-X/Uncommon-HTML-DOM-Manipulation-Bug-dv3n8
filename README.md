# Uncommon HTML Bug: DOM Manipulation Before Load

This repository demonstrates an uncommon bug in HTML related to manipulating the Document Object Model (DOM) before the page's DOM is fully loaded.  This is often overlooked, leading to unexpected behavior.

## The Bug
The bug lies in attempting to modify the style of an element (`#myDiv`) before the browser has fully parsed and rendered the HTML. Because the script executes before the DOM is ready, the `getElementById` method might return `null`, resulting in a JavaScript error or, even worse, no visible effect. 

## The Solution
The solution is to ensure that the script that manipulates the DOM runs after the DOM is fully loaded. This is typically achieved by using the `DOMContentLoaded` event listener or placing your script right before the closing `</body>` tag (this method is less reliable).