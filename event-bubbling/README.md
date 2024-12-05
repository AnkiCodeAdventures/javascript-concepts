# Event Bubbling in JavaScript

## Definition

Event bubbling is a mechanism in JavaScript where an event triggered on a child element "bubbles" up through its ancestors in the DOM hierarchy.

## Core Concept

This means the event starts at the element that triggered it (the target element) and propagates upward to its parent, grandparent, and so on, until it reaches the root of the document.

When you click on the Child Button:
Child clicked!
Parent clicked!
Grandparent clicked!
The event propagates from the child element to its parent (parent), and then to its grandparent (grandparent).

## Propagation Mechanism

- Events move from the most specific element (target) to the least specific (document root)
- The event continues to bubble up unless explicitly stopped
- It can be stopped from propagating further up the DOM tree by using stopPropagation() function on the event object

## Event Delegation

Event delegation relies on the fact that events triggered on a child element propagate (or "bubble up") to its parent elements. Instead of attaching an event listener to each child element, you attach a single event listener to a common ancestor (parent). When the event bubbles up, the parent can "catch" it and determine which child element was the actual target of the event using event.taget property.

## Significance

- ### Enables Event Delegation:

  Event bubbling allows attaching a single event listener to a parent element to manage events for its child elements, improving efficiency and handling dynamic content.

- ### Improves Performance:
  It reduces memory usage and processing overhead by minimizing the number of event listeners required in a complex DOM structure.
- ### Simplifies Code Maintenance:
  Centralized event handling at the parent level keeps the code cleaner, easier to read, and easier to debug.
- ### Facilitates Dynamic Content Handling
  When child elements are added or removed dynamically (e.g., via JavaScript), bubbling ensures that the parent can handle events for these new elements without needing additional listeners
