---
title: setMultilevelObjValue
tags: object,advanced
---

This allows you to set multilevel property in an object. It is not possible directly in JavaScript since properties are not initially defined.

- Iterative approach based on the length of props array specifying the level of nesting required.
- Assign object(myObj and thus obj) reference to a temporary variable currObj.
- Check in case the property value is null and initialize to empty object if null.
- Reach the deepest props level and assign the value to it, going one level deeper per iteration.

```js
const setMultilevelObjValue = (obj, props, value) => {
   let currObj = obj;
   for (i = 0; i < props.length - 1; i++) {
     if (currObj[props[i]] == null) currObj[props[i]] = {};
     currObj = currObj[props[i]];
   }
   currObj[props[props.length - 1]] = value;
   return myObj;
 };
```

```js
myObj={};
setMultilevelObjValue(myObj, ['level1', 'level2'], "Something"); // {level1: {level2: "Something"}}
```
