### **SysBackground.callActiveTabContentFunction(methodName, params, allFrames = false)**

**Description:**
The `SysBackground.callActiveTabContentFunction()` function sends a message to the most recently active tab, requesting the execution of a specified content script function (`methodName`) with given parameters (`params`). This function returns a `Promise` that resolves when the content script function completes its execution.

The `allFrames` parameter allows specifying whether the function should be executed in all frames of the tab.

**Parameters:**
- **methodName** (String): The name of the function to be executed in the content script of the active tab.
- **params** (Array or Object): The parameters to be passed to the content script function.
- **allFrames** (Boolean) _(optional)_: If `true`, the function is called on all frames in the active tab. Default is `false` (calls only in the main frame).

**Return Value:**
- A `Promise` that resolves or rejects based on the success of the content script function execution.

**Example:**

```javascript
SysBackground.callActiveTabContentFunction('validateCardDetails', { 
    cardNumber: '1234567890123456', 
    expiryDate: '12/33', 
    cvv: '123' 
}).then(result => {
    SysBackground.log('Card validation result:', result);
}).catch(error => {
    SysBackground.error('Error validating card:', error);
});
