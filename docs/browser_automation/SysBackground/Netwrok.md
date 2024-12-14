### **SysBackground.interceptRequest(callback, params, onAttached)**

**Description:**
The `interceptRequest()` function is deprecated and will throw an error when called. It was previously used to intercept network requests.

**Parameters:**
- **callback** (Function): The function to execute when a request is intercepted.
- **params** (Object): Contains `match_urls` and `request_method` to filter the requests.
- **onAttached** (Function): Function executed when the debugger is attached.

---

### **SysBackground.modifyRequest(callback, params, onAttached)**

**Description:**
The `modifyRequest()` function modifies network requests based on the provided callback and URL match patterns.

**Parameters:**
- **callback** (Function): Function to modify the request.
- **params** (Object): Contains `match_urls` and `request_method`.
- **onAttached** (Function): Executed when the debugger is attached.

**Example:**

```javascript
SysBackground.modifyRequest(function(details) {
    console.log('Request modified:', details);
}, { match_urls: ['https://example.com/*'], request_method: 'GET' });
```

---

### **SysBackground.onExtensionIconClick(callback)**

**Description:**
The `onExtensionIconClick()` function sets a callback to be executed when the extension icon is clicked.

**Parameters:**
- **callback** (Function): The function to execute when the extension icon is clicked.

**Example:**

```javascript
SysBackground.onExtensionIconClick(function() {
    console.log('Extension icon clicked');
});
```

---

### **SysBackground.interceptResponse(callback, params, onAttached)**

**Description:**
The `interceptResponse()` function allows you to intercept network responses that match specified URL patterns and request methods.

**Parameters:**
- **callback** (Function): Function to handle the intercepted response.
- **params** (Object): Contains `match_urls` and `request_method`.
- **onAttached** (Function): Executed when the debugger is attached.

**Example:**

```javascript
SysBackground.interceptResponse(function(response) {
    console.log('Response intercepted:', response);
}, { match_urls: ['https://example.com/*'], request_method: 'GET' });
```

---

### **SysBackground.onResponseBodyReceived(callback, params, onAttached)**

**Description:**
The `onResponseBodyReceived()` function listens for the response body of requests that match the provided patterns.

**Parameters:**
- **callback** (Function): Function to process the response body.
- **params** (Object): Contains `match_urls` and `request_method`.
- **onAttached** (Function): Executed when the debugger is attached.

---

### **SysBackground.onBeforeRequest(callback, params)**

**Description:**
The `onBeforeRequest()` function listens for requests that are about to be sent and allows modifying them before they are processed.

**Parameters:**
- **callback** (Function): Function to handle the request before it is sent.
- **params** (Object): Contains `match_urls` and `request_method`.

---

### **SysBackground.onNetworkError(callback, params)**

**Description:**
The `onNetworkError()` function listens for network errors and triggers the callback when a network error occurs.

**Parameters:**
- **callback** (Function): Function to handle the network error.
- **params** (Object): Contains `match_urls` and `request_method`.

---

### **SysBackground.onBeforeSendHeaders(callback, params)**

**Description:**
The `onBeforeSendHeaders()` function listens for requests before the headers are sent and allows modifying the headers.

**Parameters:**
- **callback** (Function): Function to modify the headers before they are sent.
- **params** (Object): Contains `match_urls` and `request_method`.

---

### **SysBackground.onExecutionContextCreated(callback)**

**Description:**
The `onExecutionContextCreated()` function sets a callback that will be executed when a new execution context is created.

**Parameters:**
- **callback** (Function): Function to execute when the execution context is created.

---

### **SysBackground.onSendHeaders(callback, params)**

**Description:**
The `onSendHeaders()` function listens for the headers being sent with a network request and allows processing them.

**Parameters:**
- **callback** (Function): Function to process the headers.
- **params** (Object): Contains `match_urls` and `request_method`.

---

### **SysBackground.onRequestCompleted(callback, params)**

**Description:**
The `onRequestCompleted()` function listens for the completion of network requests that match the specified patterns.

**Parameters:**
- **callback** (Function): Function to handle the request completion.
- **params** (Object): Contains `match_urls` and `request_method`.

---

### **SysBackground.onHeadersReceived(callback, params)**

**Description:**
The `onHeadersReceived()` function listens for the headers received from a network request and allows processing them.

**Parameters:**
- **callback** (Function): Function to process the headers received.
- **params** (Object): Contains `match_urls` and `request_method`.

---

### **SysBackground.onMessage(callback)**

**Description:**
The `onMessage()` function sets a callback to handle messages sent to the background script.

**Parameters:**
- **callback** (Function): Function to handle incoming messages.

---

### **SysBackground.onBeforeExit(callback)**

**Description:**
The `onBeforeExit()` function sets a callback that is executed before the plugin exits.

**Parameters:**
- **callback** (Function): Function to handle actions before the plugin exits.

---

### **SysBackground.onPageAlert(callback)**

**Description:**
The `onPageAlert()` function sets a callback that is executed when a page alert is triggered.

**Parameters:**
- **callback** (Function): Function to handle page alerts.

---
