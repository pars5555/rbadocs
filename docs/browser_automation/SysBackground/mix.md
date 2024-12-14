### **SysBackground.reloadActiveTab(callback, reloadProperties)**]

**Description:**
The `reloadActiveTab()` function reloads the active tab in the browser with the provided properties.

**Parameters:**
- **callback** (Function): The function to execute after the tab is reloaded.
- **reloadProperties** (Object): The properties to pass when reloading the tab.

**Example:**

```javascript
SysBackground.reloadActiveTab(function() {
    console.log('Tab reloaded');
}, {bypassCache: true});
```

---

### **SysBackground.navigateLastOpenedTab(params, callback)**

**Description:**
The `navigateLastOpenedTab()` function navigates the most recently opened tab to a new URL, with optional referrer and transition properties.

**Parameters:**
- **params** (Object): The parameters for the navigation (e.g., `url`, `referrer`, `transitionType`).
- **callback** (Function): Function to execute once the navigation is complete.

**Example:**

```javascript
SysBackground.navigateLastOpenedTab({url: 'https://example.com'}, function() {
    console.log('Navigation completed');
});
```

---

### **SysBackground.addDebuggerEventListener(eventName, listener)**

**Description:**
The `addDebuggerEventListener()` function adds a listener for a specific debugger event.

**Parameters:**
- **eventName** (String): The name of the debugger event to listen for.
- **listener** (Function): The function to execute when the event occurs.

---

### **SysBackground.removeDebuggerEventListener(eventName, listener)**

**Description:**
The `removeDebuggerEventListener()` function removes a listener for a specific debugger event.

**Parameters:**
- **eventName** (String): The name of the debugger event.
- **listener** (Function): The function to remove from the event's listener list.

---

### **SysBackground.get(url, onSuccess, onError)**

**Description:**
The `get()` function performs a GET request to the provided URL.

**Parameters:**
- **url** (String): The URL to send the GET request to.
- **onSuccess** (Function): Function to execute if the request is successful.
- **onError** (Function): Function to execute if the request fails.

**Example:**

```javascript
SysBackground.get('https://example.com', function(response) {
    console.log('Response received:', response);
}, function(error) {
    console.log('Error:', error);
});
```

---

### **SysBackground.postJson(url, json, onSuccess, onError)**

**Description:**
The `postJson()` function sends a POST request with JSON data to the specified URL.

**Parameters:**
- **url** (String): The URL to send the POST request to.
- **json** (Object or String): The JSON data to send.
- **onSuccess** (Function): Function to execute if the request is successful.
- **onError** (Function): Function to execute if the request fails.

**Example:**

```javascript
SysBackground.postJson('https://example.com', {key: 'value'}, function(response) {
    console.log('Response received:', response);
}, function(error) {
    console.log('Error:', error);
});
```

---

### **SysBackground.post(url, params, onSuccess, onError)**

**Description:**
The `post()` function sends a POST request to the specified URL with form-encoded parameters.

**Parameters:**
- **url** (String): The URL to send the POST request to.
- **params** (Object): The parameters to encode and send with the request.
- **onSuccess** (Function): Function to execute if the request is successful.
- **onError** (Function): Function to execute if the request fails.

**Example:**

```javascript
SysBackground.post('https://example.com', {key: 'value'}, function(response) {
    console.log('Response received:', response);
}, function(error) {
    console.log('Error:', error);
});
```

---

### **SysBackground.getActiveTabJpegImage(options, callback)**

**Description:**
The `getActiveTabJpegImage()` function captures a JPEG image of the active tab's visible content and returns it as a base64-encoded string.

**Parameters:**
- **options** (Object): The capture options (e.g., `quality`, `box_size`, etc.).
- **callback** (Function): Function to execute with the captured image data.

**Example:**

```javascript
SysBackground.getActiveTabJpegImage({quality: 80}, function(imgBase64) {
    console.log('Image captured:', imgBase64);
});
```
