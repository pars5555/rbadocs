
# Project Documentation

## Introduction
This project provides a system for creating browser automation plugins using JavaScript, facilitating seamless control and interaction with web browsers and apps.

## Features & Capabilities
- **Automated Browser Interaction**: Enables automation of browser actions like opening tabs, sending messages, and interacting with content.
- **Customizable Captcha Solvers**: Includes support for solving Captchas such as reCAPTCHA, hCaptcha, and Funcaptcha.
- **Task Management**: Automates tasks based on user-defined workflows.
- **API Integration**: Extends browser capabilities with external API support.

## How to Use

1. **Installation**:
   - Download the project repository and unzip it.
   - Follow the setup instructions in the `README.md` for dependencies and environment setup.

2. **Basic Usage**:
   - Use the built-in functions such as `openTab()`, `sendMessageToLastOpenedTab()`, and `getTaskData()` to automate tasks.
   - Example:
     ```javascript
     // Open a new tab and navigate to the specified URL
     await openTab('https://example.com');
     ```

## System Overview

The system operates by using a set of core functions and workflows that communicate with the browser. Below is an overview of the key components:

### 1. **SysBackground**:
   - Handles core background tasks like logging, task management, and interactions with the browser.
   - Key functions:
     - `callActiveTabContentFunction()`: Executes a function on the active tab.
     - `getTaskData()`: Retrieves task-related data for processing.

### 2. **SysContent**:
   - Defines content-specific operations and how they interact with the web page and browser.
   - Functions like `Input.tapOnScreen()` allow interaction with web page elements.

## Advanced Topics

### Captcha Solvers:
   - **Enabling Solvers**:
     - You can enable various Captcha solvers for reCAPTCHA, Funcaptcha, etc., by calling:
       ```javascript
       enableRecaptchaSolver();
       enableDatadomeCaptchaSolver();
       ```

## API & Functions

### `callActiveTabContentFunction()`
- Description: Calls a specified function on the active tab.
- Parameters: `functionName` (string) - The function to execute.

### `getTaskData()`
- Description: Retrieves task data for further processing.
- Parameters: None
- Returns: Task data object

## Examples

1. **Opening a Tab**:
   ```javascript
   await openTab('https://example.com');
   ```

2. **Typing Text**:
   ```javascript
   await Input.typeText({ text: 'Hello World!' });
   ```

## FAQs
- **How do I handle Captchas?**
   - Use the provided solvers like `enableRecaptchaSolver()` to bypass Captchas during automation.

