## [🪴 View In My Digital Garden: Security Attack - Cross-Origin Resource Sharing (CORS)](https://www.aniqa.io/wiki/security/cors)

Basic definition of the Cross-Origin Resource Sharing (CORS) policy to better understand other online security vulnerabilities.

---

> Any request for a resource outside of the host domain is known as a **cross-origin request**.

**Cross-Origin Resource Sharing (CORS) - uses HTTP request/response methods** 
- requests data from a server *after* ensuring that the server indicates **where the browser may need to load resources from**
- shares **how** the resources can be accessed *(like a receptionist that checks your ID and tells you where to go in a large office building)*
- [**Pre-flight requests**](/wiki/security/cors-preflight) using the `OPTIONS` [request header](/wiki/security/cors-headers) that is sent to the server to ensure that the data is **safe for transfer**

The CORS sharing standard includes HTTP requests for:

| Requests for... | 
| ----- | 
| `XMLHttpRequest` | 
| Fetch APIs | 
| Web Fonts (`@font-face` within CSS) |
| WebGL Textures |
| Images and video frames drawn using `drawImage()` |
| CSS Shapes from Images (`shape-outside` property) |

- HTTP Request `GET` may be allowed as it only involves viewing the assets
- HTTP Requests `PATCH`, `PUT`, `TRACE`, `DELETE` may be blocked because it **involves modifying the site assets in some way**


---


### Basic CORS Request:
**[1] Client browser begins by sending [preflight request](/wiki/security/cors-preflight) indicating the** `Origin` **[header](/wiki/security/cors-headers) with information about the current domain and which methods are being requested to use:**

```http
OPTIONS /data HTTP/1.1
Origin: https://www.aniqa.io
Access-Control-Request-Method: DELETE
```

**[2] Server will respond with** `Access-Control-Allow-Origin` **header providing access to the specified domains**

```http
HTTP/1.1 200 OK
Access-Control-Allow-Origin: https://www.aniqa.io
Access-Control-Allow-Methods: GET, DELETE, HEAD, OPTIONS
```

**[3] Browser receives the response and then, allows the response data to be shared to the client [origin](/wiki/security-origin-values) site**


### Complex CORS Request Include:

- Request that uses any method other than `GET`, `POST`, or `HEAD`
- Request that includes headers other than `Accept`, `Accept-Language`, or `Content-Language`
- Request that has a `Content-Type` header other than `application/x-www-form-urlencoded`, `multipart/form-data`, or `text/plain`
