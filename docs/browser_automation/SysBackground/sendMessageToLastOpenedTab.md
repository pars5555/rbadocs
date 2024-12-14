### **SysBackground.sendMessageToLastOpenedTab(message, callback)**

**Description:**
The `SysBackground.sendMessageToLastOpenedTab()` function sends a message to the most recently opened browser tab. This message can be used to trigger actions within the content script of that tab. The function also allows passing a callback function that is executed after the message is sent.

**Parameters:**
- **message** (Object): The message to send to the last opened tab. This message can include data and actions for the content script to execute.

**Example:**

```javascript
SysBackground.sendMessageToLastOpenedTab({
    action: "someaction", 
    somedata: {
        x: 1
        y: 2.4,
        z: 'some string'        
    }
});
