## [🪴 View In My Digital Garden: Security Attack - CORS HTTP Headers](https://www.aniqa.io/wiki/security/cors-headers)


---

> **HTTP Header** = information that describes an **HTTP Request** or **Response** and is sent alongside the specified requests and responses.

## [CORS](/wiki/security/cors) HTTP Headers
- `Access-Control-Allow-Origin`
    - indicates whether the response can be shared



- `Access-Control-Allow-Credentials`
    - whether response to request can be revealed when the credentials are flagged *true*; 
    - [credentials can be cookies, authorization headers, SSL/TLS client certificates]




- `Access-Control-Allow-Headers`
    - used as a response to [*preflight requests*](/wiki/security/cors-preflight) to indicate which [HTTP headers](/wiki/) can be used during the original [CORS](/wiki/security/cors) request; 
    - allows server to indicate which response headers should be made available to scripts running in the browser





- `Access-Control-Allow-Methods`
    - response that specifies one or more methods allowed when accessing a resource in response to the [*preflight request*](/wiki/security/cors-preflight);




- `Access-Control-Expose-Headers`
    - indicates which headers can be revealed as part of the response by listing their names




- `Access-Control-Max-Age`
    - indicates how long the results of a [*preflight request*](/wiki/security/cors-prelight) can be cached
    - relates to the information contained in `Access-Control-Allow-Methods` and `Access-Control-Allow-Headers`





- `Access-Control-Request-Headers`
    - used when issuing a [*preflight request*](/wiki/security/cors-preflight) to let server know which HTTP headers will be used during the main request
    - [the response given from the server-side will be the `Access-Control-Allow-Headers` header]





- `Access-Control-Request-Method` - *header is a must since the preflight request will always be an* `OPTIONS` *HTTP method & is not = to the* **actual request method**
    - used to issue a [*preflight request*](/wiki/security/cors-preflight) to let server know which [HTTP method](/wiki/) will be used during the main request





- `ORIGIN`
    - indicates where a fetch originates from (providing information about the [protocol scheme, hostname, and port](/wiki/security/origin-values) that started the request)



### Additional Notes

The `X-Content-Type-Options: nosniff` header lets the server say: 
   - *"hey, don't allow this to be parsed as CSS or JS unless I've sent the right* `Content-Type`"

The `nosniff` rules were expanded to prevent particular no-CORS response types from another [origin](/wiki/security/origin-values), such as HTML, JSON, and XML (except SVG). This protection is called [CORB](https://fetch.spec.whatwg.org/#corb). CORB stands for **cross-origin read blocking**. 

---

*More recently*, we don't send cookies along with the request from `site-A` to `site-B`, unless `site-B`, *the receiving end*, has opted-in using the `SameSite` [cookie attribute](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie/SameSite). 
