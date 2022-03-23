## [🪴 View In My Digital Garden: Security Attack - Clickjacking](https://www.aniqa.io/wiki/security/clickjacking)

What Clickjacking is and how to defend your websites against it as a developer.

---

**Clickjacking** = an attack that embeds a site in an existing `iframe` element and overlays a transparent button that links to a different destination, a *malicious* destination

![](https://www.aniqa.io/static/583bf173813714dd7a4fb4a199944c17/96430/clickjacking.png)

#### [Defense Against Clickjacking Attacks](/wiki/security/csp):
1. Prevent browser from loading your webpage in an `iframe` using an HTTP header that utilizes:
    - `Content-Security-Policy: frame-ancestors: 'special-directive';` HTTP header
    - `X-Frame-Options` HTTP header
2. Prevent session cookies from being included when page is loaded in a frame using the `SameSite` cookie attribute
3. Frame-Buster: Implementing JavaScript code to prevent it from being loaded in a frame

`frame-ancestors` indicates whether or not a webpage should be allowed to render within a `<frame>`, `<iframe>`, `<embed>` or `<object>`

#### Use-Cases:

Recommended: prevents **any** domain from framing the webpage content
- `Content-Security-Policy: frame-ancestors 'none';` 



Allows only the host site to frame the content
- `Content-Security-Policy: frame-ancestors 'self';`



Allows host-website `self` any page on the site with the asterisk using any particular protocol `*.anything.com`, and the specified page only using HTTPS `https://safe.example.io`

```noLineNumbers
Content-Security-Policy: frame-ancestors 'self' 
*.example.com 
https://example.io
   ```
