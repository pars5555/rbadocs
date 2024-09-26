### **SysBackground.delay(seconds, argumentsToPass)**

**Description:**
The `SysBackground.delay(seconds, argumentsToPass)` function creates a delay for the specified number of seconds before resolving a promise. If `argumentsToPass` is provided and is an array, it passes those arguments when resolving the promise.

**Parameters:**
- **seconds** (Number): The time in seconds to delay the execution.
- **argumentsToPass** (Array) _(optional)_: An optional array of arguments to pass when the promise is resolved.

**Return Value:**
- A `Promise` that resolves after the specified delay. If `argumentsToPass` is provided, it resolves with those arguments.

**Example:**

```javascript
SysBackground.delay(5, ['arg1', 'arg2']).then((arg1, arg2) => {
    console.log('Delay completed with arguments:', arg1, arg2);
});
```

// Delay of 5 seconds, and then the provided arguments are logged.
```javascript
SysBackground.delay(3).then(() => {
    console.log('Delay of 3 seconds completed');
});
```