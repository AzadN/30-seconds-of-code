---
title: preventPaste
tags: browser,event,intermediate
---

Prevents paste operation into an input field.

- Get the input field element using document.getElementbyID("inputField_id").
- Use the HTMLElement.onpaste property  to handle the paste event which is fired on paste attempt.
- Override the default paste behaviour using event.preventDefault() and return false to disable pasting.

```js
const pasteBox = document.getElementById("paste-no-event");
pasteBox.onpaste = (e) => {
  e.preventDefault();
  return false;
};
```

```js
// A live usage example can be found at : https://codepen.io/JSsnippets/pen/qBbyMoJ
// Provided since it is not possible to demonstrate the usage without actually having the required HTML/CSS components.
```
