# **SysBackground.onMessage**

## **Overview**

The `SysBackground.onMessage` function is used to listen for and handle incoming messages from other scripts or extensions, such as content scripts. This function plays a crucial role in facilitating communication between the different components of an extension, like background scripts and tabs. 

It receives messages, processes the data, and takes appropriate actions based on the content of the message, such as performing an action or sending a response.

---

## **Parameters**

1. **request** (Object)
   - The message object sent by another script, containing details like the action to be performed and any additional data.
   
2. **sender** (Object)
   - Information about the sender of the message, including the tab or frame from which the message originated.
   
3. **sendResponse** (Function)
   - A callback function that can be used to send a response back to the sender of the message.

---

## **Example Usage**

```javascript
SysBackground.onMessage(function (request, sender, sendResponse) {
    if (request.action === 'get_status') {
        // Send a response back to the content script or other sender
        sendResponse({status: 'success', message: 'Operation completed'});
    }
});