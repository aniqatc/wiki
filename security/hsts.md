## [🪴 View In My Digital Garden: HTTP Strict Transport Security (HSTS)](https://www.aniqa.io/wiki/security/hsts)

Understanding how HSTS is a process that ensures websites are loaded over HTTPS only.


---

`Strict-Transport-Security` **header tells browser to never load website using HTTP and to use [HTTPS](/wiki/web) instead**
- HTTPS loads resources with an added layer of security as opposed to HTTP
- Browser will use **HTTPS protocol** for the time specified in the header (without redirection)

### Requirements for HSTS:
- Must have a **SSL Certificate** with *subdomain coverage*
- **Redirect** all HTTP links to HTTPS with a `301 Permanent Redirect`
- **Add HSTS header** for HTTPS requests using `Strict-Transport-Security`


```:title=HSTS-Header-Syntax
Strict-Transport-Security: max-age=<expire-time>
Strict-Transport-Security: max-age=<expire-time>; includeSubDomains
Strict-Transport-Security: max-age=<expire-time>; preload

max-age: specified in [seconds]
```


- Use `includeSubDomains` directive if there are subdomains
- Include the `max-age` directive to specify time in seconds (at least a year)
- Add the `preload` directive to indicate that the site owner has consented to have their domain preloaded
    - *Must be on the [HSTS Preload List](https://hstspreload.org/) which is maintained by Chrome*
 

```:title=HSTS-Real-Example
Strict-Transport-Security: max-age=31536000; includeSubDomains; preload
```

---

**Visual Representation of How HSTS Operates:**

![](https://www.aniqa.io/static/dbb7b02d018c0569cfe38e2c83dd8afe/f1720/hsts.png)
