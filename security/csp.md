## [🪴 View In My Digital Garden: Content Security Policy (CSP)](https://www.aniqa.io/wiki/security/csp)

The definition of the Content Security Policy and how it protects against certain online attacks, including cross-site scripting, data injection and theft, and more.

---


### Definition & Use
**Content Security Policy (CSP): layer of security that detects and mitigates attacks ranging from cross-site scripting (XSS), data injection, data theft, site defacing, and malware distribution**
- If browser does not support it or if the website does not offer the CSP header, then it defaults to the [standard **same-origin policy** for web content](/wiki/security/same-origin)
- Allows **restrictions** on malicious: [1] remote scripts, [2] unsafe javascript, [3] inline scripts, [4] form submissions, [5] objects
- Used as *bonus* [security](/wiki/security) protocol

### Threats
**Cross-Site Script (XSS) Attacks & [Clickjacking](/wiki/security/clickjacking)**: exploits a browser's trust in the data it receives from a web server - making it possible for malicious scripts to run in the user's browsers **without a red flag alerted initially**
- **Stored or Persistent** - injected script is stored permanently on target servers
- **Reflected or Non-Persistent** - script is injected to the web server from clicking a malicious link or browsing a malicious site; browser already trusts the webpage because it has already made a secure connection to it 
- **DOM-Based** - malicious modifications done to the DOM environment which is the browser

### Solution
1. **List of trusted sources** - `Content-Security-Policy` makes it possible to specify specific domains that the browser can identify as **valid sources of executable scripts** *(making it so that the browsers **ignore scripts** that do not come from the list of sources approved by the web server)*
2. **List of trusted protocols** - server can specify which protocols are allowed to be used:
    - A server can specify that all content has to load using HTTPS
    - Make all cookies with the `secure` attribute
    - Automatic redirects from HTTP pages to their HTTPS equivalent [(HSTS)](/wiki/security/hsts)
    - Use `Strict-Transport-Security` HTTP Header to ensure that browsers connect to the web server over an encrypted channel

#### How to Enable CSP
- Add the `Content-Security-Policy` HTTP header to webpage
- Add values to `Content-Security-Policy` that specify which resources the user device is allowed to load

HTML `<meta>` element can be used to configure a policy:

```html:title=CSP-Example noLineNumbers
<meta http-equiv="Content-Security-Policy"
      content="default-src 'self'; 
            img-src https://*; 
            child-src 'none';">
```

`meta` **Attributes Explained:**
- `http-equiv` identifies the HTTP header
- `content` identifies sources of content that can be loaded to the origin webpage, restricting anything that's not specified
    - Under `content`, directives are specified and their respective URLs

---

**Policy**: described using a series of policy directives that each specify a specific resource type
- Specify the policy: `Content-Security-Policy: policy`

---

### Directives for `content` Attribute
**Fetch Directives: locations to trust and load resources from**

- `default-src` specifies the default policy for loading JavaScript, CSS, fonts, resources, AJAX requests, etc (always include a `default-src` policy directive as fallback for other resource types when they don't have policies of their own)




- `script-src` specifies valid sources for Javascript, including URLs within `<script>` element and inline scripts
    - `script-src-elem` location from which execution of script requests and blocks can occur
    - `script-src-attr` event handlers





- `style-src` specifies valid sources for CSS, includes `<link>` element, `@import` rules
    - `style-src-elem` specifies styles except for inline attributes
    - `style-src-attr` specifies attributes





- `img-src` specifies valid sources for images
- `font-src` specifies the locations that fonts can be loaded
- `media-src` specifies locations of video, audio, or other media resources can be loaded from
- `object-src` specifies the URLs where plugins can be loaded from
- `prefetch-src` specifies the URLs where resources can be prefetched from
- `manifest-src` specifies application manifests that can be loaded
- `connect-src` specifies valid targets for XmlHttpRequest (AJAX), WebSockets, or EventSource - if a connection attempt is made to a host that is not listed as a valid target, browser will emulate a `400` status code error



**Document Directives: tells browser about properties of the document that the policies can be applied to**
- `base-uri` specifies possible URLs that `<base>` element can use
- `plugin-types` limits types of resources that can be loaded (_e.g._ application/pdf, affecting the `<embed>` and `<object>` elements. 
**Rules:**
 1. Declare element type
 2. Element has to match declared type
 3. Resource has to match declared type
- `sandbox` can restrict certain page actions
    - works when combined with request header like so:  `Content-Security-Policy: sandbox;`
    - not adding a value for `sandbox` activates all sandbox restrictions

**Navigation Directives: tells the browser about the locations that the documents are allowed to navigate to**
- `form-action` specifies restricted URLs that form cannot submit to
- `frame-ancestors` restricts the URLs that can embed the requested resource inside of `<frame>`, `<iframe>`, `<object>`, `<embed>`, or `<applet>` elements
    - If specified in `<meta>` tag = ignored
    - Does not fall-back to `default-src`
    - `X-Frame-Options` is obsolete when `frame-ancestors` is used


**Special Directive Values**
- `'self'` = sources that have the same scheme/protocol, same host, and same port as the file defining the `Content-Security-Policy`
- `'none'` = no URLs
- `'unsafe-inline'` = allows the usage of inline scripts and styles
- `'unsafe-eval'` = allows the usage of `eval` in scripts
- `'strict-dynamic'` = informs browser to trust scripts originating from a root trusted script; must be combined with another directive value to work

**Using multiple directives**: separate different policy directives using a semicolon `;` under one `<meta>` element

![](https://www.aniqa.io/static/6e76eb1574a645a0b26b913747d2db56/2f212/csp-block.png)
