
# **SysBackground.openPage**

## **Overview**

The `SysBackground.openPage` function is used to open a new browser tab and navigate to a specified URL. It provides flexibility in defining the navigation process, allowing you to handle events before the URL is submitted to the address bar and after it has been processed.

This function is especially useful for automating browser-based tasks where programmatic navigation and page interaction are required. It supports additional options like setting the referrer, defining the referrer policy, and more.

---

## **Parameters**

### **params** (Object or String)

The primary object containing the navigation settings.

- **url** (String): The target URL to which the browser should navigate. If a string is passed directly, it will be treated as the URL.
- **referrer** (String) _(optional)_: A URL to be sent as the referrer in the request. If not provided, the browser will omit the referrer header.
- **referrerPolicy** (String) _(optional)_: Defines the referrer policy to apply. Default is `'origin'`.
- **transitionType** (String) _(optional)_: Specifies the transition type for navigation. Default is `'link'`.

**Example:**

```javascript
let params = {
  url: 'https://example.com',
  referrer: 'https://referrer.com',
  referrerPolicy: 'origin',
  transitionType: 'link'
};
```

---

### **beforeSubmitUrl** (Function) _(optional)_

This is a callback function that is executed **before** the URL is submitted into the address bar, but after the tab is created. It can be used to set up any preconditions, such as enabling solvers or adjusting the environment.

- **Arguments**: Receives the created tab object as an argument.

**Example:**

```javascript
function beforeSubmitUrl(tab) {
  SysBackground.log('Tab created:', tab);
  SysBackground.enableCustomSolver({});
}
```

---

### **afterUrlSubmit** (Function) _(optional)_

This is a callback function that is executed **after** the URL has been submitted into the address bar, but before the page has fully loaded. It allows you to interact with the page load process, such as monitoring headers or setting up event listeners.

- **Arguments**: Receives the tab object or the navigation status for iOS after the URL is submitted.

**Example:**

```javascript
function afterUrlSubmit(tab) {
  SysBackground.onHeadersReceived(onCustomEvent, {match_urls: 'https://example.com/api*'});
}
```

---

## **Example Usage**

```javascript
SysBackground.openPage(
  {
    url: 'https://example.com',
    referrer: ''
  },
  // Callback executed before URL submission
  function (tab) {
    SysBackground.enableCustomSolver({});
  },
  // Callback executed after URL is submitted into the address bar
  function () {
    SysBackground.onHeadersReceived(onCustomEvent, {match_urls: 'https://example.com/api*'});
  }
);

// Adding a delay and reload in case the condition isn't met
SB.delay(20).then(() => {
  if (!customEventLoaded) {
    SB.reloadActiveTab();
    exitProcess(80, '__start__');
  }
});
```

---

## **How It Works**

1. **Initial URL Navigation**: 
   The function initially opens the browser with a placeholder URL (`about:blank`, `chrome://version`, or platform-specific URLs like `about://version` for Samsung browsers) before navigating to the specified URL.

2. **Before URL Submission**: 
   Once the tab is created, the `beforeSubmitUrl` callback is executed. This can be used to set up solvers or handle any tasks that need to occur before the URL is processed.

3. **Navigating to the Target URL**: 
   The system navigates to the final URL using `SysBackground.navigateLastOpenedTab`. This triggers the necessary parameters like referrer and transition type.

4. **After URL Submission**: 
   The `afterUrlSubmit` callback is executed after the URL has been submitted into the address bar, allowing further handling of the page loading process.

---

## **Additional Functions**

### **SysBackground.navigateLastOpenedTab**
This helper function is used by `openPage` to navigate the last opened tab to the target URL, handling specific referrer and transition options.

- **params**: Same options as in `openPage`.
- **callback**: Function that is executed after navigation is complete.
